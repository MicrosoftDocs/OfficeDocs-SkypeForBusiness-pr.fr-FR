---
title: Déploiement de Skype Room Systems v2 avec Exchange Online
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
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lisez cette rubrique pour plus d’informations sur le déploiement de systèmes de salle Skype v2 avec Exchange Online.
ms.openlocfilehash: 0581834666476f2635785a48b189396c9240ac8f
ms.sourcegitcommit: e53749714dcde9f7b184d5ef554bffbc77f54267
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2019
ms.locfileid: "28729385"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online"></a>Déploiement de Skype Room Systems v2 avec Exchange Online 
 
Lisez cette rubrique pour plus d’informations sur la façon de déployer v2 de systèmes de salle Skype avec Exchange Online et Skype pour Business Server local.
  
Si votre organisation possède un mélange de services, avec une poignée hébergés sur site et certaines hébergées en ligne, votre configuration dépendra où se trouve chaque service. Cette rubrique traite des déploiements hybrides pour systèmes de salle Skype v2 avec Exchange hébergé en ligne. Il existe de nombreuses différentes variantes dans ce type de déploiement, il n’est pas possible de fournir des instructions détaillées pour toutes les. Le processus suivant fonctionnera pour de nombreuses configurations. Si le processus n’est pas bon choix pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour atteindre le même résultat final, comme indiqué ici et pour d’autres options de déploiement. 

Pour configurer des comptes d’utilisateurs, la plus simple consiste à configurer à l’aide de Windows PowerShell à distance. Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs v2 Skype salle systèmes compatibles. Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer les comptes utilisés par votre appareil v2 de systèmes de salle Skype.


  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a>Déploiement de Skype Room Systems v2 avec Exchange Online

Avant de déployer des systèmes de salle Skype v2 avec Exchange Online, assurez-vous que vous remplissez les conditions. Pour plus d’informations, reportez-vous à la rubrique [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Pour déployer des systèmes de salle Skype v2 avec Exchange Online, procédez comme suit. Assurez-vous de disposer des autorisations adéquates pour exécuter les applets de commande associées. 
  
### <a name="create-an-account-and-set-exchange-properties"></a>Création d’un compte et définition des propriétés Exchange

1. Démarrer une session Windows PowerShell à distance sur un PC et se connecter à Exchange Online comme suit :
    
```
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. Après avoir établi une session, vous allez créer une nouvelle boîte aux lettres et activer comme un RoomMailboxAccount, soit modifier les paramètres d’une boîte aux lettres de salle existante. Ainsi, le compte de s’authentifier sur des systèmes de salle Skype v2.
    
   Si vous modifiez une boîte aux lettres de ressource :
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Si vous créez une nouvelle boîte aux lettres de ressources :
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Pour améliorer l’expérience de réunion, vous devez définir les propriétés Exchange sur le compte d’utilisateur comme suit :
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

    
4. Vous devez vous connecter à Azure AD pour appliquer certains paramètres de compte. Pour vous connecter, vous pouvez exécuter l’applet de commande suivante.
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Ajout d’une adresse e-mail pour votre compte de domaine sur site

1. Dans l’outil **Active Directory utilisateurs et ordinateurs Active Directory** , avec le bouton droit sur le dossier ou l’unité d’organisation que vos systèmes de salle Skype v2 comptes seront créés, cliquez sur **Nouveau**, puis cliquez sur **utilisateur**.
    
2. Saisissez le nom d’affichage de l’applet de commande précédente dans le champ **Nom complet** et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur**. Cliquez sur **Suivant**.


3. Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.
    
    > [!NOTE]
    > Sélection de **mot de passe n’expire jamais** est une condition requise pour Skype pour Business Server sur les systèmes de salle Skype v2. Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe. Dans ce cas, vous devez créer une exception pour chaque compte d’utilisateur Skype salle systèmes v2.
  
4. Cliquez sur **Terminer** pour créer le compte.
    
5. Une fois le compte créé, exécutez une synchronisation de répertoire. À l’issue de cette opération, accédez à la page d’utilisateurs et vérifiez que les deux comptes créés lors des étapes précédentes sont fusionnés.
    
### <a name="assign-an-office-365-license"></a>Affectation d’une licence Office 365

1. Le compte d’utilisateur doit disposer d’une licence Office 365 valide pour vous assurer que Exchange et Skype pour Business Server fonctionnera. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’utilisateur ; cela permet de déterminer les SKU de licence disponibles pour votre compte.
    
2. Ensuite, utilisez Get-MsolAccountSku pour récupérer une liste de références disponibles pour votre client Office 365.
    
3. Une fois la liste obtenue, vous pouvez ajouter une licence à l’aide de l’applet de commande Set-MsolUserLicense. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```


### <a name="enable-the-user-account-with-skype-for-business-server"></a>Activer le compte d’utilisateur avec Skype pour Business Server

1. Créez une session Windows PowerShell à distance à partir d’un PC comme suit :
    
    ```
    Import-Module LyncOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Pour activer votre compte v2 de systèmes de salle Skype pour Skype pour Business Server, exécutez cette commande :
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Si vous ne savez pas quelle valeur utiliser pour le paramètre RegistrarPool dans votre environnement, vous pouvez obtenir la valeur d’un Skype pour utilisateur Business Server à l’aide de cette commande existante
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-skype-room-systems-v2-account"></a>Affecter un Skype licence Business Server à votre compte v2 de systèmes de salle Skype

1. Connectez-vous en tant qu’administrateur client, ouvrez le portail d’administration d’Office 365 et cliquez sur l’application d’administration.
    
2. Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.
    
3. Cliquez sur le compte de v2 Skype salle systèmes, puis cliquez sur l’icône du crayon pour modifier les informations de compte.
    
4. Cliquez sur **Licences**.
    
5. Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise. Vous devrez utiliser une licence 3 planifier si vous souhaitez utiliser Enterprise Voice sur votre v2 Skype salle systèmes.
    
6. Cliquez sur **Enregistrer**.
    
Pour la validation, vous devez être en mesure d’utiliser n’importe quel Skype pour client d’entreprise pour vous connecter à ce compte.
  
## <a name="see-also"></a>Voir aussi

[Configurer des comptes pour les systèmes de salle Skype v2](room-systems-v2-configure-accounts.md)

[Planification de Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Déploiement des systèmes Skype Room version 2](room-systems-v2.md)
  
[Configuration d’une console pour les systèmes Skype Room version 2](console.md)
  
[Gestion des systèmes Skype Room version 2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

