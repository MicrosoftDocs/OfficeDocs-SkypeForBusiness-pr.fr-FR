---
title: Déployer des Salles Microsoft Teams avec Exchange Online
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lisez cette rubrique pour plus d’informations sur la façon de déployer des Salles Microsoft Teams avec Exchange Online.
ms.openlocfilehash: e6eb3253d7edb999ba74d28ef9a6d8ae835ac16d
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055484"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Déployer des Salles Microsoft Teams avec Exchange Online

Lisez cette rubrique pour plus d’informations sur la façon de déployer des Salles Microsoft Teams avec Exchange Online.
  
Si votre organisation dispose d’un mélange de services, dont certains sont hébergés en local et d’autres en ligne, votre configuration dépend de l’endroit où chaque service est hébergé. Cette rubrique traite des déploiements hybrides Salles Microsoft Teams avec des Exchange en ligne. Ce type de déploiement étant très différent, il n’est pas possible de fournir des instructions détaillées pour l’ensemble d’entre eux. Le processus suivant fonctionne pour de nombreuses configurations. Si le processus n’est pas configuré pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour obtenir le même résultat final que celui documenté ici, ainsi que pour d’autres options de déploiement.

## <a name="requirements"></a>Conditions requises

Avant de déployer Salles Microsoft Teams avec Exchange Online, assurez-vous que vous avez répondu à la exigences. Pour plus d’informations, [voir Salles Microsoft Teams requise.](requirements.md)
  
Pour déployer des Salles Microsoft Teams’Exchange Online, suivez les étapes ci-dessous. Assurez-vous que vous êtes autorisé à exécuter les cmdlets. 

   > [!NOTE]
   >  Le [module Azure Active Directory pour Windows PowerShell cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) dans cette section (par exemple, Set-MsolUser) a été testé dans le cadre de la configuration des comptes pour Salles Microsoft Teams. Il est possible que d’autres cmdlets fonctionnent, toutefois, elles n’ont pas été testées dans ce scénario particulier.

Si vous avez déployé les services AD FS (Active Directory Federation Services), vous deront peut-être convertir le compte d’utilisateur en utilisateur géré avant de suivre ces étapes, puis convertir l’utilisateur en utilisateur fédéré une fois ces étapes terminées.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Création d’un compte et définition des propriétés Exchange

1. Démarrez une session de Windows PowerShell distante sur un PC et connectez-vous à Exchange Online comme suit :

    ``` Powershell
   Connect-ExchangeOnline
    ```

2. Après avoir établi une session, vous allez créer une boîte aux lettres et l’activer en tant que compte RoomMailboxAccount, ou modifier les paramètres d’une boîte aux lettres de salle existante. Cela permet au compte de s’authentifier dans Salles Microsoft Teams.

   Si vous modifiez une boîte aux lettres de ressource :

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Si vous créez une boîte aux lettres de ressources :

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name 'ConferenceRoom01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Pour améliorer l’expérience de réunion, vous devez définir les propriétés Exchange du compte d’utilisateur comme suit :

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Rooms enabled  room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Ajout d’une adresse e-mail pour votre compte de domaine sur site

1. Dans l’outil Utilisateurs et ordinateurs **Active Directory AD,** cliquez avec le bouton droit sur le conteneur ou l’unité d’organisation dans qui vos comptes Salles Microsoft Teams seront créés, cliquez sur **Nouveau,** puis sur **Utilisateur.**
2. Tapez le nom d’affichage (- Identité) de l’cmdlet  précédente (Set-Mailbox ou  New-Mailbox) dans la zone Nom complet et l’alias dans la zone Nom de l’utilisateur. Cliquez sur **Suivant**.
3. Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.

    > [!NOTE]
    > La sélection **du mot de passe n’expire** jamais est une obligation pour Salles Microsoft Teams. Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe. Si c’est le cas, vous devez créer une exception pour Salles Microsoft Teams compte d’utilisateur.
  
4. Cliquez sur **Terminer** pour créer le compte.
5. Après avoir créé le compte, exécutez une synchronisation d’annuaires. Cela peut être réalisé à l’aide de la configuration [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) dans PowerShell. Lorsque cette procédure est terminée, allez sur la page de l’utilisateur et vérifiez que les deux comptes créés lors des étapes précédentes ont été fusionnés.

### <a name="assign-an-office-365-license"></a>Affectation d’une licence Office 365

1. Tout d’abord, connectez-Azure AD pour appliquer certains paramètres de compte. Pour vous connecter, vous pouvez exécuter l’applet de commande suivante. Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0 n’est](/powershell/azure/active-directory/overview?view=azureadps-2.0) pas pris en charge.

    ``` PowerShell
   Connect-MsolService
    ```

2. Le compte d’utilisateur doit avoir une licence Office 365 valide pour se connecter à Microsoft Teams. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’utilisateur ; cela permet de déterminer les SKU de licence disponibles pour votre compte.
3. Utilisez la référence « Get-MsolAccountSku » pour récupérer la liste des références SKU disponibles pour Office 365 client.
4. Une fois les S SKUs répertoriées, vous pouvez ajouter une licence à l’aide de la licence « Set-MsolUserLicense » <!-- Set-AzureADUserLicense--> cmdlet. 

    ```PowerShell
     Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM
    ```

## <a name="validate"></a>Validate

Pour validation, vous devez être en mesure d’utiliser n’importe Microsoft Teams client pour vous connectez au compte que vous avez créé.
  
## <a name="see-also"></a>Voir aussi

[Mettre à jour les boîtes aux lettres de salle avec des métadonnées supplémentaires pour fournir une meilleure expérience de recherche et de suggestion de salle](/powershell/module/exchange/set-place)

[Configurer des comptes pour Salles Microsoft Teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)
