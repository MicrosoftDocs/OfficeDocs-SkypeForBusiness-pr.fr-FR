---
title: Intégration entre Skype Entreprise Online et le serveur Exchange
ms.reviewer: cbland
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/17/2022
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: La configuration de l’authentification OAuth entre Exchange local et Skype Entreprise Online active les fonctionnalités d’intégration de Skype Entreprise et Exchange décrites dans la prise en charge des fonctionnalités.
ms.openlocfilehash: 0b312dfde144f12a9c2db523ce4526153b445d59
ms.sourcegitcommit: e3931446943684db155bb3edf7d7e52d41775013
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2022
ms.locfileid: "65886641"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Configurer l’intégration et OAuth entre Skype Entreprise Online et Exchange Server 

La configuration de l’intégration entre exchange server et Skype Entreprise Online active les fonctionnalités Skype Entreprise et Exchange Integration décrites dans la [prise en charge des fonctionnalités](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Cette rubrique s’applique à l’intégration à Exchange Server 2013 à 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Ce qu’il faut savoir avant de commencer

- Durée d'exécution estimée de cette tâche : 15 minutes

-  Des autorisations doivent vous être attribuées avant de pouvoir exécuter cette procédure. Pour connaître les autorisations dont vous avez besoin, consultez la rubrique [sur les autorisations d’infrastructure Exchange et Shell](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) .

- Pour des informations sur les raccourcis clavier applicables aux procédures de cette rubrique, voir Raccourcis clavier dans Exchange 2013[Raccourcis clavier dans le Centre d'administration Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Pour plus d’informations sur la compatibilité, consultez [La compatibilité de Skype Entreprise avec les applications Office](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurer l’intégration entre Exchange Server et O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Étape 1 : Configurer l’authentification OAuth entre Exchange Server et O365

Effectuez les étapes décrites dans l’article suivant :

[Configurer l’authentification OAuth entre des organisations Exchange et Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Étape 2 : Créer un compte d’utilisateur de messagerie pour l’application partenaire Skype Entreprise Online

Cette étape est effectuée sur le serveur Exchange. Il crée un utilisateur de messagerie et lui attribue les droits de rôle de gestion appropriés. Ce compte sera ensuite utilisé à l’étape suivante.

Spécifiez un domaine vérifié pour votre organisation Exchange. Ce domaine doit être le même que le domaine SMTP principal utilisé pour les comptes Exchange locaux. Ce domaine est appelé \<your Verified Domain\> dans la procédure suivante. En outre, il \<DomainControllerFQDN\> doit s’agir du nom de domaine complet d’un contrôleur de domaine.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Cette commande masque le nouvel utilisateur de messagerie des listes d’adresses.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Ces deux commandes suivantes attribuent le rôle de gestion UserApplication et ArchiveApplication à ce nouveau compte.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Étape 3 : Créer et activer une application partenaire pour Skype Entreprise Online 

Créez une application partenaire et utilisez le compte que vous venez de créer. Exécutez la commande suivante dans Exchange PowerShell dans votre organisation Exchange locale.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Étape 4 : Exporter le certificat d’autorisation local

Exécutez un script PowerShell pour exporter le certificat d’autorisation local, que vous importerez dans votre organisation Skype Entreprise Online à l’étape suivante.

Enregistrez le texte suivant dans un fichier de script PowerShell nommé, par exemple, ExportAuthCert.ps1.

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false) {
    md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

Dans Exchange PowerShell dans votre organisation Exchange locale, exécutez le script PowerShell que vous venez de créer. Par exemple : .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Étape 5 : Charger le certificat d’autorisation local dans Azure Active Directory ACS

Ensuite, utilisez Windows PowerShell pour charger le certificat d’autorisation local que vous avez exporté à l’étape précédente vers Azure Active Directory Access Control Services (ACS). Pour ce faire, le module Azure Active Directory pour les applets de commande Windows PowerShell doit déjà être installé. Si elle n'est pas installée, accédez à [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) pour installer la cmdlet Module Azure Active Directory pour Windows PowerShell. Effectuez les étapes suivantes une fois que la cmdlet Module Azure Active Directory pour Windows PowerShell est installée.

1. Cliquez sur le raccourci **Module Windows Azure Active Directory pour Windows PowerShell** afin d'ouvrir un espace de travail Windows PowerShell pour lequel les cmdlets Azure AD sont installées. Dans cette étape, toutes les commandes seront exécutées à l'aide de la console Windows PowerShell pour Azure Active Directory.

2. Enregistrez le texte suivant dans un fichier de script PowerShell nommé, par exemple,  `UploadAuthCert.ps1`.

   ```powershell
   Connect-MsolService
   Import-Module MSOnline
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile)
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert)
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000"
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. Exécutez le script PowerShell que vous avez créé à l'étape précédente. Par exemple :  `.\UploadAuthCert.ps1`

4. Une fois le script lancé, une boîte de dialogue d'informations d'identification s'affiche. Entrez les informations d’identification du compte d’administrateur client de votre organisation Microsoft Online Azure AD. Après avoir exécuté le script, laissez la session Windows PowerShell pour Azure AD ouverte. Vous l'utiliserez pour exécuter un script PowerShell à l'étape suivante.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Étape 6 : Vérifier que le certificat a été chargé sur le principal du service Skype Entreprise
1. Dans PowerShell ouvert et authentifié au sein d’Azure Active Directory, exécutez les opérations suivantes :

   ```powershell
   Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
   ```
2. Appuyez sur Entrée lorsque vous êtes invité à entrer ReturnKeyValues
3. Vérifiez que vous voyez une clé répertoriée avec les données de date de début et de fin qui correspondent aux dates de début et de fin de votre certificat Exchange Oauth

### <a name="verify-your-success"></a>Vérifier votre réussite

Vérifiez que la configuration est correcte en vérifiant que certaines fonctionnalités fonctionnent correctement. 

1. Vérifiez que les utilisateurs de Skype Entreprise avec le service de messagerie vocale cloud, dans une organisation avec une configuration Exchange Server hybride, peuvent modifier avec succès leurs messages d’accueil de messagerie vocale.

2. Vérifiez que l’historique des conversations pour les clients mobiles est visible dans le dossier Historique des conversations Outlook.

3. Vérifiez que les messages de conversation archivés sont déposés dans la boîte aux lettres locale de l’utilisateur dans le dossier Purges à l’aide [d’EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor).

Vous pouvez également examiner votre trafic. Le trafic dans une négociation OAuth est vraiment distinctif (et ne ressemble pas à l’authentification de base), en particulier autour des domaines, où vous commencerez à voir le trafic émetteur qui ressemble à ceci : 00000004-0000-0ff1-ce00-000000000000@ (parfois avec un / avant le signe @ ), dans les jetons qui sont passés. Vous ne verrez pas de nom d’utilisateur ou de mot de passe, ce qui est le point d’OAuth. Mais vous verrez l’émetteur « Office » (dans ce cas, « 4 » est Skype Entreprise ) et le domaine de votre abonnement.

Si vous souhaitez être sûr d’utiliser OAuth avec succès, assurez-vous de savoir à quoi vous attendre et de savoir à quoi doit ressembler le trafic. Voici donc [à quoi vous attendre](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), voici un exemple assez standard [de trafic OAuth dans une application Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (très utile à lire, même s’il n’utilise pas de jetons d’actualisation), et il existe des extensions Fiddler qui vous permettent d’examiner votre jeton web OAuth JWT (JSON Web Token).

Voici un [exemple de configuration](/archive/blogs/kaevans/updated-fiddler-oauth-inspector), mais vous pouvez utiliser n’importe quel outil de suivi réseau que vous aimez pour entreprendre ce processus.

## <a name="related-topics"></a>Rubriques connexes

[Configurer l’authentification OAuth entre des organisations Exchange et Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
