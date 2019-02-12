---
title: Gérer les fonctionnalités de Microsoft Teams dans votre organisation Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Découvrez comment activer ou désactiver les applications Teams dans votre organisation Office 365, notamment les onglets, les connecteurs, les bots ou n’importe quelle combinaison des trois.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: dfa908418061b4a9cc1d899d2ed64a9564b6f181
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753507"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a>Gérer les fonctionnalités de Microsoft Teams dans votre organisation Office 365

Tous les paramètres de Teams seront bientôt migrés vers le nouveau centre d’administration de Microsoft Teams. La seule fonctionnalité de Teams qui est gérée dans le centre d’administration Office 365 est Applications. 

Sauf indication contraire, la valeur par défaut d'une option est **Activée**.

## <a name="tenant-wide-settings"></a>Paramètres à l’échelle du client 

Vous pouvez désactiver ou activer les applications pour Teams dans **Paramètres à l’échelle du client** dans le centre d’administration Microsoft 365. 

Pour modifier les **paramètres à l’échelle du client** de Teams, accédez au centre d’administration Microsoft 365, sélectionnez **Paramètres** > **Services et compléments** > **Microsoft Teams**. Si vous êtes connecté en tant qu’administrateur d’Office 365, ce lien doit vous diriger vers l’emplacement suivant : 

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a>Applications

Apps are tabs, connectors, bots, or any combination of these three, provided by Teams (first-party apps, also known as default apps) or by a third-party (also known as external apps). Under **Apps**, you can enable and disable default apps and configure settings to control external apps.  

#### <a name="default-apps"></a>Applications par défaut

These apps, such as Planner, Praise, and Weather, are provided by Teams. To turn on an app, select the check box for that app. To turn off an app, clear the check box. 

![Capture d’écran de la section Applications par défaut.](media/teams-tenant-wide-settings-default-apps.png "Capture d’écran de la section Applications par défaut")

#### <a name="external-apps"></a>Applications externes

These apps are provided by third parties. You can configure the following settings for external apps.

![Capture d’écran de la section Applications par défaut.](media/teams-tenant-wide-settings-external-apps-settings.png "Capture d’écran de la section Applications par défaut, montrant les paramètres que vous pouvez activer et désactiver")

- **Autoriser les applications externes dans Microsoft Teams :** lorsque ce paramètre est activé, les utilisateurs peuvent ajouter les applications externes qui sont disponibles pour votre organisation. 

- **Enable new external apps by default**: When this setting is turned on, users can activate new apps as soon as they're added to the Teams app catalog. Turn off this setting if you want to control new apps. Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on new apps. 

- **Allow sideloading of external apps**: If you want to turn on some external apps and turn off others , turn off this setting, and then in the list of external apps, turn off the apps that you don't want users to access. When this setting is turned on, team owners and members who are granted permission can sideload apps to Teams. 

