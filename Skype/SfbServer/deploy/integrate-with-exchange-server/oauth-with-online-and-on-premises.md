---
title: Intégration de Skype entreprise Online et du serveur Exchange
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: La configuration de l’authentification OAuth entre Exchange sur site et Skype entreprise Online permet d’activer les fonctionnalités d’intégration de Skype entreprise et Exchange décrites dans la rubrique prise en charge des fonctionnalités.
ms.openlocfilehash: b673332ea4c4428e68d6434c4638cbc78aa0ba7d
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797045"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Configurer l’intégration et le protocole OAuth entre Skype entreprise Online et Exchange Server 

La configuration de l’intégration d’Exchange Server et de Skype entreprise Online permet d’activer les fonctionnalités d’intégration Skype entreprise et Exchange décrites dans la rubrique [prise en charge](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)des fonctionnalités.

Cette rubrique s’applique à l’intégration à Exchange Server 2013 à 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Que devez-vous savoir avant de commencer ?

- Temps estimé pour réaliser cette tâche : 15 minutes

-  Avant de pouvoir réaliser cette (ces) procédure(s), des autorisations doivent vous avoir été attribuées. Pour connaître les autorisations dont vous avez besoin, consultez la rubrique [autorisations d’infrastructure Exchange et noyau](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Pour plus d’informations sur les raccourcis clavier susceptibles d’être appliqués aux procédures décrites dans cette rubrique, voir [raccourcis clavier dans le centre d’administration Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Pour plus d’informations sur la compatibilité, reportez-vous à la rubrique [compatibilité de Skype entreprise avec les applications Office](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurer l’intégration entre Exchange Server et O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Étape 1 : configuration de l’authentification OAuth entre Exchange Server et O365

Suivez les étapes décrites dans l’article suivant :

[Configurer l’authentification OAuth entre les organisations Exchange et Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Étape 2 : créer un compte d’utilisateur de messagerie pour l’application partenaire de Skype entreprise Online

Cette étape est exécutée sur le serveur Exchange. Elle crée un utilisateur de messagerie et lui attribue les droits de rôle de gestion adaptés. Ce compte sera alors utilisé lors de l’étape suivante.

Spécifiez un domaine vérifié pour votre organisation Exchange. Ce domaine doit être identique à celui utilisé pour le domaine SMTP principal utilisé pour les comptes Exchange locaux. Ce domaine est connu sous \<le nom de\> domaine vérifié dans la procédure suivante. Par ailleurs, \<le\> DomainControllerFQDN doit être le nom de domaine complet d’un contrôleur de domaine.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Cette commande masquera le nouvel utilisateur de messagerie dans les listes d’adresses.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Les deux commandes qui suivent permettront d’attribuer les rôles de gestion ArchiveApplication et UserApplication à ce nouveau compte.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Étape 3 : créer et activer une application partenaire pour Skype entreprise Online 

Créez une nouvelle application partenaire et utilisez le compte que vous venez de créer. Exécutez la commande suivante dans Exchange PowerShell dans votre organisation Exchange locale.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Étape 4 : exporter le certificat d’autorisation local

Exécutez un script PowerShell pour exporter le certificat d’autorisation local que vous allez importer vers votre organisation Skype entreprise Online à l’étape suivante.

Enregistrez le texte suivant dans un fichier de script PowerShell appelé, par exemple, ExportAuthCert.ps1.

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false)
{
md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

Dans Exchange PowerShell dans votre organisation Exchange locale, exécutez le script PowerShell que vous venez de créer. Par exemple : .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Étape 5 : Télécharger le certificat d’autorisation local auprès d’Azure Active Directory ACS

Utilisez ensuite Windows PowerShell pour télécharger le certificat d’autorisation locale que vous avez exporté au cours de l’étape précédente pour Azure Active Directory Access Control Services (ACS). Pour ce faire, le module Azure Active Directory pour applets de commande Windows PowerShell doit déjà être installé. Si ce n’est pas le cas, [https://aka.ms/aadposh](https://aka.ms/aadposh) accédez à l’installation du module Azure Active Directory pour Windows PowerShell. Complétez les étapes suivantes après avoir installé le module Azure Active Directory pour Windows PowerShell.

1. Cliquez sur le raccourci du **module Azure Active Directory pour Windows PowerShell** pour ouvrir un espace de travail Windows PowerShell qui contient les applets Azure AD installées. Dans cette étape, toutes les commandes seront exécutées au moyen de la console Windows PowerShell pour Azure Active Directory.

2. Enregistrez le texte suivant dans un fichier de script PowerShell nommé, par exemple `UploadAuthCert.ps1`.

   ```powershell
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. Exécutez le script PowerShell que vous avez créé lors de l’étape précédente. Par exemple :`.\UploadAuthCert.ps1`

4. Une fois que vous avez lancé le script, une boîte de dialogue d’informations d’identification s’affiche. Entrez les données d’identification du compte d’administrateur client de votre organisation Microsoft Online Azure AD. Après avoir exécuté le script, laissez la session Windows PowerShell pour Azure AD ouverte. Vous l’utiliserez pour exécuter un script PowerShell à l’étape suivante.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Étape 6 : vérifier que le certificat a été téléchargé pour le principal du service Skype entreprise
1. Dans PowerShell ouvert et authentifié dans Azure Active Directory, exécutez la commande suivante :
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. Appuyez sur entrée lorsque vous êtes invité à ReturnKeyValues
3. Confirmez que vous voyez une clé qui correspond à la date de début et aux données de fin correspondant aux dates de début et de fin de votre certificat OAuth Exchange.

### <a name="verify-your-success"></a>Vérifiez que tout fonctionne correctement

Vérifiez que la configuration est correcte en vérifiant que certaines fonctionnalités fonctionnent correctement. 

1. Assurez-vous que les utilisateurs de Skype entreprise avec le service de messagerie vocale Cloud, au sein d’une organisation qui dispose d’une configuration Exchange Server hybride, peuvent modifier les messages d’accueil de la boîte vocale.

2. L’historique des conversations pour les clients mobiles est visible dans le dossier historique des conversations Outlook.

3. Vérifiez que les messages archivés sont déposés dans la boîte aux lettres locale de l’utilisateur dans le dossier purges à l’aide de [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).

Vous pouvez également examiner votre trafic. Le trafic d’une connexion OAuth est réellement distinctif (et ne ressemble pas à l’authentification de base), en particulier par rapport aux domaines, où vous commencerez à voir le trafic de l’émetteur qui ressemble à ce qui suit : 00000004-0000-0ff1-CE00-000000000000 @ (parfois avec le signe/devant le signe @), dans les jetons transmis. Aucun nom d’utilisateur ou mot de passe ne s’affiche, qui est le point de OAuth. Néanmoins, vous verrez l’émetteur’Office', dans le cas où « 4 » est Skype entreprise, ainsi que le domaine de votre abonnement.

Si vous voulez vous assurer que vous utilisez correctement OAuth, assurez-vous que vous savez à quoi il doit s’attendre et que vous savez à quoi ressemble le trafic. Voici [ce à quoi vous pouvez vous attendre, vous](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)trouverez ci-dessous un [exemple standard de trafic OAuth dans une application Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (il est réellement utile de lire, même si elle n’utilise pas de jeton d’actualisation), et il existe des extensions Fiddler qui vous permettront d’accéder à votre JWT OAUTH (jeton Web JSON).

Voici un [exemple de configuration d’une valeur unique](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), mais vous pouvez utiliser n’importe quel outil de suivi réseau qui vous plaît pour engager ce processus.

## <a name="related-topics"></a>Rubriques connexes

[Configurer l’authentification OAuth entre les organisations Exchange et Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
