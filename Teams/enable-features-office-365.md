---
title: Gérer les paramètres pour votre organisation
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ritikag
search.appverid: MET150
description: Découvrez comment activer ou désactiver les paramètres à l’échelle de l’organisation Microsoft Teams, y compris les applications, l’accès externe, l’accès invité, les paramètres Teams et les préférences de mise à niveau Teams.
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.teamssettings.targetingintro
- ms.teamsadmincenter.teamssettings.overview
- NewAdminCenter_Update
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d39ec3f7bb6a5454c25acf859e335993ed275a71
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042501"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a>Gérer les paramètres de Microsoft Teams pour votre organisation

## <a name="teams-apps-settings-in-the-microsoft-teams-admin-center"></a>Paramètres des applications Teams dans le centre d’administration Microsoft Teams

Vous gérez les applications pour votre organisation dans les **applications Teams** au sein du [centre d’administration Microsoft Teams](https://admin.teams.microsoft.com). Par exemple, vous pouvez définir des stratégies pour contrôler les applications disponibles pour l’ensemble de l’organisation ou pour des utilisateurs spécifiques de Teams. Vous pouvez également personnaliser Teams en épinglant les applications les plus importantes pour vos utilisateurs.

Pour en savoir plus, voir [Paramètres d’administration des applications dans Teams](admin-settings.md).  

## <a name="teams-org-wide-settings-in-the-microsoft-teams-admin-center"></a>Paramètres Teams à l’échelle de l’organisation dans le centre d’administration de Microsoft Teams

Vous pouvez contrôler les paramètres utilisateur à l’échelle de l’organisation dans le centre d’administration de Microsoft Teams. Pour modifier les paramètres à l’échelle de l’organisation, accédez au centre d’administration de Microsoft Teams, puis sélectionnez **Paramètres à l’échelle de l’organisation**. Vous pouvez configurer les paramètres suivants.

### <a name="external-access"></a>Accès externe

L’**accès externe** permet aux utilisateurs de Teams et de Skype Entreprise de communiquer avec des utilisateurs extérieurs à votre organisation. Pour configurer l’accès externe, accédez à la rubrique [Permettre aux utilisateurs de Teams de discuter et de communiquer avec des utilisateurs d’une autre organisation Teams](let-your-teams-users-communicate-with-other-people.md).

Pour ajouter ou bloquer un domaine :

1. Sélectionnez **Ajouter un domaine**.
2. Dans la zone Ajouter un volet de domaine, entrez le nom de domaine, puis cliquez sur la barre d’espace pour enregistrer le nom.
3. Sélectionnez **Autorisés** ou **Bloqués**.
4. Sélectionnez **OK** pour enregistrer vos modifications. 

### <a name="guest-access"></a>Accès invité

L’**accès invité** dans Microsoft Teams permet aux équipes de votre organisation de collaborer avec des personnes à l’extérieur de votre organisation en leur accordant l'accès aux équipes et aux canaux.Toutes les personnes ayant un compte de messagerie professionnel ou de particulier tel que Outlook, Gmail, etc. peuvent participer en tant qu’invitées dans Teams, avec un accès complet aux conversations, réunions et fichiers des équipes. Pour plus d’informations, reportez-vous à la rubrique [Accès invité dans Microsoft Teams](guest-access.md).

### <a name="teams-settings"></a>Paramètres de Teams

Dans les **Paramètres de Teams**, vous pouvez configurer des fonctionnalités pour les équipes, notamment les notifications et les flux, l’intégration des e-mails, les options de stockage cloud et les appareils.

#### <a name="notifications-and-feeds"></a>Notifications et flux

Vous pouvez déterminer si les flux suggérés s’affichent dans le flux d’activité des utilisateurs dans Teams. Pour en savoir plus sur le flux d’activités, voir [Explorer le flux d’activités dans Microsoft Teams](https://support.office.com/article/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56).

#### <a name="tagging"></a>Marquage

Les indicateurs permettent aux utilisateurs de communiquer avec un sous-ensemble de membres d’une équipe. Les indicateurs peuvent être ajoutés à un ou plusieurs membres de l’équipe. Une fois qu’une étiquette est ajoutée, elle peut être utilisée dans @mentions par tous les membres de l’équipe dans un billet de canal pour communiquer uniquement avec les personnes auxquelles cette étiquette est attribuée. Utilisez ces paramètres pour contrôler les utilisateurs pouvant ajouter des indicateurs et la manière dont les étiquettes sont utilisées au sein de votre organisation. Pour plus d’informations, consultez [Gérer les étiquettes dans Teams](manage-tags.md).

#### <a name="email-integration"></a>Intégration de courrier électronique

Activez cette fonctionnalité pour que les utilisateurs puissent envoyer des e-mails à un canal dans Teams, en utilisant l’adresse de messagerie du canal. Les utilisateurs peuvent envoyer des e-mails pour tous les canaux appartenant à une équipe dont ils sont propriétaires. Ils peuvent également envoyer des e-mails à n’importe quel canal dans une équipe pour laquelle la fonction d’ajout de connecteurs est activée pour les membres de l’équipe. Pour activer l’intégration de la messagerie, assurez-vous que l’option **Autoriser les utilisateurs à envoyer des e-mails à une adresse e-mail de canal** est **activée**.

#### <a name="files"></a>Fichiers

Ici, vous pouvez activer ou désactiver les options de partage de fichiers et de stockage de fichiers dans le cloud.

Les utilisateurs peuvent charger et partager des fichiers à partir de services de stockage cloud dans les canaux et conversations Teams. Actuellement, les options de stockage cloud dans Teams incluent Dropbox, Box, ShareFile, Google Drive et Egnyte (bientôt disponible). Activez l'option pour les fournisseurs de stockage cloud que votre organisation souhaite utiliser.

#### <a name="organization"></a>Organisation

Cette option vous permet d’activer l'onglet **Organisation**, qui affiche l'organigramme détaillé de l'organisation de l’utilisateur. Pour plus d’informations, reportez-vous à la rubrique [Utiliser l’onglet Organisation dans Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).

#### <a name="devices"></a>Appareils

Ces paramètres contrôlent le comportement du compte de ressource pour les périphériques Surface Hub qui participent aux réunions Teams. Utilisez ces paramètres pour configurer les exigences d’authentification, demander un code confidentiel de contenu et activer les comptes de ressource Surface Hub pour envoyer des messages.

- **Requiert un seconde mode d’authentification pour accéder au contenu des réunions** : sélectionnez le niveau d’accès dont disposent les utilisateurs lorsqu'ils entrent le code confidentiel de contenu.
- **Définir le code confidentiel de contenu** : les utilisateurs doivent entrer ce code confidentiel pour empêcher l’accès non autorisé aux documents. Ce paramètre empêche un utilisateur non autorisé de rejoindre les prochaines réunions et d’accéder aux pièces jointes.
- **Les comptes de ressource peuvent envoyer des messages** : **activez** ce paramètre pour autoriser l’envoi de messages depuis le compte de ressource Surface Hub.

#### <a name="search-by-name"></a>Recherche par nom

La fonction de recherche d’annuaire étendue de Microsoft Teams utilise la stratégie de carnet d’adresses (APB) pour permettre aux organisations de créer des limites virtuelles qui contrôlent comment les utilisateurs peuvent trouver d’autres utilisateurs dans leur organisation et communiquer avec eux. Vous pouvez utiliser une recherche d’annuaire étendue dans les situations suivantes :

- Votre organisation comporte plusieurs entreprises au sein de son client que vous souhaitez garder séparées. 
- Votre école souhaite limiter les conversations entre la faculté et les étudiants. 

Basculez ce paramètre sur **Activé** pour activer les recherches d’annuaire étendues.

### <a name="teams-upgrade"></a>Mise à niveau de Teams

Vous pouvez utiliser ces paramètres pour configurer la manière dont vos utilisateurs feront la transition de Skype Entreprise vers Microsoft Teams. 

#### <a name="coexistence-mode"></a>Mode de coexistence
Vous pouvez spécifier un mode de coexistence : 

- **Teams uniquement**
- **Îles ** (Teams et Skype Entreprise coexisteront)
- **Skype Entreprise uniquement**
- **Skype Entreprise avec Teams pour la collaboration** (les utilisateurs participent à des conversations, reçoivent des appels, et planifient des réunions dans Skype Entreprise, mais utilisent Teams pour la collaboration en groupe)
- **Skype Entreprise avec Teams pour la collaboration et les réunions** (les utilisateurs participent à des conversations, reçoivent des appels dans Skype Entreprise, mais utilisent Teams pour la collaboration en groupe et la planification des réunions)

Le mode de coexistence que vous choisissez détermine le routage des appels et conversations entrants et l’application qui est utilisée par l’utilisateur pour initialiser des conversations et appels ou pour planifier des réunions. Pour plus d’informations sur les modes de coexistence, accédez à la rubrique [Comprendre la coexistence et l’interopérabilité de Microsoft Teams et Skype Entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="app-preferences"></a>Préférences d’application

Cette option vous permet de sélectionnez l’application que les utilisateurs utiliseront pour participer à des réunions Skype Entreprise (Skype Entreprise ou [l’application Réunions Skype](https://support.office.com/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Ce paramètre ne dépend pas du paramètre de mode de coexistence.


#### <a name="network-planner"></a>Planificateur de réseau

Le Planificateur de réseau vous aide à déterminer et organiser les exigences réseau pour connecter les utilisateurs de Teams au sein de votre organisation.  Découvrez comment [utiliser le Planificateur de réseau pour Microsoft Teams](https://docs.microsoft.com/microsoftteams/network-planner).

Vous pouvez également sélectionner l’option « Télécharger l’application Teams en arrière-plan pour les utilisateurs Skype Entreprise ».  Par défaut, le paramètre est défini sur Activé. Lorsque ce paramètre est activé, l’application Teams est téléchargée en arrière-plan pour les utilisateurs de l’application Skype Entreprise sur PC Windows. Cela se produit si le mode de coexistence pour l’utilisateur est Teams uniquement, ou si une notification de mise à niveau en attente est activée dans l’application Skype Entreprise.


## <a name="how-can-i-tell-which-features-are-available"></a>Comment puis-je savoir quelles fonctionnalités sont disponibles ?

Pour des informations sur les nouvelles fonctionnalités de Teams, reportez-vous à la [Feuille de route Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams). Pour plus d'informations sur les fonctionnalités nouvelles et à venir, consultez la page [Nouveautés](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) de Teams et le [blog Microsoft Teams de la communauté technique](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531). 

## <a name="more-information"></a>Plus d’informations

Pour savoir quels rôles peuvent effectuer des fonctions d’administrateur, reportez-vous à la rubrique [Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams](using-admin-roles.md).
