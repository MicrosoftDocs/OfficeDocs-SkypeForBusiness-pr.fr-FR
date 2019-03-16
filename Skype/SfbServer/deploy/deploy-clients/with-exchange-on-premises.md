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
ms.openlocfilehash: a804ba6b1210efae8ed36630180f14ad367cb955
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2019
ms.locfileid: "30645415"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a>Déploiement de Skype Room Systems v2 avec Exchange sur site

Lisez cette rubrique pour plus d’informations sur le déploiement de systèmes de salle Skype v2 dans un environnement hybride avec Exchange sur site et Skype pour Business Online.
  
Si votre organisation possède un mélange de services, avec une poignée hébergés sur site et certaines hébergées en ligne, votre configuration dépendra où se trouve chaque service. Cette rubrique traite des déploiements hybrides pour systèmes de salle Skype v2 avec Exchange hébergé sur site. Il existe de nombreuses différentes variantes dans ce type de déploiement, il n’est pas possible de fournir des instructions détaillées pour toutes les. Le processus suivant fonctionnera pour de nombreuses configurations. Si le processus n’est pas bon choix pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour atteindre le même résultat final, comme indiqué ici et pour d’autres options de déploiement.

Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs v2 Skype salle systèmes compatibles. Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer les comptes utilisés par votre appareil v2 de systèmes de salle Skype.
  
## <a name="requirements"></a>Configuration requise

Avant de déployer des systèmes de salle Skype v2 avec Exchange sur site, assurez-vous que vous remplissez les conditions. Pour plus d’informations, reportez-vous à la rubrique [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Si vous déployez des systèmes de salle Skype v2 avec Exchange sur site, vous utiliserez les outils d’administration Active Directory pour ajouter une adresse de messagerie pour votre compte de domaine local. Ce compte sera synchronisé avec Office 365. Vous devrez réaliser les opérations suivantes :
  
- Création d’un compte et synchronisation avec Active Directory

- Activation de la boîte aux lettres distante et définition des propriétés

- Attribuer une licence Office 365.

- Activez le compte de l’appareil avec Skype pour Business Server. Pour activer le compte d’appareil avec dans votre environnement, vous devez remplir les conditions préalables suivantes :

  - Vous devez avoir Skype pour Business Online (Plan 2) ou version ultérieure dans votre plan Office 365. Le plan doit prendre en charge la fonctionnalité de conférence.
  
  - - Si vous avez besoin d’Enterprise Voice (téléphonie TLS) à l’aide de fournisseurs de services de téléphonie pour les systèmes de salle Skype v2 vous devez Skype pour Business Online (Plan 3).
  
  - - Les utilisateurs de client doivent avoir des boîtes aux lettres Exchange.
  
  - - Votre compte v2 de systèmes de salle Skype requiert Skype pour Business Online (Plan 2) ni Skype licence entreprise Online (Plan 3), mais il ne nécessite pas une licence Exchange Online.

- Affecter un Skype licence Business Server à votre compte de v2 Skype salle systèmes.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Création d’un compte et synchronisation avec Active Directory

1. Dans l’outil **Active Directory utilisateurs et ordinateurs Active Directory** , avec le bouton droit sur le dossier ou l’unité d’organisation que vos systèmes de salle Skype v2 comptes seront créés, cliquez sur **Nouveau**, puis cliquez sur **utilisateur**.

2. Saisissez le nom d’affichage de l’applet de commande précédente dans le champ **Nom complet** et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur**. Cliquez sur **Suivant**.

3. Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.

    > [!NOTE]
    > Sélection de **mot de passe n’expire jamais** est une condition requise pour Skype pour Business Server sur les systèmes de salle Skype v2. Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe. Dans ce cas, vous devez créer une exception pour chaque compte de périphérique Skype salle systèmes v2.
  
4. Une fois le compte créé, exécutez une synchronisation de répertoire. Lorsqu’elle est terminée, accédez à la page utilisateurs dans votre centre d’administration d’Office 365 et vérifiez que le compte créé lors des étapes précédentes a fusionné à en ligne.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Activation de la boîte aux lettres distante et définition des propriétés

1. [Ouvrez Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [vous connecter à votre serveur Exchange à l’aide de PowerShell à distance](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

2. Dans Exchange PowerShell, créer une boîte aux lettres pour le compte de (boîte aux lettres activer le compte) en exécutant la commande suivante :

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Pour détaillées sur la syntaxe et les informations sur les paramètres, consultez la rubrique [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).

3. Dans Exchange PowerShell, configurez les paramètres suivants dans la boîte aux lettres de salle pour améliorer l’expérience de réunion :

   - AutomateProcessing : AutoAccept (organisateurs de réunion recevoir la décision de réservation de salles directement sans intervention humaine : libre = accepter ; occupé = refuser.)

   - AddOrganizerToSubject : $false (l’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion).

   - DeleteComments : $false (conserver le texte dans le corps du message de demandes de réunion entrantes).

   - DeleteSubject : $false (conserver l’objet de demandes de réunion entrantes).

   - RemovePrivateProperty : $false (garantit la demande de l’indicateur privé qui a été envoyé par l’organisateur de la réunion d’origine reste comme indiqué).

   - AddAdditionalResponse : $true (le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion).

   - AdditionalResponse : « Ceci est une salle de réunion Skype ! » (Texte supplémentaire à ajouter à la demande de réunion.)

   Cet exemple configure ces paramètres dans la boîte aux lettres de salle nommé Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Pour détaillées sur la syntaxe et les informations sur les paramètres, voir [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-an-office-365-license"></a>Affectation d’une licence Office 365

1. Se connecter à Active Directory Azure PowerShell. Pour obtenir des instructions, consultez la rubrique [Connect avec Azure Active Directory PowerShell pour le module de graphique](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)

2. Le compte de l’appareil doit avoir une licence Office 365 ou Exchange et Skype pour les entreprises ne fonctionnent pas. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte. Vous pouvez utiliser Get-AzureADSubscribedSku pour récupérer une liste de références disponibles pour votre client Office 365 comme suit :

   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```

   Ensuite, vous pouvez ajouter une licence à l’aide de l’applet de commande Set-AzureADUserLicense. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).

   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

   Pour obtenir des instructions détaillées, consultez la rubrique [attribution de licences pour les comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="enable-the-device-account-with-skype-for-business"></a>Activation du compte de l’appareil avec Skype Entreprise

1. Créez une session Windows PowerShell à distance à partir d’un PC comme suit :

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Pour activer votre compte v2 de systèmes de salle Skype pour Skype pour Business Server, exécutez cette commande :

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Si vous ne savez pas quelle valeur utiliser pour le paramètre RegistrarPool dans votre environnement, vous pouvez obtenir la valeur d’un Skype pour utilisateur Business Server à l’aide de cette commande existante

   ``` Powershell
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

[Planification de Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Déploiement des systèmes Skype Room version 2](room-systems-v2.md)
  
[Configuration d’une console pour les systèmes Skype Room version 2](console.md)
  
[Gestion des systèmes Skype Room version 2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)