Pour en savoir plus, consultez la rubrique [Paramètres d'administration des applications dans Teams](admin-settings.md). 

## <a name="teams-org-wide-settings"></a>Paramètres à l’échelle de l'organisation de Teams

Vous pouvez contrôler les paramètres utilisateur à l’échelle de l’organisation dans le centre d’administration de Microsoft Teams. Pour modifier les paramètres à l’échelle de l’organisation, accédez au centre d’administration de Microsoft Teams, puis sélectionnez **Paramètres à l’échelle de l’organisation**. Vous pouvez configurer les paramètres suivants.

### <a name="external-access"></a>Accès externe

L’**accès externe** permet à vos utilisateurs de Teams et Skype Entreprise de communiquer avec des utilisateurs qui sont à l’extérieur de votre organisation. Pour configurer l’accès externe, accédez à la rubrique [Permettre à vos utilisateurs de Teams de discuter et communiquer avec des utilisateurs dans une autre organisation Teams](let-your-teams-users-communicate-with-other-people.md).

### <a name="guest-access"></a>Accès invité

L’**accès invité** dans Microsoft Teams permet aux équipes de votre organisation de collaborer avec des personnes à l’extérieur de votre organisation en leur accordant l'accès aux équipes et aux canaux.Toutes les personnes ayant un compte de messagerie professionnel ou de particulier tel que Outlook, Gmail, etc. peuvent participer en tant qu’invitées dans Teams, avec un accès complet aux conversations, réunions et fichiers des équipes. Pour plus d’informations, reportez-vous à la rubrique [Accès invité dans Microsoft Teams](guest-access.md).

### <a name="teams-settings"></a>Paramètres de Teams

Dans les **paramètres de Teams**, vous pouvez configurer l'intégration de la messagerie, les options de stockage cloud, l’interopérabilité de Skype Entreprise et les périphériques.

#### <a name="email-integration"></a>Intégration de courrier électronique

Activez cette fonctionnalité pour que les utilisateurs puissent envoyer des e-mails à un canal dans Teams, en utilisant l’adresse de messagerie du canal. Les utilisateurs peuvent envoyer des e-mails pour tous les canaux appartenant à une équipe dont ils sont propriétaires. Ils peuvent également envoyer des e-mails à n’importe quel canal dans une équipe pour laquelle la fonction d’ajout de connecteurs est activée pour les membres de l’équipe. Pour activer l’intégration de la messagerie, assurez-vous que l’option **Autoriser les utilisateurs à envoyer des e-mails à une adresse e-mail de canal** est **activée**. 

#### <a name="files"></a>Fichiers

Ici, vous pouvez activer ou désactiver les options de partage de fichiers et de stockage de fichiers dans le cloud. 

Les utilisateurs peuvent charger et partager des fichiers à partir de services de stockage cloud dans les canaux et conversations Teams. Actuellement, les options de stockage cloud dans Teams incluent ShareFile, Dropbox, Box et Google Drive. Activez l'option pour les fournisseurs de stockage cloud que votre organisation souhaite utiliser.

#### <a name="organization"></a>Organisation

Cette option vous permet d’activer l'onglet **Organisation**, qui affiche l'organigramme détaillé de l'organisation de l’utilisateur. Pour plus d’informations, reportez-vous à la rubrique [Utiliser l’onglet Organisation dans Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).

#### <a name="devices"></a>Appareils

Ces paramètres contrôlent le comportement du compte de ressource pour les périphériques Surface Hub qui participent aux réunions Teams. Utilisez ces paramètres pour configurer les exigences d’authentification, demander un code confidentiel de contenu et activer les comptes de ressource Surface Hub pour envoyer des messages.

- **Requiert un seconde mode d’authentification pour accéder au contenu des réunions** : sélectionnez le niveau d’accès dont disposent les utilisateurs lorsqu'ils entrent le code confidentiel de contenu.
- **Définir le code confidentiel de contenu** : les utilisateurs doivent entrer ce code confidentiel pour empêcher l’accès non autorisé aux documents. Ce paramètre empêche un utilisateur non autorisé de rejoindre les prochaines réunions et d’accéder aux pièces jointes.
- **Les comptes de ressource peuvent envoyer des messages** : **activez** ce paramètre pour autoriser l’envoi de messages depuis le compte de ressource Surface Hub.

#### <a name="search"></a>Rechercher

La fonction de recherche d’annuaire étendue de Microsoft Teams utilise la stratégie de carnet d’adresses (APB) pour permettre aux organisations de créer des limites virtuelles qui contrôlent comment les utilisateurs peuvent trouver d’autres utilisateurs dans leur organisation et communiquer avec eux. Vous pouvez utiliser une recherche d’annuaire étendue dans les situations suivantes :

- Votre organisation comporte plusieurs entreprises au sein de son client que vous souhaitez garder séparées. 
- Votre école souhaite limiter les conversations entre la faculté et les étudiants. 

Basculez ce paramètre sur **Activé** pour activer les recherches d’annuaire étendues.

### <a name="teams-upgrade"></a>Mise à niveau de Teams

Vous pouvez utiliser ces paramètres pour configurer la manière dont vos utilisateurs feront la transition de Skype Entreprise vers Microsoft Teams. 

#### <a name="coexistence-mode"></a>Mode de coexistence
Vous pouvez spécifier un mode de coexistence : **Teams uniquement**, **Îles** (Teams et Skype Entreprise coexisteront) ou **Skype Entreprise uniquement**. Le mode de coexistence que vous choisissez détermine le routage des appels et conversations entrants et l’application qui est utilisée par l’utilisateur pour initialiser des conversations et appels ou pour planifier des réunions. Pour plus d’informations sur les modes de coexistence, accédez à la rubrique [Comprendre la coexistence et l’interopérabilité de Microsoft Teams et Skype Entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="app-preferences"></a>Préférences d’application

Cette option vous permet de sélectionnez l’application que les utilisateurs utiliseront pour participer à des réunions Skype Entreprise (Skype Entreprise ou [l’application Réunions Skype](https://support.office.com/fr-FR/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Ce paramètre ne dépend pas du paramètre de mode de coexistence.

## <a name="how-can-i-tell-which-features-are-available"></a>Comment puis-je savoir quelles fonctionnalités sont disponibles ?

Pour des informations sur les nouvelles fonctionnalités de Teams, reportez-vous à la [Feuille de route Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams). Pour plus d'informations sur les fonctionnalités nouvelles et à venir, consultez la page [Nouveautés](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) de Teams et le [blog Microsoft Teams de la communauté technique](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531). 

## <a name="more-information"></a>Plus d’informations

Pour savoir quels rôles peuvent effectuer des fonctions d’administrateur, reportez-vous à la rubrique [Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams](using-admin-roles.md).
