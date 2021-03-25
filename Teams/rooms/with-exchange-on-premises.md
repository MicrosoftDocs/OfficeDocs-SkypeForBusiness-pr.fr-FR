---
title: Déployer des salles Microsoft Teams avec Exchange sur site
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Lisez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft Teams dans un environnement hybride avec Exchange en local.
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117352"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Déployer des salles Microsoft Teams avec Exchange en local

Lisez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft Teams dans un environnement hybride avec Exchange en local et Microsoft Teams ou Skype Entreprise Online.
  
Si votre organisation dispose d’un mélange de services, dont certains sont hébergés en local et d’autres hébergés en ligne, votre configuration dépend de l’endroit où chaque service est hébergé. Cette rubrique traite des déploiements hybrides de salles Microsoft Teams avec Exchange hébergé en local. Ce type de déploiement étant très différent, il n’est pas possible de fournir des instructions détaillées pour l’ensemble d’entre eux. Le processus suivant fonctionne pour de nombreuses configurations. Si le processus n’est pas configuré pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour obtenir le même résultat final que celui documenté ici, ainsi que pour d’autres options de déploiement.

Microsoft fournit [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aidera à créer de nouveaux comptes d’utilisateurs, ou à valider les comptes de ressources existants que vous avez afin de vous aider à les transformer en comptes d’utilisateurs de salles Microsoft Teams compatibles. Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer des comptes que votre appareil Microsoft Teams Rooms utilisera.
  
## <a name="requirements"></a>Conditions requises

Avant de déployer des salles Microsoft Teams avec Exchange en local, assurez-vous que vous avez répondu à la exigences. Pour plus d’informations, consultez [la conditions requises pour les salles Microsoft Teams.](requirements.md)
  
Si vous déployez des salles Microsoft Teams avec Exchange en local, vous utiliserez les outils d’administration Active Directory pour ajouter une adresse de messagerie pour votre compte de domaine local. Ce compte sera synchronisé avec Microsoft 365 ou Office 365. Vous devrez réaliser les opérations suivantes :
  
- Création d’un compte et synchronisation avec Active Directory

- Activation de la boîte aux lettres distante et définition des propriétés

- Attribuer une licence Microsoft 365 ou Office 365.

- Activez le compte d’appareil avec Skype Entreprise Server. Pour activer le compte d’appareil avec dans votre environnement, vous devez remplir les conditions préalables suivantes :

  - Vous devez avoir Skype Entreprise Online (plan 2) ou une version supérieure dans votre offre Microsoft 365 ou Office 365. Le plan doit prendre en charge la fonctionnalité de conférence.
  
  - Si vous avez besoin Voix Entreprise (téléphonie PSTN) en utilisant des fournisseurs de services téléphoniques pour les salles Microsoft Teams, vous avez besoin de Skype Entreprise Online (plan 3).

  - Lors de la configuration d’un compte de salle avec Microsoft Teams ou Skype Entreprise Online, le numéro de téléphone doit être affecté avant que le compte soit activé en tant que compte de salle.
  
  - Vos utilisateurs clients doivent avoir une boîte aux lettres Exchange.
  
  - Votre compte Salles Microsoft Teams ne nécessite pas de licence Skype Entreprise Online (plan 2) ou Skype Entreprise Online (plan 3), mais pas de licence Exchange Online.

- Affectez une licence Skype Entreprise Server à votre compte Salles Microsoft Teams.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Création d’un compte et synchronisation avec Active Directory

1. Dans l’outil Utilisateurs et ordinateurs **Active Directory,** cliquez avec le bouton droit sur le dossier ou l’unité de l’organisation dans qui vos comptes Salles Microsoft Teams seront créés, cliquez sur **Nouveau,** puis sur **Utilisateur.**

2. Saisissez le nom d’affichage de l’applet de commande précédente dans le champ **Nom complet** et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur**. Cliquez sur **Suivant**.

3. Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.

    > [!NOTE]
    > La sélection **du mot de passe n’expire** jamais est obligatoire pour Skype Entreprise Server sur les salles Microsoft Teams. Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe. Si c’est le cas, vous devez créer une exception pour chaque compte d’appareil Microsoft Teams Rooms.
  
4. Une fois le compte créé, exécutez une synchronisation de répertoire. Une fois l’étape terminée, dans la page utilisateurs de votre Centre d’administration Microsoft 365, vérifiez que le compte créé lors des étapes précédentes a été fusionné en ligne.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Activation de la boîte aux lettres distante et définition des propriétés

1. [Ouvrez Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [connectez-vous à votre serveur Exchange à l’aide de Remote PowerShell.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. Dans Exchange PowerShell, créez une boîte aux lettres pour le compte (activez-le avec la boîte aux lettres) en exécutant la commande suivante :

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Pour plus d’informations sur la syntaxe et les paramètres, [voir Enable-Mailbox.](/powershell/module/exchange/mailboxes/enable-mailbox)

3. Dans Exchange PowerShell, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’expérience de réunion :

   - AutomateProcessing :accept automatique (les organisateurs de réunion reçoivent directement la décision de réservation de salle sans intervention humaine : libre = accepter ; occupé = refus.)

   - AddOrganizerToSubject: $false (L’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion.)

   - DeleteComments : $false (conservez tout texte dans le corps du message des demandes de réunion entrantes).)

   - SuppressionSubject : $false (conserver l’objet des demandes de réunion entrantes).)

   - RemovePrivateProperty : $false (garantit que l’indicateur privé envoyé par l’organisateur de la réunion dans la demande de réunion d’origine reste tel que spécifié.)

   - AddAdditionalResponse: $true (Le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)

   - Réponse supplémentaire : « Il s’agit d’une salle de réunion Skype ! » (Le texte supplémentaire à ajouter à la demande de réunion.)

   Cet exemple configure ces paramètres sur la boîte aux lettres de salle project-Rigel-01.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Pour plus d’informations sur la syntaxe et les paramètres, [voir Set-CalendarProcessing.](/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Attribuer une licence Microsoft 365 ou Office 365

1. Connectez-vous à Azure Active Directory. Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0 n’est](/powershell/azure/active-directory/overview?view=azureadps-2.0) pas pris en charge. 

2. Le compte d’appareil doit avoir une licence Microsoft 365 ou Office 365 valide, sinon Exchange et Microsoft Teams ne fonctionneront pas. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte. Vous pouvez utiliser `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> pour récupérer la liste des S SKUs disponibles.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Ensuite, vous pouvez ajouter une licence à l’aide du `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).

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

   Pour obtenir des instructions détaillées, voir Attribuer des licences à des comptes d’utilisateurs [avec PowerShell Office 365.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="enable-the-device-account"></a>Activer le compte d’appareil

Skype Entreprise Online PowerShell est utilisé pour gérer les services pour Microsoft Teams et Skype Entreprise Online.

1. Créez une session Windows PowerShell distance à partir d’un PC comme suit :
> [!NOTE]
> Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.
>
> Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. Obtenez l’adresse SIP du compte :

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. **Facultatif**. Si vous voulez attribuer un numéro de téléphone au compte, l’opération doit être effectuée à ce stade. Si vous souhaitez affecter un numéro de téléphone de routage direct :

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    Si vous affectez un numéro de téléphone fourni par Microsoft, utilisez l’cmdlet ci-dessous après avoir fourni à l’utilisateur une licence forfait d’appels :
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. Pour activer votre compte Salles Microsoft Teams, exécutez la commande ci-après :

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Si vous n’êtes pas certain de la valeur à utiliser pour le paramètre RegistrarPool dans votre environnement, vous pouvez obtenir la valeur auprès d’un utilisateur existant à l’aide de la commande ci-après :

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Attribuer une licence à votre compte Salles Microsoft Teams

1. Connectez-vous en tant qu’administrateur client, ouvrez le Centre d’administration Microsoft 365, puis cliquez sur l’application Administrateur.
2. Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.
3. Cliquez sur le compte Salles Microsoft Teams, puis sur l’icône de stylet pour modifier les informations sur le compte.
4. Cliquez sur **Licences**.
5. Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise. Vous devez utiliser une licence Plan 3 si vous souhaitez utiliser des Voix Entreprise dans vos salles Microsoft Teams.
6. Cliquez sur **Enregistrer**.

Pour validation, vous pouvez utiliser n’importe quel client pour vous connecter à ce compte.
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer des comptes pour les salles Microsoft Teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)