---
title: Gérer les fonctionnalités de Microsoft Teams de votre organisation d’Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Découvrez toutes les fonctionnalités de Microsoft Teams que vous pouvez activer ou désactiver dans votre organisation Office 365, y compris les paramètres à l'échelle du client, l'intégration de la messagerie, les applications, le stockage cloud et bien d'autres.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: d4e450f4ffcb178a19d185b14d65b7adb880924b
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2018
---
<a name="manage-microsoft-teams-features-in-your-office-365-organization"></a>Gérer les fonctionnalités de Microsoft Teams de votre organisation d’Office 365
======================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Équipes a plusieurs paramètres qui peuvent être activées ou désactivées au niveau des clients Office 365. Avec les équipes activés, tout utilisateur qui est également activée pour les équipes héritent des paramètres à partir du niveau du locataire.

Voici la liste des fonctionnalités qu'un administrateur Office 365 peut activer ou désactiver dans Teams. 

Sauf indication contraire, une option est activée par défaut.

> [!NOTE] 
> Pour gérer les paramètres d'administration dans Teams, accédez au Centre d'administration Office 365 et ouvrez **Paramètres** > **Services et compléments**, puis sélectionnez **Microsoft Teams**. Si vous êtes connecté en tant qu’administrateur d’Office 365, ce lien vous dirige sur cette option : 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

