---
title: Déployer Salles Microsoft Teams avec Exchange local
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Lisez cette rubrique pour plus d’informations sur le déploiement d Salles Microsoft Teams dans un environnement hybride avec des Exchange en local.
ms.openlocfilehash: 96d8a49cd75e3413739d36a3c86a91daa72b22e6
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909535"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Déployer Salles Microsoft Teams avec Exchange local

Lisez cette rubrique pour plus d’informations sur la façon de déployer des Salles Microsoft Teams dans un environnement hybride avec des Exchange locaux et Microsoft Teams.
  
Si votre organisation dispose d’un mélange de services, dont certains sont hébergés en local et d’autres hébergés en ligne, votre configuration dépend de l’endroit où chaque service est hébergé. Cette rubrique traite des déploiements hybrides Salles Microsoft Teams avec Exchange sur site. Ce type de déploiement étant très différent, il n’est pas possible de fournir des instructions détaillées pour l’ensemble d’entre eux. Le processus suivant fonctionne pour de nombreuses configurations. Si le processus n’est pas configuré pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour obtenir le même résultat final que celui documenté ici, ainsi que pour d’autres options de déploiement.

Microsoft fournit [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer de nouveaux comptes d’utilisateurs, ou à valider les comptes de ressources existants que vous avez pour vous aider à les transformer en comptes d’utilisateurs Salles Microsoft Teams compatibles. Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer des comptes que votre Salles Microsoft Teams appareil utilisera.
  
## <a name="requirements"></a>Conditions requises

Avant de déployer Salles Microsoft Teams avec Exchange local, assurez-vous que vous avez satisfait aux exigences. Pour plus d’informations, [voir Salles Microsoft Teams requise.](requirements.md)
  
Si vous déployez Salles Microsoft Teams avec Exchange local, vous utiliserez les outils d’administration Active Directory pour ajouter une adresse de courrier pour votre compte de domaine local. Ce compte sera synchronisé avec les Microsoft 365 ou Office 365. Vous devrez réaliser les opérations suivantes :
  
- Créez un compte et synchronisez-le avec Azure Active Directory.

- Activation de la boîte aux lettres distante et définition des propriétés

- Affectez une Microsoft 365 ou une Office 365 licence.

### <a name="create-an-account-and-synchronize-with-azure-active-directory"></a>Créer un compte et le synchroniser avec Azure Active Directory

1. Dans l’outil Utilisateurs et ordinateurs **Active Directory,** cliquez avec le bouton droit sur le dossier ou l’unité de l’organisation dans qui vos comptes Salles Microsoft Teams seront créés, cliquez sur **Nouveau,** puis sur **Utilisateur.**

2. Tapez le nom complet dans la **zone Nom complet** et l’alias dans la zone Nom de **l’utilisateur.** Cliquez sur **Suivant**.

3. Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.

    > [!NOTE]
    > La sélection **du mot de passe n’expire** jamais est une obligation pour Salles Microsoft Teams. Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe. Si c’est le cas, vous devez créer une exception pour Salles Microsoft Teams compte d’appareil.
  
4. Une fois le compte créé, exécutez une synchronisation de répertoire. Une fois l’étape terminée, allez dans la page utilisateurs de votre Centre d'administration Microsoft 365 et vérifiez que le compte créé lors des étapes précédentes a été fusionné sur en ligne.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Activation de la boîte aux lettres distante et définition des propriétés

1. [Ouvrez le Exchange Management Shell ou](/powershell/exchange/exchange-server/open-the-exchange-management-shell) connectez-vous à votre serveur Exchange à [l’aide de Remote PowerShell.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. Dans Exchange PowerShell, créez une boîte aux lettres pour le compte (activez ce compte) en exécutant la commande suivante :

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Pour plus d’informations sur la syntaxe et les paramètres, voir [Enable-Mailbox.](/powershell/module/exchange/mailboxes/enable-mailbox)

3. Dans Exchange PowerShell, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’expérience de réunion :

   - AutomateProcessing :accept automatique (les organisateurs de réunion reçoivent directement la décision de réservation de salle sans intervention humaine : libre = accepter ; occupé = refus.)

   - AddOrganizerToSubject: $false (L’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion.)

   - DeleteComments : $false (conservez tout texte dans le corps du message des demandes de réunion entrantes).)

   - SuppressionSubject : $false (conserver l’objet des demandes de réunion entrantes).)

   - RemovePrivateProperty : $false (garantit que l’indicateur privé envoyé par l’organisateur de la réunion dans la demande de réunion d’origine reste tel que spécifié.)

   - AddAdditionalResponse: $true (Le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)

   - Réponse supplémentaire : « Il s’agit d’Microsoft Teams salle de réunion ! » (Texte supplémentaire à ajouter à la demande de réunion.

   Cet exemple configure ces paramètres sur la boîte aux lettres de salle Project-Rigel-01.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Pour plus d’informations sur la syntaxe et les paramètres, [voir Set-CalendarProcessing.](/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Affecter une licence Microsoft 365 licence Office 365 licence

1. Connecter à Azure Active Directory. Pour plus d’Azure Active Directory, voir [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0 n’est](/powershell/azure/active-directory/overview?view=azureadps-2.0) pas pris en charge. 

2. Le compte de l’appareil doit avoir une licence Microsoft 365 ou Office 365 licence valide, ou Exchange et Microsoft Teams ne fonctionneront pas. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte. Vous pouvez utiliser `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> pour récupérer la liste des S SKUs disponibles.

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

   Pour obtenir des instructions détaillées, voir Attribuer des licences à des comptes [d’utilisateurs Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

Pour validation, vous pouvez utiliser n’importe quel client pour vous connecter à ce compte.
  
## <a name="related-topics"></a>Sujets associés

[Configurer des comptes pour Salles Microsoft Teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)
