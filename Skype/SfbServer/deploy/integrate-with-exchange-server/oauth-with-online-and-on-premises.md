---
title: Configurer OAuth entre Skype pour Business Online et Exchange sur site
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Configuration OAuth authentification entre Exchange sur site et Skype pour Business Online permet la Skype pour les fonctionnalités d’entreprise et l’intégration d’Exchange décrites dans prise en charge de la fonctionnalité.
ms.openlocfilehash: cb822dd183e913fd1b3258cc136572380592733f
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2018
ms.locfileid: "22138608"
---
# <a name="configure-oauth-between-skype-for-business-online-and-exchange-on-premises"></a>Configurer OAuth entre Skype pour Business Online et Exchange sur site
 
Configuration OAuth authentification entre Exchange sur site et Skype pour Business Online permet la Skype pour les fonctionnalités d’entreprise et l’intégration d’Exchange décrites dans la [fonction prend en charge](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).
  
Cette rubrique s’applique à Exchange Server 2016 et Exchange Server 2013.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Que devez-vous savoir avant de commencer ?

- Temps estimé pour réaliser cette tâche : 15 minutes
    
-  Avant de pouvoir réaliser cette (ces) procédure(s), des autorisations doivent vous avoir été attribuées. Pour voir les autorisations dont vous avez besoin, consultez la rubrique [autorisations d’infrastructure Exchange et Shell](https://go.microsoft.com/fwlink/p/?LinkId=746511) .
    
- Pour plus d’informations sur les raccourcis clavier applicables aux procédures de cette rubrique, voir [raccourcis clavier dans le centre d’administration Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).
    
## <a name="configure-oauth-authentication-between-your-on-premises-exchange-and-skype-for-business-organizations"></a>Configurer l’authentification OAuth entre vos organisations Exchange et Skype Entreprise locales.

### <a name="step-1-create-an-authorization-server-object-for-your-skype-for-business-online-organization"></a>Étape 1 : Créer un objet serveur d’autorisation pour votre Skype pour une organisation Business en ligne

Spécifiez un domaine vérifié pour votre Skype pour l’organisation en ligne Business. Ce domaine doit être le même domaine que celui utilisé comme domaine SIP principal pour les comptes sur le cloud. Ce domaine est appelé \<votre domaine vérifié\> dans la procédure suivante.
  
Exécutez la commande suivante dans Exchange Management Shell (Exchange PowerShell) dans votre environnement local organisation Exchange.
  
```
New-AuthServer -Name "WindowsAzureACS" -AuthMetadataUrl "https://accounts.accesscontrol.windows.net/<your Verified Domain>/metadata/json/1" 
```

### <a name="step-2-enable-the-partner-application-for-your-skype-for-business-online-organization"></a>Étape 2 : Activer l’application partenaire pour votre Skype pour une organisation Business en ligne

Exécutez la commande suivante dans Exchange PowerShell dans votre environnement local organisation Exchange.
  
```
Get-PartnerApplication | ?{$_.ApplicationIdentifier -eq "00000002-0000-0ff1-ce00-000000000000" -and $_.Realm -eq ""} | Set-PartnerApplication -Enabled $true
```

### <a name="step-3-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Étape 3 : Créer un nouveau compte d’utilisateur de messagerie pour le Skype pour Application de partenaire métier en ligne

Cette étape est effectuée en local. Elle crée un utilisateur de messagerie et lui attribue les droits de rôle de gestion adaptés. Ce compte sera alors utilisé lors de l’étape suivante.
  
Spécifiez un domaine vérifié pour votre organisation Exchange. Ce domaine doit être le même domaine que celui utilisé en tant que le domaine SMTP principal utilisé pour les comptes Exchange sur site. Ce domaine est appelé \<votre domaine vérifié\> dans la procédure suivante. En outre, le \<DomainControllerFQDN\> doit être le nom de domaine complet du contrôleur de domaine. 
  
```
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN> 
```

Cette commande masquera le nouvel utilisateur de messagerie dans les listes d’adresses.
  
```
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN> 
```

Les deux commandes qui suivent permettront d’attribuer les rôles de gestion ArchiveApplication et UserApplication à ce nouveau compte.
  
```
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN> 
```

```
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN> 
```

### <a name="step-4-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Étape 4 : Créer et activer une Application partenaire pour Skype pour Business Online

Créez une nouvelle application partenaire et utilisez le compte que vous venez de créer. Exécutez la commande suivante dans Exchange PowerShell dans votre environnement local organisation Exchange. 
  
```
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-5-export-the-on-premises-authorization-certificate"></a>Étape 5 : exportez le certificat d’autorisation locale

Exécuter un script PowerShell pour exporter le certificat d’autorisation local, vous l’importez à votre Skype pour une organisation Business Online à l’étape suivante.
  
Enregistrez le texte suivant dans un fichier de script PowerShell appelé, par exemple, ExportAuthCert.ps1.
  
```
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

Dans Exchange PowerShell dans votre organisation Exchange locale, exécutez le script PowerShell que vous venez de créer. Par exemple :.\ExportAuthCert.ps1
  
### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Étape 6 : chargez le certificat d’autorisation locale dans Azure Active Directory ACS

Utilisez ensuite Windows PowerShell pour télécharger le certificat d’autorisation locale que vous avez exporté au cours de l’étape précédente pour Azure Active Directory Access Control Services (ACS). Pour ce faire, le module Azure Active Directory pour applets de commande Windows PowerShell doit déjà être installé. S’il n’est pas installé, accédez à [https://aka.ms/aadposh](https://aka.ms/aadposh) pour installer le Azure Active Directory Module pour Windows PowerShell. Complétez les étapes suivantes après avoir installé le module Azure Active Directory pour Windows PowerShell.
  
1. Cliquez sur le raccourci du **module Azure Active Directory pour Windows PowerShell** pour ouvrir un espace de travail Windows PowerShell qui contient les applets Azure AD installées. Dans cette étape, toutes les commandes seront exécutées au moyen de la console Windows PowerShell pour Azure Active Directory.
    
2. Enregistrez le texte suivant dans un fichier de script PowerShell nommé, par exemple, `UploadAuthCert.ps1`.
    
  ```
  Connect-MsolService; 
Import-Module msonlineextended; 
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer" 
$objFSO = New-Object -ComObject Scripting.FileSystemObject; 
$CertFile = $objFSO.GetAbsolutePathName($CertFile); 
$cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate 
$cer.Import($CertFile); 
$binCert = $cer.GetRawCertData(); 
$credValue = [System.Convert]::ToBase64String($binCert); 
$ServiceName = "00000002-0000-0ff1-ce00-000000000000"; 
$p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName 
New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue 
  ```

3. Exécutez le script PowerShell que vous avez créé lors de l’étape précédente. Par exemple :`.\UploadAuthCert.ps1`
    
4. Une fois que vous avez lancé le script, une boîte de dialogue d’informations d’identification s’affiche. Entrez les données d’identification du compte d’administrateur client de votre organisation Microsoft Online Azure AD. Après avoir exécuté le script, laissez la session Windows PowerShell pour Azure AD ouverte. Vous l’utiliserez pour exécuter un script PowerShell à l’étape suivante.
    
### <a name="step-7-register-the-hostname-authorities-for-the-smtp-domain"></a>Étape 7 : inscrivez les autorités de nom d’hôte pour le domaine SMTP

Spécifiez un domaine vérifié pour votre organisation Exchange. Ce domaine doit être le même domaine que celui utilisé en tant que le domaine SMTP principal utilisé pour les comptes Exchange sur site. Ce domaine est appelé \<votre domaine vérifié\> dans la procédure suivante.
  
> [!NOTE]
> Pour exécuter correctement le script suivant, Windows PowerShell pour Azure Active Directory doit être connecté à votre client Microsoft Online Azure AD, comme expliqué dans l’étape 4 de la section précédente. 
  
1. Enregistrez le texte suivant dans un fichier de script PowerShell appelé, par exemple, RegisterEndpoints.ps1. Dans cet exemple, un caractère générique est utilisé pour enregistrer tous les points de terminaison pour contoso.com. Remplacez contoso.com par une autorité de nom d’hôte pour votre organisation d’Exchange sur site
    
  ```
  $externalAuthority="*.<your Verified Domain>" 
$ServiceName = "00000002-0000-0ff1-ce00-000000000000"; 
$p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName; 
$spn = [string]::Format("{0}/{1}", $ServiceName, $externalAuthority); 
$p.ServicePrincipalNames.Add($spn); 
Set-MsolServicePrincipal -ObjectID $p.ObjectId -ServicePrincipalNames $p.ServicePrincipalNames; 
  ```

2.  Dans Windows PowerShell pour Azure Active Directory, exécutez le script Windows PowerShell que vous avez créé lors de l’étape précédente. Par exemple : `.\RegisterEndpoints.ps1`
    
### <a name="verify-your-success"></a>Vérifiez que tout fonctionne correctement

Vérifiez que la configuration OAuth est correcte en vous assurant que certaines des fonctionnalités fonctionnent correctement (par exemple, l’historique des conversations pour les clients mobiles doit être visible dans l’historique des conversations d’Outlook).
  
1. Démarrer le Skype pour l’application mobile Professionnel sur vos périphériques iOS ou pour Windows Phone et connectez-vous en tant qu’un Skype pour utilisateur Business Online avec un 2016 Exchange ou une boîte aux lettres locale de Exchange 2013.
    
2. Avoir une conversation par messagerie instantanée avec un autre Skype pour l’utilisateur d’entreprise en ligne.
    
3. Fermez la fenêtre de conversation de la messagerie instantanée.
    
4. Démarrez Outlook pour cet utilisateur et vérifiez que la conversation est visible dans l’historique des conversations d’Outlook.
    
Consultez également le trafic. Le trafic dans un protocole OAuth est vraiment différente (et ne ressemble à l’authentification de base), en particulier autour de domaines, où vous allez commencer à voir le trafic émetteur qui ressemble à ceci : 00000004-0000-0ff1-ce00-000000000000 @ (parfois avec un / avant le signe @), dans les jetons sont passées. Vous ne verrez pas un nom d’utilisateur ou le mot de passe, qui est le point de OAuth. Mais vous verrez l’émetteur « Office », dans ce cas '4' Skype pour les entreprises – et le domaine de votre abonnement.

Si vous souhaitez que vous utilisez correctement OAuth, assurez-vous que vous savez quoi s’attendre et savoir quoi doit ressembler le trafic. C' [est ici à quoi s’attendre](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), Voici un assez standard [exemple du trafic OAuth dans une application Microsoft](http://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (très utile lire, s’il n’utilise des jetons d’actualisation), et il existe des extensions de Fiddler qui vous permet de rechercher dans votre JWT (JSON OAuth Jeton Web). 

Voici un [exemple de configuration](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), mais vous pouvez utiliser n’importe quel outil de suivi réseau que vous entreprenez ce processus.
