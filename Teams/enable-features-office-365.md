---
title: Gérer les paramètres pour votre organisation
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ritikag
search.appverid: MET150
description: Découvrez comment activer ou désactiver les paramètres à l’échelle de l’organisation Microsoft Teams, y compris les applications, l’accès externe, l’accès invité, les paramètres Teams et les préférences de mise à niveau Teams.
ms.localizationpriority: high
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
ms.openlocfilehash: b3b16b3015771cd136f3e5ee7333619008ada332
ms.sourcegitcommit: 5b1d8d6f811fab0b350a09e5187d982f952d0edb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2022
ms.locfileid: "63047134"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a>Gérer les paramètres de Microsoft Teams pour votre organisation

## <a name="teams-apps-settings-in-the-microsoft-teams-admin-center"></a>Paramètres des applications Teams dans le centre d’administration Microsoft Teams

Vous gérez les applications pour votre organisation dans les **applications Teams** au sein du [centre d’administration Microsoft Teams](https://admin.teams.microsoft.com). Par exemple, vous pouvez définir des stratégies pour contrôler les applications disponibles pour l’ensemble de l’organisation ou pour des utilisateurs spécifiques de Teams. Vous pouvez également personnaliser Teams en épinglant les applications les plus importantes pour vos utilisateurs.

Pour en savoir plus, voir [Paramètres d’administration des applications dans Teams](admin-settings.md).

### <a name="workflows-in-teams"></a>Flux de travail dans Teams

Les flux de travail vous permettent d’automatiser les tâches répétitives et les processus à l’aide Power Automate. Vous pouvez désactiver les flux de travail pour votre organisation dans Teams à l’aide d’une **stratégie d’autorisation d’application** ou via la page **Gérer les applications** en bloquant Power Automate. Cette fonctionnalité est activée par défaut. Pour plus d’informations sur les flux de travail, consultez [Parcourir et ajouter des flux de travail](https://support.microsoft.com/office/browse-and-add-workflows-4998095c-8b72-4b0e-984c-f2ad39e6ba9a).

Pour désactiver les flux de travail avec une stratégie d’autorisation d’application, modifiez la stratégie globale (par défaut à l’échelle de l’organisation) pour inclure Power Automate dans la liste bloquée ou supprimez-la de la liste autorisée.

Vous pouvez également bloquer Power Automate via la page **Gérer les applications** .

1. Allez à [**Teams applications** > **AppsManage**](https://admin.teams.microsoft.com/policies/manage-apps).
1. Recherchez des **Power Automate**.
1. Sélectionnez l’application.
1. Modifier le **statut** de **Autorisé** à **Bloqué**.

> [!NOTE]
> Lorsque vous désactivez les flux de travail, l’application est masquée dans l’App Store Teams, les extensions de message et le menu Plus d’actions. La désactivation des flux de travail désactive également tous les flux actifs.

## <a name="teams-external-access-and-guest-access-settings-in-the-microsoft-teams-admin-center"></a>Paramètres d’accès externe et d’accès invité Teams dans le Centre d'administration Microsoft Teams

Vous pouvez contrôler les paramètres d’accès externe et d’accès invité dans le Centre d'administration Microsoft Teams. Pour modifier ces paramètres, accédez au Centre d'administration Microsoft Teams, puis sélectionnez **Utilisateurs**. Vous pouvez configurer les paramètres suivants.

### <a name="external-access"></a>Accès externe

L’**accès externe** permet aux utilisateurs de Teams et de Skype Entreprise de communiquer avec des utilisateurs extérieurs à votre organisation. Pour configurer l’accès externe, accédez à la rubrique [Permettre aux utilisateurs de Teams de discuter et de communiquer avec des utilisateurs d’une autre organisation Teams](./manage-external-access.md).

Pour ajouter ou bloquer un domaine :

1. Sélectionnez **Ajouter un domaine**.
2. Dans la zone Ajouter un volet de domaine, entrez le nom de domaine, puis sélectionnez la barre d’espace pour enregistrer le nom.
3. Sélectionnez **Autorisés** ou **Bloqués**.
4. Sélectionnez **OK** pour enregistrer vos modifications. 

### <a name="guest-access"></a>Accès invité

L’**accès invité** dans Microsoft Teams permet aux équipes de votre organisation de collaborer avec des personnes à l’extérieur de votre organisation en leur accordant l'accès aux équipes et aux canaux.Toutes les personnes ayant un compte de messagerie professionnel ou de particulier tel que Outlook, Gmail, etc. peuvent participer en tant qu’invitées dans Teams, avec un accès complet aux conversations, réunions et fichiers des équipes. Pour plus d’informations, reportez-vous à la rubrique [Accès invité dans Microsoft Teams](guest-access.md).

## <a name="teams-settings-and-teams-upgrade-settings-in-the-microsoft-teams-admin-center"></a>Paramètres Teams et paramètres de mise à niveau dans le Centre d'administration Microsoft Teams

Vous pouvez contrôler les paramètres Teams et les paramètres de mise à niveau Teams dans le Centre d'administration Microsoft Teams. Pour modifier ces paramètres, accédez au Centre d'administration Microsoft Teams, puis sélectionnez **Teams**. Vous pouvez configurer les paramètres suivants.

### <a name="teams-settings"></a>Paramètres de Teams

Dans les **Paramètres de Teams**, vous pouvez configurer des fonctionnalités pour les équipes, notamment les notifications et les flux, l’intégration des e-mails, les options de stockage cloud et les appareils.

#### <a name="notifications-and-feeds"></a>Notifications et flux

Vous pouvez déterminer si les flux suggérés s’affichent dans le flux d’activité des utilisateurs dans Teams. Pour en savoir plus sur le flux d’activités, voir [Explorer le flux d’activités dans Microsoft Teams](https://support.office.com/article/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56).

#### <a name="tagging"></a>Marquage

Les indicateurs permettent aux utilisateurs de communiquer avec un sous-ensemble de membres d’une équipe. Les indicateurs peuvent être ajoutés à un ou plusieurs membres de l’équipe. Une fois qu’une étiquette est ajoutée, elle peut être utilisée dans @mentions par tous les membres de l’équipe dans un billet de canal pour communiquer uniquement avec les personnes auxquelles cette étiquette est attribuée. Utilisez ces paramètres pour contrôler les utilisateurs pouvant ajouter des indicateurs et la manière dont les étiquettes sont utilisées au sein de votre organisation. Pour plus d’informations, consultez [Gérer les étiquettes dans Teams](manage-tags.md).

#### <a name="email-integration"></a>Intégration de courrier électronique

Activez cette fonctionnalité pour que les utilisateurs puissent envoyer des e-mails à un canal dans Teams, en utilisant l’adresse de messagerie du canal. Les utilisateurs peuvent envoyer des e-mails pour tous les canaux appartenant à une équipe dont ils sont propriétaires. Les utilisateurs peuvent également envoyer des e-mails à n’importe quel canal d’une équipe pour laquelle l’ajout de connecteurs est activé pour les membres de l’équipe. Pour activer l’intégration des e-mails, assurez-vous que **Autoriser les utilisateurs à envoyer des e-mails à une adresse e-mail du canal** est **activé**. Ensuite, vérifiez que le domaine de l’adresse e-mail de l’expéditeur n’est pas bloqué dans le Centre d’administration Teams>Paramètres à l’échelle de l’organisation>Paramètres Teams>Intégration de courrier électronique>**Accepter les e-mails du canal à partir de ces domaines SMTP**. Celle-ci doit être vide ou inclure tous les domaines dont vous vous attendez à recevoir des e-mails. Ensuite, vous devez vérifier que vous avez les règles nécessaires pour vous assurer que [les e-mails envoyés à l’adresse de messagerie du canal Teams ne sont pas bloqués](/office365/servicedescriptions/exchange-online-protection-service-description/anti-spam-and-anti-malware-protection-eop#customize-anti-spam-policies).

#### <a name="files"></a>Fichiers

Ici, vous pouvez activer ou désactiver les options de partage de fichiers et de stockage de fichiers dans le cloud.

Les utilisateurs peuvent charger et partager des fichiers à partir de services de stockage cloud dans les canaux et conversations Teams. Les options de stockage cloud dans Teams incluent actuellement Dropbox, Box, les fichiers Citrix, Google Drive et Egnyte. Activez l'option pour les fournisseurs de stockage cloud que votre organisation souhaite utiliser.

#### <a name="organization"></a>Organisation

Cette option vous permet d’activer l'onglet **Organisation**, qui affiche l'organigramme détaillé de l'organisation de l’utilisateur. Pour plus d’informations, reportez-vous à la rubrique [Utiliser l’onglet Organisation dans Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).

#### <a name="devices"></a>Appareils

Ces paramètres contrôlent le comportement du compte de ressource pour les périphériques Surface Hub qui participent aux réunions Teams. Utilisez ces paramètres pour configurer les exigences d’authentification, demander un code confidentiel de contenu et activer les comptes de ressource Surface Hub pour envoyer des messages.

- **Requiert un seconde mode d’authentification pour accéder au contenu des réunions** : sélectionnez le niveau d’accès dont disposent les utilisateurs lorsqu'ils entrent le code confidentiel de contenu.
- **Définir le code confidentiel de contenu** : les utilisateurs doivent entrer ce code confidentiel pour empêcher l’accès non autorisé aux documents. Ce paramètre empêche un utilisateur non autorisé de rejoindre les prochaines réunions et d’accéder aux pièces jointes.
- **Les comptes de ressource peuvent envoyer des messages** : **activez** ce paramètre pour autoriser l’envoi de messages depuis le compte de ressource Surface Hub.

#### <a name="search-by-name"></a>Recherche par nom

La fonction de recherche d’annuaire étendue de Microsoft Teams utilise la stratégie de carnet d’adresses (APB) pour permettre aux organisations de créer des limites virtuelles qui contrôlent comment les utilisateurs peuvent trouver d’autres utilisateurs dans leur organisation et communiquer avec eux. Vous pouvez utiliser une recherche d’annuaire étendue dans les situations suivantes :

- Votre organisation comporte plusieurs entreprises au sein de son client que vous souhaitez garder séparées. 
- Votre école souhaite limiter les conversations entre la faculté et les étudiants.

Basculez ce paramètre sur **Activé** pour activer les recherches d’annuaire étendues.

#### <a name="safety-and-communications"></a>Sécurité et communications

La surveillance de conversation permet aux organisations et aux établissements scolaires de limiter les fonctionnalités de conversation à l’aide d’autorisations basées sur les rôles. Ces autorisations contrôlent la quantité de surveillance dont un utilisateur a besoin tout en discutant avec d’autres personnes. En savoir plus sur [surveillance de conversation](supervise-chats-edu.md).

### <a name="teams-upgrade-settings"></a>Paramètres de mise à niveau de Teams

Vous pouvez utiliser ces paramètres pour configurer la manière dont vos utilisateurs feront la transition de Skype Entreprise vers Microsoft Teams. 

#### <a name="coexistence-mode"></a>Mode de coexistence
Vous pouvez spécifier un mode de coexistence : 

- **Teams uniquement**
- **Îles** (Teams et Skype Entreprise coexisteront)
- **Skype Entreprise uniquement**
- **Skype Entreprise avec Teams pour la collaboration** (les utilisateurs participent à des conversations, reçoivent des appels, et planifient des réunions dans Skype Entreprise, mais utilisent Teams pour la collaboration en groupe)
- **Skype Entreprise avec Teams pour la collaboration et les réunions** (les utilisateurs participent à des conversations, reçoivent des appels dans Skype Entreprise, mais utilisent Teams pour la collaboration en groupe et la planification des réunions)

Le mode de coexistence que vous choisissez détermine le routage des appels et conversations entrants et l’application qui est utilisée par l’utilisateur pour initialiser des conversations et appels ou pour planifier des réunions. Pour plus d’informations sur les modes de coexistence, accédez à la rubrique [Comprendre la coexistence et l’interopérabilité de Microsoft Teams et Skype Entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="app-preferences"></a>Préférences d’application

Cette option vous permet de sélectionnez l’application que les utilisateurs utiliseront pour participer à des réunions Skype Entreprise (Skype Entreprise ou [l’application Réunions Skype](https://support.office.com/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Ce paramètre ne dépend pas du paramètre de mode de coexistence.

### <a name="planning-settings-in-the-microsoft-teams-admin-center"></a>Paramètres de planification dans le Centre d’administration Microsoft Teams

#### <a name="network-planner"></a>Planificateur de réseau

Le Planificateur de réseau vous aide à déterminer et organiser les exigences réseau pour connecter les utilisateurs de Teams au sein de votre organisation.  Découvrez comment [utiliser le Planificateur de réseau pour Microsoft Teams](./network-planner.md).

Vous pouvez également sélectionner l’option « Télécharger l’application Teams en arrière-plan pour les utilisateurs Skype Entreprise ».  Par défaut, le paramètre est défini sur Activé. Lorsque ce paramètre est activé, l’application Teams est téléchargée en arrière-plan pour les utilisateurs de l’application Skype Entreprise sur PC Windows. Cela se produit si le mode de coexistence pour l’utilisateur est Teams uniquement, ou si une notification de mise à niveau en attente est activée dans l’application Skype Entreprise.

## <a name="other-settings-in-the-microsoft-teams-admin-center"></a>Autres paramètres du Centre d'administration Microsoft Teams

### <a name="skype-for-business"></a>Skype Entreprise

Utilisez cette page pour gérer les fonctionnalités de Skype Entreprise pour les utilisateurs de Skype Entreprise au sein de votre organisation. Pour plus d’informations, consultez [Gérer les paramètres de Skype Entreprise dans le centre d’administration Microsoft Teams](skype-for-business-settings.md).

## <a name="how-can-i-tell-which-features-are-available"></a>Comment puis-je savoir quelles fonctionnalités sont disponibles ?

Pour des informations sur les nouvelles fonctionnalités de Teams, reportez-vous à la [Feuille de route Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams). Pour plus d'informations sur les fonctionnalités nouvelles et à venir, consultez la page [Nouveautés](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) de Teams et le [blog Microsoft Teams de la communauté technique](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531). 

## <a name="more-information"></a>Plus d’informations

Pour savoir quels rôles peuvent effectuer des fonctions d’administrateur, reportez-vous à la rubrique [Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams](using-admin-roles.md).
