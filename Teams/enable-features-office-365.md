---
title: "Activer les fonctionnalités Microsoft Teams dans votre organisation Office 365 | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Découvrez toutes les fonctionnalités Microsoft Teams que vous pouvez activer dans votre organisation Office 365, y compris des paramètres à l'échelle du client, des intégrations de messagerie, des applications, le stockage cloud et bien d'autres."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7c626acc5e9fe4d19d7198ea023df155ff427f40
ms.sourcegitcommit: 4a396557d51c7fb246144cd682bcf5e6a2c823be
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2017
---
<a name="enable-microsoft-teams-features-in-your-office-365-organization"></a>Activer les fonctionnalités Microsoft Teams dans votre organisation Office 365
======================================================

Microsoft Teams dispose de multiples paramètres qui peuvent être activés ou désactivés au niveau du client. Lorsque Teams est activé pour le client, tous les utilisateurs pour lesquels Teams est également activé hériteront des paramètres du niveau client.

Voici une liste des fonctionnalités qu'un administrateur Office 365 peut activer ou désactiver dans Teams.

Sauf indication contraire, une option est activée par défaut.

> [!NOTE]
> Un administrateur Office 365 peut désactiver Microsoft Teams à tout moment via le Centre d'administration Office 365. Notez que la vignette de Microsoft Teams s'affichera toujours pour les utilisateurs disposant de licences actives pour l'application même si vous la désactivez. Pour plus d'informations sur la suppression de licences, reportez-vous à la rubrique [Gestion de l'accès des utilisateurs à Microsoft Teams](user-access.md). Une fois l'application désactivée, l'accès à partir du client Teams est bloqué, mais les données disponibles au moyen d'autres clients et services restent accessibles, telles que les fichiers disponibles via SharePoint et OneDrive. Toutes les données restent en place à moins que les équipes aient été explicitement supprimées.

<a name="tenant-wide-settings"></a>Paramètres à l'échelle du client 
---------------------

Dans **Paramètres à l'échelle du client**, vous pouvez activer ou désactiver des options sous les sections Général, Intégration de messagerie, Applications et Stockage cloud personnalisé.

### <a name="general"></a>Général

La section Général vous permet de configurer les paramètres suivants pour votre organisation :

> ![Capture d'écran de la section Général dans les paramètres à l'échelle du client.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   **Afficher l'organigramme dans le profil personnel :** Lorsque ce paramètre est activé, il affiche l'icône de l'organigramme dans la carte de visite de l'utilisateur ; les détails de l'organigramme apparaissent en cliquant sur cette icône.

    ![Capture d'écran de l'icône d'organigramme d'une carte de visite d'un utilisateur.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![Capture d'écran d'un organigramme.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-   **Utiliser Skype Entreprise pour les destinataires qui ne disposent pas de Microsoft Teams :** Lorsque ce paramètre est activé, il permet aux utilisateurs Microsoft Teams de contacter d'autres utilisateurs pour lesquels Microsoft Teams n'est pas activé via Skype Entreprise.

-   **Autoriser les messages d'aide proactifs de T-Bot :** Lorsque ce paramètre est activé, T-bot lancera une session de conversation privée avec les utilisateurs pour les orienter dans l'utilisation de Microsoft Teams.

    ![Capture d'écran de la section T-Bot dans l'interface Microsoft Teams.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a>Intégration de la messagerie
-----------------

Activez cette fonctionnalité pour permettre aux utilisateurs d'envoyer un e-mail à un canal dans Microsoft Teams, à l'aide de l'adresse de messagerie du canal. Les utilisateurs peuvent réaliser cette action pour tous les canaux appartenant à une équipe dont ils sont propriétaires. Ils peuvent également envoyer un e-mail à tous les canaux d'une équipe pour laquelle l'ajout de connecteurs a été activé pour ses membres. De plus, même si un utilisateur n'a pas l'autorisation de créer une adresse de messagerie de canal, si un autre utilisateur qui la possède crée cette adresse, le premier pourra y avoir accès par le menu de l'\<icône plus\> de ce canal.

La section Intégration de la messagerie vous permet de configurer les paramètres suivants pour votre organisation :

   ![Capture d'écran de la section Intégration de la messagerie dans les paramètres à l'échelle du client.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image5.png)

-   **Autoriser les utilisateurs à envoyer des e-mails aux canaux :** Lorsque ce paramètre est activé, des hooks de messagerie sont activés et les utilisateurs peuvent publier des messages dans un canal en envoyant un e-mail à l'adresse de messagerie du canal Microsoft Teams.

> Pour rechercher l'adresse de messagerie d'un canal, cliquez sur **Plus d'options** près du nom du canal, puis sélectionnez **Obtenir l'adresse de messagerie**.

-   **Liste des utilisateurs restreints :** Les domaines d'expéditeurs peuvent être limités pour garantir que seuls les domaines SMTP autorisés peuvent envoyer des e-mails aux canaux Microsoft Teams.

<a name="apps"></a>Applications
----

Les applications dans Microsoft Teams sont particulièrement pratiques pour intégrer les outils et services dont votre équipe a besoin directement dans un canal ou une conversation.

La section **Applications** vous permet de configurer les paramètres suivants pour votre organisation :

![Capture d'écran de la section Applications.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

-   **Autoriser les applications externes dans Microsoft Teams :** Lorsque ce paramètre est activé, les utilisateurs peuvent ajouter des onglets et des bots disponibles pour le client Office 365.
![Capture d'écran de la commande Autoriser les applications externes dans la section Applications.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

-   **Autoriser le chargement des versions de test d'applications externes :** Lorsque ce paramètre est activé, les utilisateurs peuvent installer et activer des bots et onglets personnalisés.

<a name="custom-cloud-storage"></a>Stockage cloud personnalisé
--------------------

Actuellement, les options de stockage cloud dans Microsoft Teams incluent Box, Dropbox, Google Drive et ShareFile. Les utilisateurs peuvent charger et partager des fichiers à partir de services de stockage cloud dans les canaux et conversations Microsoft Teams. Cliquez ou appuyez sur le commutateur près des fournisseurs de stockage cloud que votre organisation souhaite utiliser.

![Capture d'écran de la section Stockage cloud personnalisé.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a>Paramètres utilisateur par licence
------------------------

Dans **Paramètres utilisateur par licence**, vous pouvez activer ou désactiver les options dans les sections Équipes et canaux, Appels et réunions et Messagerie.

<a name="teams-and-channels"></a>Équipes et canaux
------------------

Une équipe rassemble un groupe de personnes qui travaillent ensemble pour atteindre leurs objectifs. Les équipes peuvent être dynamiques dans le cadre d'activités de projet (par exemple, pour lancer un produit ou créer un centre de crise numérique). Les équipes peuvent également être continues et refléter la structure interne de votre organisation.

En tant qu'administrateur, vous pouvez gérer les propriétaires et membres d'équipe à l'aide du tableau de bord Groupes dans le portail du Centre d'administration Office 365. Dans la section Équipes et canaux, cliquez sur le lien **Utiliser le tableau de bord Groupes dans le centre d'administration Office 365 pour gérer les équipes**.

Vous pouvez décider quels utilisateurs de votre organisation peuvent créer des équipes dans Microsoft Teams. Les mêmes paramètres de création définis par des groupes Office 365 s'appliquent à Microsoft Teams. Pour plus d'informations sur la gestion des groupes Office 365, reportez-vous aux articles [Créer un groupe Office 365 dans le Centre d'administration](https://support.office.com/en-us/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) et [Gérer les utilisateurs qui peuvent créer des groupes Office 365](https://support.office.com/en-us/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

REMARQUE : Vous ne pouvez pas créer d'équipe à l'aide du tableau de bord Groupes. Les équipes doivent être créées à l'aide du client de bureau ou de l'application Web Microsoft Teams.

Par défaut, chaque utilisateur peut créer une équipe ou un groupe. Les utilisateurs peuvent créer des équipes en sélectionnant Équipes sur le côté gauche du client Microsoft Teams (client de bureau ou application Web), puis en choisissant Créer une équipe dans la partie inférieure du client, sous la liste d'équipes.

Par défaut, un client Office 365 peut actuellement contenir 500 000 équipes au maximum. Un administrateur global peut créer un nombre illimité d'équipes. Un utilisateur peut créer 250 équipes. Un propriétaire d'équipe peut ajouter 2 500 membres à une équipe.

![Capture d'écran des Paramètres utilisateur dans la section de licence.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

Les canaux sont des sous-catégories d'équipes. Chacun des membres de l'équipe peut ajouter des canaux et participer à des conversations dans un canal. Vous pouvez créer un canal pour une activité ou un service. Les conversations, fichiers et pages wiki sont propres à chaque canal, mais tous les membres de l'équipe peuvent les afficher.

### <a name="calls-and-meetings"></a>Appels et réunions

Les canaux sont des sous-catégories d'équipes. Chacun des membres de l'équipe peut ajouter des canaux et participer à des conversations dans un canal. Vous pouvez créer un canal pour une activité ou un service. Les conversations, fichiers et pages wiki sont propres à chaque canal, mais tous les membres de l'équipe peuvent les afficher.

La section **Appels et réunions** vous permet de configurer les paramètres suivants pour votre organisation :

> ![Capture d'écran de la section Appels et réunions.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

-   **Autoriser la planification de réunions privées :** Lorsque ce paramètre est activé, les utilisateurs peuvent planifier des réunions privées qui n'apparaîtront dans aucun canal.

-   **Autoriser les réunions ad hoc de canal :**

-   **Autoriser la planification de réunions de canal :** Lorsque ce paramètre est activé, les utilisateurs peuvent planifier une réunion pour un canal à laquelle les membres pourront facilement participer en un clic.

-   **Autoriser la vidéo dans les réunions :** Spécifie si l'utilisation de la vidéo est autorisée dans les réunions.

-   **Autoriser le partage d'écran dans les réunions :** Spécifie si le partage d'écran est autorisé dans les réunions.

-   **Autoriser les appels privés :** Lorsque ce paramètre est activé, les utilisateurs peuvent passer des appels privés.

Une réunion peut inclure 80 personnes maximum. Une conversation privée peut compter 20 membres, y compris l'utilisateur qui en est à l'origine.

### <a name="messaging"></a>Messagerie 

La section Messagerie vous permet de configurer les paramètres suivants pour votre organisation :

![Capture d'écran de la section Messagerie.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   **Activer Giphy pour permettre aux utilisateurs d'ajouter des images GIF aux conversations :** Lorsque ce paramètre est activé, les utilisateurs peuvent utiliser des images animées dans les conversations.

    -   **Contrôle d'accès au contenu :** Lorsque les images animées sont activées, vous pouvez appliquer un contrôle d'accès au contenu pour limiter l'affichage dans les conversations en fonction du type d'images animées. Les options de contrôle d'accès au contenu disponibles sont les suivantes :

        -   Aucune restriction

        -   Modéré (valeur par défaut)

        -   Strict

-   **Activer les mèmes pour permettre aux utilisateurs de les modifier et de les ajouter aux conversations :** Lorsque ce paramètre est activé, les utilisateurs peuvent utiliser des mèmes Internet pour publier des messages amusants.

-   **Activer les autocollants pour permettre aux utilisateurs de les modifier et de les ajouter aux conversations :** Lorsque ce paramètre est activé, les utilisateurs peuvent publier des images avec un texte modifiable pour attirer l'attention des membres d'un canal.

-   **Autoriser les propriétaires à supprimer tous les messages :** Lorsque ce paramètre est activé, les propriétaires de canal peuvent supprimer tous les messages d'un canal.

-   **Autoriser les utilisateurs à modifier leurs propres messages :** Lorsque ce paramètre est activé, les utilisateurs peuvent modifier leurs propres messages.

-   **Autoriser les utilisateurs à supprimer leurs propres messages :** Lorsque ce paramètre est activé, les utilisateurs peuvent supprimer leurs propres messages.

-   **Autoriser les utilisateurs à discuter en privé :** Lorsque ce paramètre est activé, les utilisateurs peuvent mener des conversations privées visibles uniquement pour les personnes qui y participent, non pour tous les membres de l'équipe.


| |  |  |
|---------|---------|---------|
|![Icône Point de décision.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |Point de décision         |Quels sont les paramètres que votre organisation activera pour Microsoft Teams ?         |
|![Icône Étapes suivantes.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |Étapes suivantes        |Documentez ces décisions dans le tableau qui se trouve dans [Assigner des rôles et des autorisations dans Microsoft Teams](assign-roles-permissions.md).         |