> [!IMPORTANT]
> Un administrateur d’Office 365 peut désactiver Microsoft Teams à tout moment via le Centre d'administration Office 365. Notez que la vignette de Microsoft Teams s'affichera toujours pour les utilisateurs disposant de licences actives pour l'application même si vous la désactivez. Pour plus d'informations sur la suppression de licences, reportez-vous à la rubrique [Gestion de l'accès des utilisateurs à Microsoft Teams](user-access.md). Une fois l'application désactivée, l'accès à partir du client Teams est bloqué, mais les données disponibles au moyen d'autres clients et services restent accessibles, telles que les fichiers disponibles via SharePoint et OneDrive. Toutes les données restent en place à moins que les équipes aient été explicitement supprimées.

<a name="office-365-tenant-wide-settings"></a>Paramètres à l'échelle du client Office 365 
---------------------

Dans **Paramètres à l'échelle du client**, vous pouvez activer ou désactiver des options sous les sections Général, Intégration de messagerie, Applications et Stockage cloud personnalisé.

Pour modifier les **paramètres à l'échelle du client** de Teams, accédez au Centre d’administration Office 365. Sélectionnez **Paramètres** > **Services et compléments** > **Microsoft Teams**.

### <a name="general"></a>Général

La section Général vous permet de configurer les paramètres suivants pour votre organisation :

> ![Capture d'écran de la section Général dans les paramètres à l'échelle du client.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   **Afficher l'organigramme dans le profil personnel :** lorsque ce paramètre est activé, il affiche l'icône de l'organigramme dans la carte de visite de l'utilisateur ; les détails de l'organigramme apparaissent en cliquant sur cette icône.

    ![Capture d'écran de l'icône d'organigramme d'une carte de visite d'un utilisateur.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![Capture d'écran d'un organigramme.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-  **Utiliser Skype Entreprise pour les destinataires qui ne disposent pas de Teams :** lorsque ce paramètre est activé, les conversations Teams apparaissent automatiquement dans Skype Entreprise pour les utilisateurs pour lesquels Teams n'est pas activé.  

-   **Autoriser les messages d'aide proactifs de T-Bot :** lorsque ce paramètre est activé, T-bot lancera une session de conversation privée avec les utilisateurs pour les aider à utiliser Teams.

    ![Capture d'écran de la section T-Bot dans l'interface de Teams.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a>Intégration de la messagerie
-----------------

Activez cette fonctionnalité pour que les utilisateurs puissent envoyer des e-mails à un canal dans Teams, en utilisant l’adresse de messagerie du canal. Les utilisateurs peuvent envoyer des e-mails pour tous les canaux appartenant à une équipe dont ils sont propriétaires. Ils peuvent également envoyer des e-mails à n’importe quel canal dans une équipe pour laquelle la fonction d’ajout de connecteurs est activée pour les membres de l’équipe. De plus, même si un utilisateur n'est pas autorisé à créer une adresse de messagerie de canal, si une personne qui dispose de cette autorisation crée cette adresse, l'utilisateur pourra y avoir accès depuis le menu **Plus d'options** de ce canal.

Configurez les paramètres d'**intégration de la messagerie** suivants pour votre organisation : 

   ![Capture d'écran de la section Intégration de la messagerie dans les paramètres à l'échelle du client.](media/QS-edu-email-integration.png)


-   **Autoriser les utilisateurs à envoyer des e-mails aux canaux :** lorsque ce paramètre est activé, des hooks de messagerie sont activés et les utilisateurs peuvent publier des messages dans un canal en envoyant un e-mail à l'adresse de messagerie du canal Teams. 

    Pour rechercher l'adresse de messagerie d'un canal, cliquez sur le menu **Plus d'options** du canal, puis sélectionnez **Obtenir l'adresse de messagerie**. 

-   **Liste des utilisateurs restreints :** les domaines d'expéditeurs peuvent être limités pour garantir que seuls les domaines SMTP autorisés peuvent envoyer des e-mails aux canaux Teams.

<a name="apps"></a>Applications
----

Les applications sont des onglets, des connecteurs et des bots ou toute combinaison de ces éléments, fournis par un service tiers. Des stratégies d'administration Teams peuvent être configurées dans le Centre d'administration Office 365 pour contrôler l'autorisation d'applications tierces externes. Ces stratégies vous permettent de spécifier les applications autorisées et non autorisées, le comportement d'une nouvelle application externe, ainsi que l'autorisation du chargement de version test d'applications. 

La section **Applications** vous permet de configurer les paramètres suivants pour votre organisation : 

![Capture d'écran de la section Applications.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- **Autoriser les applications externes dans Microsoft Teams :** lorsque cette option est activée, les utilisateurs peuvent ajouter des onglets et des bots disponibles pour le client Office 365. 
 
    ![Capture d'écran de la commande Autoriser les applications externes dans la section Applications.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- **Activer les applications externes nouvelles par défaut** : lorsque cette option est activée, les utilisateurs peuvent activer les nouvelles applications dès qu'elles sont ajoutées au catalogue d'applications Teams. Désactivez cette option si vous souhaitez contrôler les nouvelles applications. Bien sûr, si vous la désactivez, n'oubliez pas de vérifier régulièrement les nouvelles applications afin que votre organisation ne passe pas à côté de nouvelles applications intéressantes. 

- **Autoriser le chargement des versions de test d'applications externes :** lorsque cette option est activée, les utilisateurs peuvent installer et activer des bots et onglets personnalisés. 

Pour en savoir plus, consultez la rubrique [Paramètres d'administration pour les applications dans Microsoft Teams](admin-settings.md). 



<a name="custom-cloud-storage"></a>Stockage cloud personnalisé
--------------------

Actuellement, les options de stockage cloud dans Teams incluent Box, Dropbox, Google Drive et ShareFile. Les utilisateurs peuvent charger et partager des fichiers à partir de services de stockage cloud dans les canaux et conversations Teams. Activez l'option pour les fournisseurs de stockage cloud que votre organisation souhaite utiliser. 

![Capture d'écran de la section Stockage cloud personnalisé.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="settings-by-userlicense-type"></a>Paramètres par type de licence d’utilisateur
------------------------
Lorsque vous configurez Microsoft Teams de votre organisation au départ, vous avez utilisé la la liste déroulante **paramètres par type de licence d’utilisateur** pour sélectionner un type de licence puis rallumé équipes pour tous les utilisateurs de ce type de licence.

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

 **Business & entreprise** et **invité**sont des exemples de types de licence d’utilisateur. (Si vous disposez d’une licence de formation SKU, **éducation - du corps enseignant et du personnel** ou **l’éducation - Student** sont disponibles.) ![Contrôle de licence utilisateur de jeu](media/enable-microsoft-teams-features-in-your-office-365-organization-image13.png)

Vous avez plusieurs types de licences au sein de votre organisation, par exemple, les **professionnels et entreprise** et **invité**. Microsoft Teams pouvez différencier uniquement les utilisateurs basés sur les licences que vous leur avez attribués. Vous pouvez activer ou désactiver les options pour ces utilisateurs dans les **équipes et les canaux**, **les réunions et les appels**et de la **messagerie**. Si vous utilisez le type de licence qu’une seule, tenir compte des paramètres ici en tant que paramètres au niveau du client.
> [!NOTE]
> Pour plus d’informations sur l’accès invité, voir [Activer ou désactiver l’accès invité pour les équipes de Microsoft](set-up-guests.md).

<a name="teams-and-channels"></a>Équipes et canaux
------------------

Une équipe rassemble un groupe de personnes qui travaillent ensemble pour atteindre leurs objectifs. Les équipes peuvent être dynamiques dans le cadre d'activités de projet (par exemple, pour lancer un produit ou créer un centre de crise numérique). Les équipes peuvent également être continues et refléter la structure interne de votre organisation.

Le nombre maximal d'équipes qu'un client Office 365 peut comprendre est actuellement de 500 000. Un administrateur général peut créer un nombre illimité d'équipes. Un utilisateur peut créer 250 équipes. Un propriétaire d'équipe peut ajouter 2 500 membres à une équipe.

En tant qu'administrateur, vous pouvez gérer les propriétaires et les membres d'équipe à l'aide du tableau de bord Groupes dans le Centre d'administration Office 365. Pour en savoir plus, cliquez sur **Utiliser le tableau de bord Groupes dans le Centre d'administration Office 365 pour gérer les équipes** sous l'option **Équipes et canaux**.

Vous pouvez décider quels utilisateurs de votre organisation peuvent créer des équipes dans Teams.  Les mêmes paramètres de création définis par des groupes Office 365 s'appliquent à Teams. Pour plus d'informations sur la gestion des groupes Office 365, consultez les rubriques [Créer des groupes Office 365](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) et [Gérer les utilisateurs qui peuvent créer des groupes Office 365](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

> [!NOTE]
> Vous ne pouvez pas créer d’équipes depuis le tableau de bord Groupes. Les équipes doivent être créées à l'aide du client de bureau ou de l'application Web Teams.

Par défaut, chaque utilisateur peut créer une équipe ou un groupe. Sélectionnez **Équipes** dans la partie gauche du client Teams (client de bureau ou application Web), puis l’option **Créer et rejoindre une équipe** dans la partie inférieure du client, sous la liste des clients.

![Capture d'écran des Paramètres utilisateur dans la section de licence.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

Les canaux sont des sous-catégories d'équipes. Chacun des membres de l'équipe peut ajouter des canaux et participer à des conversations dans un canal. Vous pouvez créer un canal pour une activité ou un service. Les conversations, fichiers et pages wiki sont propres à chaque canal, mais tous les membres de l'équipe peuvent les afficher.

## <a name="calls-and-meetings"></a>Appels et réunions

Configurez les paramètres d'**appels et de réunions** suivants pour votre organisation :

![Capture d'écran de la section Appels et réunions.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

Une réunion peut inclure 80 personnes maximum. Une conversation privée peut compter 20 membres, y compris l'utilisateur qui en est à l'origine.

-   **Autoriser la planification de réunions privées** : lorsque ce paramètre est activé, les utilisateurs peuvent planifier des réunions privées qui n'apparaîtront dans aucun canal.

-   **Autoriser les réunions ad-hoc de canal** : lorsque ce paramètre est activé, les utilisateurs peuvent démarrer rapidement une réunion pour un canal qui a été créé à une fin immédiate ou spécifique.

-   **Autoriser la planification de réunions de canal** : lorsque ce paramètre est activé, les utilisateurs peuvent planifier une réunion pour un canal à laquelle les membres pourront facilement participer en un clic.

-   **Autoriser la vidéo dans les réunions** : spécifie si l'utilisation de la vidéo est autorisée dans les réunions.

-   **Autoriser le partage d'écran dans les réunions** : spécifie si le partage d'écran est autorisé dans les réunions.

-   **Autoriser les appels privés** : lorsque ce paramètre est activé, les utilisateurs peuvent passer des appels privés.

## <a name="messaging"></a>Messagerie 

La section Messagerie vous permet de configurer les paramètres suivants pour votre organisation :

![Capture d'écran de la section Messagerie.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   **Activer Giphy pour permettre aux utilisateurs d'ajouter des images animées aux conversations** : lorsque ce paramètre est activé, les utilisateurs peuvent utiliser des images animées dans les conversations.

-   **Contrôle d'accès au contenu** : lorsque les images animées sont activées, vous pouvez appliquer un contrôle d'accès au contenu pour limiter l'affichage dans les conversations en fonction du type d'images animées. Les options de contrôle d'accès au contenu disponibles sont les suivantes :

    -   Aucune restriction
    -   Modéré (valeur par défaut)
    -   Strict

-   **Activer les mèmes pour permettre aux utilisateurs de les modifier et de les ajouter aux conversations** : lorsque ce paramètre est activé, les utilisateurs peuvent utiliser des mèmes Internet pour publier des messages amusants.

-   **Activer les autocollants pour permettre aux utilisateurs de les modifier et de les ajouter aux conversations** : lorsque ce paramètre est activé, les utilisateurs peuvent publier des images avec un texte modifiable pour attirer l'attention des membres d'un canal.

-   **Autoriser les propriétaires à supprimer tous les messages** : lorsque ce paramètre est activé, les propriétaires de canal peuvent supprimer tous les messages d'un canal.

-   **Autoriser les utilisateurs à modifier leurs propres messages** : lorsque ce paramètre est activé, les utilisateurs peuvent modifier leurs propres messages.

-   **Autoriser les utilisateurs à supprimer leurs propres messages** : lorsque ce paramètre est activé, les utilisateurs peuvent supprimer leurs propres messages.

-   **Autoriser les utilisateurs à discuter en privé** : lorsque ce paramètre est activé, les utilisateurs peuvent mener des conversations privées visibles uniquement pour les personnes qui y participent, non pour tous les membres de l'équipe.


| |  |  |
|---------|---------|---------|
|![Icône Point de décision.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |Point de décision         |Quels sont les paramètres que votre organisation activera pour Microsoft Teams ?         |
|![Icône Étapes suivantes.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |Étapes suivantes        |Documentez ces décisions dans le tableau qui se trouve dans [Assigner des rôles et des autorisations dans Microsoft Teams](assign-roles-permissions.md).         |

