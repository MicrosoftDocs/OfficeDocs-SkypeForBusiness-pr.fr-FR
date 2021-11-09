---
title: Intégration entre Skype Entreprise Online et Exchange server
ms.reviewer: cbland
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: La configuration de l’authentification OAuth entre Exchange local et Skype Entreprise Online active les fonctionnalités d’intégration Skype Entreprise et Exchange décrites dans la prise en charge des fonctionnalités.
ms.openlocfilehash: dfc1bf25b19779b6a568a70e2cf18287d2f95d18
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864231"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Configurer l’intégration et OAuth entre Skype Entreprise Online et Exchange Server 

La configuration de l’intégration entre Exchange serveur et Skype Entreprise Online active les fonctionnalités d’intégration Skype Entreprise et Exchange décrites dans la prise en charge [des fonctionnalités.](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)

Cette rubrique s’applique à l’intégration Exchange Server 2013 à 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Ce qu’il faut savoir avant de commencer

- Durée d'exécution estimée de cette tâche : 15 minutes

-  Des autorisations doivent vous être attribuées avant de pouvoir exécuter cette procédure. Pour voir les autorisations qui vous sont nécessaires, consultez la [rubrique Exchange’autorisations d’infrastructure de l’Exchange shell.](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help)

- Pour obtenir des informations sur les raccourcis clavier applicables aux procédures de cette rubrique, reportez-vous à l’article [Raccourcis clavier dans le Centre d’administration Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Pour plus d’informations sur la compatibilité, [voir Skype Entreprise compatibilité avec Office applications.](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md)

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurer l’intégration entre Exchange Server et O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Étape 1 : Configurer l’authentification OAuth entre Exchange Server et O365

Effectuez les étapes de l’article suivant :

[Configurer l’authentification OAuth entre des organisations Exchange et Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Étape 2 : Créer un compte d’utilisateur de messagerie pour l’application Skype Entreprise Online Partner

Cette étape est effectuée sur le Exchange serveur. Il crée un utilisateur de messagerie et lui attribue les droits de rôle de gestion appropriés. Ce compte sera ensuite utilisé à l’étape suivante.

Spécifiez un domaine vérifié pour votre Exchange organisation. Ce domaine doit être le même domaine que celui utilisé comme domaine SMTP principal pour les comptes Exchange locaux. Ce domaine est appelé dans \<your Verified Domain\> la procédure suivante. En outre, \<DomainControllerFQDN\> il doit s’agit du nom de domaine (FQDN) d’un contrôleur de domaine.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Cette commande masquera le nouvel utilisateur de messagerie dans les listes d’adresses.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Les deux commandes suivantes affecteront le rôle de gestion UserApplication et ArchiveApplication à ce nouveau compte.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Étape 3 : Créer et activer une application partenaire pour Skype Entreprise Online 

Créez une application partenaire et utilisez le compte que vous avez créé. Exécutez la commande suivante dans Exchange PowerShell dans votre organisation Exchange locale.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Étape 4 : Exporter le certificat d’autorisation local

Exécutez un script PowerShell pour exporter le certificat d’autorisation local, que vous importez dans votre organisation Skype Entreprise Online à l’étape suivante.

Enregistrez le texte suivant dans un fichier de script PowerShell nommé, par exemple, ExportAuthCert.ps1.

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

Dans Exchange PowerShell dans votre organisation Exchange local, exécutez le script PowerShell que vous vient de créer. Par exemple : .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Étape 5 : Télécharger certificat d’autorisation local pour Azure Active Directory ACS

Ensuite, utilisez Windows PowerShell pour télécharger le certificat d’autorisation local que vous avez exporté à l’étape précédente vers Azure Active Directory Access Control Services (ACS). Pour ce faire, le module Azure Active Directory pour Windows PowerShell cmdlets doit déjà être installé. Si elle n'est pas installée, accédez à [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) pour installer la cmdlet Module Azure Active Directory pour Windows PowerShell. Effectuez les étapes suivantes une fois que la cmdlet Module Azure Active Directory pour Windows PowerShell est installée.

1. Cliquez sur le raccourci **Module Windows Azure Active Directory pour Windows PowerShell** afin d'ouvrir un espace de travail Windows PowerShell pour lequel les cmdlets Azure AD sont installées. Dans cette étape, toutes les commandes seront exécutées à l'aide de la console Windows PowerShell pour Azure Active Directory.

2. Enregistrez le texte suivant dans un fichier de script PowerShell nommé, par exemple,  `UploadAuthCert.ps1` .

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

3. Exécutez le script PowerShell que vous avez créé à l'étape précédente. Par exemple :  `.\UploadAuthCert.ps1`

4. Une fois le script lancé, une boîte de dialogue d'informations d'identification s'affiche. Entrez les informations d’identification du compte d’administrateur client de votre organisation Microsoft Online Azure AD client. Après avoir exécuté le script, laissez la session Windows PowerShell pour Azure AD ouverte. Vous l'utiliserez pour exécuter un script PowerShell à l'étape suivante.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Étape 6 : Vérifier que le certificat a été téléchargé vers le principal Skype Entreprise service
1. Dans le PowerShell ouvert et authentifié Azure Active Directory, exécutez la liste suivante :
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. Appuyez sur Entrée lorsque vous y invitez ReturnKeyValues
3. Confirmez que vous voyez une clé avec des données de date de début et de fin qui correspond à vos dates de début et de fin Exchange certificat Oauth

### <a name="verify-your-success"></a>Vérifier votre réussite

Vérifiez que la configuration est correcte en vérifiant que certaines fonctionnalités fonctionnent correctement. 

1. Confirmez que Skype Entreprise utilisateurs ayant un service Messagerie vocale infonuagique, dans une organisation avec une configuration Exchange Server hybride, peuvent modifier correctement leurs messages d’accueil vocaux.

2. Confirmez que l’historique des conversations pour les clients mobiles est visible dans Outlook’historique des conversations.

3. Confirmez que les messages de conversation archivés sont déposés dans la boîte aux lettres sur site de l’utilisateur dans le dossier Purges à l’aide [d’EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor).

Vous pourz également examiner votre trafic. Le trafic dans une poignée de main OAuth est vraiment distinct (et ne ressemble pas à l’authentification de base), en particulier autour des domaines, où vous allez commencer à voir le trafic de l’émetteur qui ressemble à ceci : 00000004-0000-0ff1-ce00-000000000000@ (parfois avec un / avant le signe @), dans les jetons transmis. Vous ne verrez pas de nom d’utilisateur ou de mot de passe, qui est le point d’OAuth. Mais vous verrez l’émetteur « Office » (dans ce cas, « 4 » est Skype Entreprise) et le domaine de votre abonnement.

Si vous voulez être sûr d’utiliser OAuth avec succès, assurez-vous que vous savez à quoi vous attendre et à quoi le trafic doit ressembler. Voici donc ce à quoi vous devez vous attendre, voici un exemple assez standard de trafic [OAuth](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) dans une application Microsoft (vraiment utile pour lire, bien [qu’il](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)n’utilise pas de jetons d’actualisation), et il existe des extensions Fiddler qui vous permet d’examiner votre JWT OAuth (jeton web JSON).

Voici un exemple de [configuration](/archive/blogs/kaevans/updated-fiddler-oauth-inspector)d’un outil de suivi réseau, mais vous pouvez utiliser n’importe quel outil de suivi réseau pour effectuer ce processus.

## <a name="related-topics"></a>Rubriques connexes

[Configurer l’authentification OAuth entre des organisations Exchange et Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)