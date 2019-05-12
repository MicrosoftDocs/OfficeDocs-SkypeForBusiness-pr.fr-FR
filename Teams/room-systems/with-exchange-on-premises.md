---
title: Déployer Microsoft équipes salles avec Exchange sur site
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: Lisez cette rubrique pour plus d’informations sur le déploiement des salles d’équipes Microsoft dans un environnement hybride avec Exchange sur site.
ms.openlocfilehash: 1c1dd5ad49cedb2aee41b036f71bbc6b840aed96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33916210"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Déployer Microsoft équipes salles avec Exchange sur site

Lisez cette rubrique pour plus d’informations sur le déploiement des salles d’équipes Microsoft dans un environnement hybride avec Exchange sur site et Microsoft Teams ou Skype pour Business Online.
  
Si votre organisation possède un mélange de services, avec une poignée hébergés sur site et certaines hébergées en ligne, votre configuration dépendra où se trouve chaque service. Cette rubrique traite des déploiements hybrides pour les salles d’équipes Microsoft avec Exchange hébergé sur site. Il existe de nombreuses différentes variantes dans ce type de déploiement, il n’est pas possible de fournir des instructions détaillées pour toutes les. Le processus suivant fonctionnera pour de nombreuses configurations. Si le processus n’est pas bon choix pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour atteindre le même résultat final, comme indiqué ici et pour d’autres options de déploiement.

Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs locaux des équipes Microsoft compatibles. Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer les comptes utilisés par votre périphérique Microsoft équipes salles.
  
## <a name="requirements"></a>Configuration requise

Avant de déployer Microsoft équipes salles avec Exchange sur site, assurez-vous que vous remplissez les conditions. Pour plus d’informations, consultez [Configuration requise de salles d’équipes Microsoft](requirements.md).
  
Si vous déployez Microsoft équipes salles avec Exchange sur site, vous utiliserez les outils d’administration Active Directory pour ajouter une adresse de messagerie pour votre compte de domaine local. Ce compte sera synchronisé avec Office 365. Vous devrez réaliser les opérations suivantes :
  
- Création d’un compte et synchronisation avec Active Directory

- Activation de la boîte aux lettres distante et définition des propriétés

- Attribuer une licence Office 365.

- Activez le compte de l’appareil avec Skype pour Business Server. Pour activer le compte d’appareil avec dans votre environnement, vous devez remplir les conditions préalables suivantes :

  - Vous devez avoir Skype pour Business Online (Plan 2) ou version ultérieure dans votre plan Office 365. Le plan doit prendre en charge la fonctionnalité de conférence.
  
  - - Si vous avez besoin d’Enterprise Voice (téléphonie TLS) à l’aide de fournisseurs de services de téléphonie pour les salles d’équipes Microsoft vous devez Skype pour Business Online (Plan 3).
  
  - - Les utilisateurs de client doivent avoir des boîtes aux lettres Exchange.
  
  - - Votre compte Microsoft équipes salles requiert Skype pour Business Online (Plan 2) ni Skype licence entreprise Online (Plan 3), mais il ne requiert pas de licence Exchange Online.

- Affecter un Skype licence Business Server à votre compte Microsoft équipes salles.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Création d’un compte et synchronisation avec Active Directory

1. Dans l’outil **utilisateurs et ordinateurs** , avec le bouton droit sur le dossier ou l’unité d’organisation que vos salles d’équipes Microsoft comptes seront créés, cliquez sur **Nouveau**, puis cliquez sur **utilisateur**.

2. Saisissez le nom d’affichage de l’applet de commande précédente dans le champ **Nom complet** et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur**. Cliquez sur **Suivant**.

3. Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.

    > [!NOTE]
    > Sélection de **mot de passe n’expire jamais** est une condition requise pour Skype pour Business Server dans les salles d’équipes Microsoft. Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe. Dans ce cas, vous devez créer une exception pour chaque compte de périphérique salles d’équipes Microsoft.
  
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

1. Se connecter à Azure Active Directory. Pour plus d’informations sur Active Directory, voir [Azure Active Directory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) n’est pas pris en charge. 

2. Le compte de l’appareil doit avoir une licence Office 365 ou Exchange et Microsoft Teams ne fonctionnent pas. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte. Vous pouvez utiliser`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> pour récupérer une liste de références disponibles.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Ensuite, vous pouvez ajouter une licence à l’aide du`Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> applet de commande. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   Pour obtenir des instructions détaillées, consultez la rubrique [attribution de licences pour les comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="enable-the-device-account"></a>Activer le compte de l’appareil

Skype pour Business Online PowerShell est utilisé pour gérer les services Microsoft Teams et Skype pour Business Online.

1. Créez une session Windows PowerShell à distance à partir d’un PC comme suit :

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Pour activer votre compte Microsoft équipes salles, exécutez cette commande :

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Si vous ne savez pas quelle valeur utiliser pour le paramètre RegistrarPool dans votre environnement, vous pouvez obtenir la valeur d’un utilisateur existant à l’aide de cette commande :

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Attribuer une licence à votre compte Microsoft équipes salles

1. Connectez-vous en tant qu’administrateur client, ouvrez le portail d’administration d’Office 365 et cliquez sur l’application d’administration.
2. Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.
3. Cliquez sur le compte de salles d’équipes Microsoft, puis cliquez sur l’icône du crayon pour modifier les informations de compte.
4. Cliquez sur **Licences**.
5. Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise. Vous devrez utiliser une licence 3 planifier si vous souhaitez utiliser Enterprise Voice sur vos salles d’équipes Microsoft.
6. Cliquez sur **Enregistrer**.

Pour la validation, vous devez être en mesure d’utiliser n’importe quel client pour vous connecter à ce compte.
  
## <a name="see-also"></a>Voir aussi

[Configurer des comptes pour les salles d’équipes Microsoft](room-systems-v2-configure-accounts.md)

[Planifier des équipes Microsoft salles](skype-room-systems-v2-0.md)
  
[Déployer les équipes Microsoft salles](room-systems-v2.md)
  
[Configurer une console Microsoft équipes salles](console.md)
  
[Gérer Microsoft Teams Rooms](skype-room-systems-v2.md)
