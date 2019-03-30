---
title: Déployer les équipes Microsoft salles avec Exchange Online
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lisez cette rubrique pour plus d’informations sur la façon de déployer Microsoft équipes salles avec Exchange Online.
ms.openlocfilehash: 09a9cf6ed01ea4b523e6f790d30a586e92b5c4f5
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012883"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Déployer les équipes Microsoft salles avec Exchange Online

Lisez cette rubrique pour plus d’informations sur la façon de déployer les salles d’équipes Microsoft avec Exchange Online et Skype pour Business Server local.
  
Si votre organisation possède un mélange de services, avec une poignée hébergés sur site et certaines hébergées en ligne, votre configuration dépendra où se trouve chaque service. Cette rubrique traite des déploiements hybrides pour les salles d’équipes Microsoft avec Exchange hébergé en ligne. Il existe de nombreuses différentes variantes dans ce type de déploiement, il n’est pas possible de fournir des instructions détaillées pour toutes les. Le processus suivant fonctionnera pour de nombreuses configurations. Si le processus n’est pas bon choix pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour atteindre le même résultat final, comme indiqué ici et pour d’autres options de déploiement.

Pour configurer des comptes d’utilisateurs, la plus simple consiste à configurer à l’aide de Windows PowerShell à distance. Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs locaux des équipes Microsoft compatibles. Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer les comptes utilisés par votre périphérique Microsoft équipes salles.

## <a name="requirements"></a>Configuration requise

Avant de déployer Microsoft équipes salles avec Exchange Online, assurez-vous que vous remplissez les conditions. Pour plus d’informations, consultez [Configuration requise de salles d’équipes Microsoft](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Pour déployer Microsoft équipes salles avec Exchange Online, procédez comme suit. Assurez-vous de disposer des autorisations adéquates pour exécuter les applets de commande associées.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Création d’un compte et définition des propriétés Exchange

1. Démarrer une session Windows PowerShell à distance sur un PC et se connecter à Exchange Online comme suit :

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. Après avoir établi une session, vous allez créer une nouvelle boîte aux lettres et activer comme un RoomMailboxAccount, soit modifier les paramètres d’une boîte aux lettres de salle existante. Ainsi, le compte d’authentification dans les salles d’équipes Microsoft.

   Si vous modifiez une boîte aux lettres de ressource :

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Si vous créez une nouvelle boîte aux lettres de ressources :

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Pour améliorer l’expérience de réunion, vous devez définir les propriétés Exchange sur le compte d’utilisateur comme suit :

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Vous devez vous connecter à Azure AD pour appliquer certains paramètres de compte. Pour vous connecter, vous pouvez exécuter l’applet de commande suivante.

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Ajout d’une adresse e-mail pour votre compte de domaine sur site

1. Dans l’outil **Active Directory utilisateurs et ordinateurs Active Directory** , avec le bouton droit sur le dossier ou l’unité d’organisation que vos salles d’équipes Microsoft comptes seront créés, cliquez sur **Nouveau**, puis cliquez sur **utilisateur**.
2. Saisissez le nom d’affichage de l’applet de commande précédente dans le champ **Nom complet** et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur**. Cliquez sur **Suivant**.
3. Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.

    > [!NOTE]
    > Sélection de **mot de passe n’expire jamais** est une condition requise pour Skype pour Business Server dans les salles d’équipes Microsoft. Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe. Dans ce cas, vous devez créer une exception pour chaque compte d’utilisateur locaux des équipes Microsoft.
  
4. Cliquez sur **Terminer** pour créer le compte.
5. Une fois le compte créé, exécutez une synchronisation de répertoire. À l’issue de cette opération, accédez à la page d’utilisateurs et vérifiez que les deux comptes créés lors des étapes précédentes sont fusionnés.

### <a name="assign-an-office-365-license"></a>Affectation d’une licence Office 365

1. Le compte d’utilisateur doit disposer d’une licence Office 365 valide pour vous assurer que Exchange et Skype pour Business Server fonctionnera. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’utilisateur ; cela permet de déterminer les SKU de licence disponibles pour votre compte.
2. Ensuite, utilisez`Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> pour récupérer une liste de références disponibles pour votre client Office 365.
3. Une fois que vous répertoriez les références, vous pouvez ajouter une licence à l’aide du`Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> applet de commande. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK). 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Activer le compte d’utilisateur avec Skype pour Business Server

1. Créez une session Windows PowerShell à distance à partir d’un PC comme suit :

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Pour activer votre compte Microsoft équipes salles pour Skype pour Business Server, exécutez cette commande :

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Si vous ne savez pas quelle valeur utiliser pour le paramètre RegistrarPool dans votre environnement, vous pouvez obtenir la valeur d’un Skype pour utilisateur Business Server à l’aide de cette commande existante

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Affecter un Skype licence Business Server à votre compte Microsoft équipes salles

1. Connectez-vous en tant qu’administrateur client, ouvrez le portail d’administration d’Office 365 et cliquez sur l’application d’administration.
2. Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.
3. Cliquez sur le compte de salles d’équipes Microsoft, puis cliquez sur l’icône du crayon pour modifier les informations de compte.
4. Cliquez sur **Licences**.
5. Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise. Vous devrez utiliser une licence 3 planifier si vous souhaitez utiliser Enterprise Voice dans les salles d’équipes Microsoft.
6. Cliquez sur **Enregistrer**.

Pour la validation, vous devez être en mesure d’utiliser n’importe quel Skype pour client d’entreprise pour vous connecter à ce compte.
  
## <a name="see-also"></a>Voir aussi

[Configurer des comptes pour les salles d’équipes Microsoft](room-systems-v2-configure-accounts.md)

[Planifier des équipes Microsoft salles](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Déployer les équipes Microsoft salles](room-systems-v2.md)
  
[Configurer une console Microsoft équipes salles](console.md)
  
[Gérer les équipes Microsoft salles](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
