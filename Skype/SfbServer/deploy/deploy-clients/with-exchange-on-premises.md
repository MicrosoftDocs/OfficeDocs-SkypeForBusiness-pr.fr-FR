---
title: Déploiement de Skype Room Systems v2 avec Exchange sur site
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: Lisez cette rubrique pour plus d’informations sur le déploiement de systèmes de salle Skype v2 dans un environnement hybride avec Exchange sur site.
ms.openlocfilehash: 49e0b85cc38de91ed269ca103ef995507a6d1e37
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699359"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a>Déploiement de Skype Room Systems v2 avec Exchange sur site
 
Lisez cette rubrique pour plus d’informations sur le déploiement de systèmes de salle Skype v2 dans un environnement hybride avec Exchange sur site et Skype pour Business Online.
  
Si votre organisation possède un mélange de services, avec une poignée hébergés sur site et certaines hébergées en ligne, votre configuration dépendra où se trouve chaque service. Cette rubrique traite des déploiements hybrides pour systèmes de salle Skype v2 avec Exchange hébergé sur site. Il existe de nombreuses différentes variantes dans ce type de déploiement, il n’est pas possible de fournir des instructions détaillées pour toutes les. Le processus suivant fonctionnera pour de nombreuses configurations. Si le processus n’est pas bon choix pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour atteindre le même résultat final, comme indiqué ici et pour d’autres options de déploiement. 

Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs v2 Skype salle systèmes compatibles. Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer les comptes utilisés par votre appareil v2 de systèmes de salle Skype.
  
## <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a>Déploiement de Skype Room Systems v2 avec Exchange sur site

Avant de déployer des systèmes de salle Skype v2 avec Exchange sur site, assurez-vous que vous remplissez les conditions. Pour plus d’informations, reportez-vous à la rubrique [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Si vous déployez des systèmes de salle Skype v2 avec Exchange sur site, vous utiliserez les outils d’administration Active Directory pour ajouter une adresse de messagerie pour votre compte de domaine local. Ce compte sera synchronisé avec Office 365. Vous devrez réaliser les opérations suivantes :
  
- Création d’un compte et synchronisation avec Active Directory
    
- Activation de la boîte aux lettres distante et définition des propriétés
    
- Attribuer une licence Office 365.
    
- Activez le compte de l’appareil avec Skype pour Business Server. Pour activer le compte d’appareil avec dans votre environnement, vous devez remplir les conditions préalables suivantes :
    
  - Vous devez avoir Skype pour Business Online (Plan 2) ou version ultérieure dans votre plan Office 365. Le plan doit prendre en charge la fonctionnalité de conférence.
    
  - Si vous avez besoin d’Enterprise Voice (téléphonie TLS) à l’aide de fournisseurs de services de téléphonie pour les systèmes de salle Skype v2 vous devez Skype pour Business Online (Plan 3).
    
  - Les utilisateurs de client doivent avoir des boîtes aux lettres Exchange.
    
  - Votre compte v2 de systèmes de salle Skype requiert Skype pour Business Online (Plan 2) ni Skype licence entreprise Online (Plan 3), mais il ne nécessite pas une licence Exchange Online.
    
- Affecter un Skype licence Business Server à votre compte de v2 Skype salle systèmes.
    
### <a name="create-an-account-and-synchronize-with-active-directory"></a>Création d’un compte et synchronisation avec Active Directory

1. Dans l’outil **Active Directory utilisateurs et ordinateurs Active Directory** , avec le bouton droit sur le dossier ou l’unité d’organisation que vos systèmes de salle Skype v2 comptes seront créés, cliquez sur **Nouveau**, puis cliquez sur **utilisateur**.
    
2. Saisissez le nom d’affichage de l’applet de commande précédente dans le champ **Nom complet** et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur**. Cliquez sur **Suivant**.
    
3. Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.
    
    > [!NOTE]
    > Sélection de **mot de passe n’expire jamais** est une condition requise pour Skype pour Business Server sur les systèmes de salle Skype v2. Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe. Dans ce cas, vous devez créer une exception pour chaque compte de périphérique Skype salle systèmes v2.
  
4. Une fois le compte créé, exécutez une synchronisation de répertoire. Lorsqu’elle est terminée, accédez à la page utilisateurs dans votre centre d’administration d’Office 365 et vérifiez que le compte créé lors des étapes précédentes a fusionné à en ligne.
    
### <a name="enable-the-remote-mailbox-and-set-properties"></a>Activation de la boîte aux lettres distante et définition des propriétés

1. Activer la boîte aux lettres distante en ouvrant votre shell de gestion Exchange sur site avec des autorisations d’administrateur et exécutez la commande suivante :
     
   ```
   Enable-Mailbox 'PROJECTRIGEL01@contoso.com' -Room
   ```

2. Démarrer une session Windows PowerShell à distance et se connecter à Microsoft Exchange. À partir de votre client Office 365, exécutez les commandes suivantes :
    
   ```
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess = New-PSSession -ConfigurationName Microsoft.Exchange -Credential $cred -AllowRedirection -Authentication Basic -ConnectionUri "https://<ExchangeServerFQDN>/PowerShell"
   Import-PSSession $sess
   ```

3. Pour améliorer l’expérience de réunion, vous devez définir les propriétés Exchange sur le compte de l’appareil comme suit :
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false 
   -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Skype Meeting room!'
   ```
    Pour plus d’informations sur les propriétés, vous devez définir, voir les propriétés Exchange.
    
4. Vous devrez vous connecter à Azure AD pour appliquer certains paramètres de compte. Pour vous connecter, vous pouvez exécuter la commande suivante :
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="assign-an-office-365-license"></a>Affectation d’une licence Office 365

1. Le compte de l’appareil doit avoir une licence Office 365 pour vous assurer que Exchange et Skype pour Business Server fonctionnera. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte.
    
2. Ensuite, utilisez Get-MsolAccountSku pour récupérer une liste de références disponibles pour votre client Office 365.
    
3. Une fois la liste obtenue, vous pouvez ajouter une licence à l’aide de l’applet de commande Set-MsolUserLicense. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-device-account-with-skype-for-business"></a>Activation du compte de l’appareil avec Skype Entreprise

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

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a>Affectation d’une licence Skype Entreprise à votre compte Skype Room Systems v2

1. Connectez-vous en tant qu’administrateur client, ouvrez le portail d’administration d’Office 365 et cliquez sur l’application d’administration.
    
2. Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.
    
3. Cliquez sur le compte de v2 Skype salle systèmes, puis cliquez sur l’icône du crayon pour modifier les informations de compte.
    
4. Cliquez sur **Licences**.
    
5. Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise. Vous devrez utiliser une licence 3 planifier si vous souhaitez utiliser Enterprise Voice sur votre v2 Skype salle systèmes.
    
6. Cliquez sur **Enregistrer**.
    
Pour la validation, vous devez être en mesure d’utiliser n’importe quel Skype pour client d’entreprise pour vous connecter à ce compte.
  
## <a name="see-also"></a>Voir aussi

[Configurer des comptes pour les systèmes de salle Skype v2](room-systems-v2-configure-accounts.md)

[Plan for Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Déploiement de Skype Room System v2](room-systems-v2.md)
  
[Configuration d’une console Skype Room Systems v2](console.md)
  
[Gestion de Skype Room System v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

