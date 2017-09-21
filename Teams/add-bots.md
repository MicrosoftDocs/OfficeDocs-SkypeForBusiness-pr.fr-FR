---
title: "Ajouter des bots à des conversations et des canaux privés dans Microsoft Teams | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: tutorial
ms.service: msteams
description: "Découvrez comment ajouter des bots dans Microsoft Teams pour des conversations et des canaux privés, créer des bots personnalisés et charger une version test de votre propre bot pour une conversation privée."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 5ce0886a8bf509de53f7956a76b8ba503989aa14
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2017
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Ajouter des bots à des conversations et des canaux privés dans Microsoft Teams
==========================================================

Les bots sont des programmes automatisés configurés pour répondre à des questions ou proposer des mises à jour et des notifications concernant des informations qui intéressent les utilisateurs ou à propos desquels ils souhaitent rester informés. Les bots permettent aux utilisateurs d'interagir avec des services cloud tels que la gestion des tâches, la planification et les sondages, via des conversations dans Microsoft Teams. Les bots pour Microsoft Teams sont créés dans [Bot Framework de Microsoft ](https://go.microsoft.com/fwlink/?linkid=854370) et les bots développés à l'aide de cette structure peuvent être facilement activés pour Microsoft Teams.

Actuellement, Microsoft Teams prend en charge les bots dans les conversations et canaux privés dans une équipe. Les administrateurs peuvent contrôler l'autorisation ou l'interdiction de l'utilisation de bots dans le client Office 365.<span id="_T-Bot" class="anchor"></span>

Les bots développés par la communauté sont mis à disposition et peuvent être utilisés dans Microsoft Teams. La fonctionnalité et le chargement de version test de bot doivent être activés au niveau du client pour rendre les bots personnalisés fonctionnels. Les bots peuvent être utilisés dans les conversations et canaux privés. Dans le cas des canaux, les propriétaires ou membres d'équipe peuvent ajouter des bots.

<a name="add-bots-for-private-chat-and-channels"></a>Ajout de bots pour les conversations et canaux privés
--------------------------------------

Il existe deux méthodes pour intégrer un bot aux conversations et canaux privés :

1.  Installation publique de bots disponibles pour les **conversations** ou les **canaux privés** (Première option)

2.  Il est également possible de rechercher des bots : sélectionnez **Conversation**, recherchez un **contact,** et cliquez sur **Rechercher des applications.**

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image1.png)

3.  Sélectionnez le **Bot** avec lequel vous souhaitez discuter, comme indiqué ci-après.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image2.png)

4.  Une fois sélectionné, octroyez des **autorisations** au bot et décidez si vous voulez l'utiliser **dans une conversation privée** ou dans une **équipe**.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image3.png)

5.  De même, pour utiliser un bot dans le canal d'une équipe, cliquez simplement sur **Afficher l'équipe et les bots**. Vous pouvez rechercher d'autres bots ici.

6.  À tout moment, un bot peut être supprimé de l'équipe. Cliquez simplement sur **Afficher l'équipe et les bots,** pour afficher tous les bots puis **supprimez ** celui de votre choix.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image4.png)

<a name="create-custom-bots-for-microsoft-teams"></a>Création de bots personnalisés pour Microsoft Teams
--------------------------------------

Vous pouvez facilement créer un bot qui s'intègre à vos applications métier à l'aide de Bot Framework de Microsoft. Reportez-vous au guide [Creating and Testing a bot for Microsoft Teams (Création et test de bots pour Microsoft Teams)](https://go.microsoft.com/fwlink/?linkid=854371) pour connaître la procédure de développement et de publication de vos propres bots.

Lorsque vous créez un bot et l'enregistrez avec Bot Framework, vous pouvez décider de le publier ou non. Si vous ne le publiez pas, le bot reste privé. Vous pouvez également demander à vos utilisateurs de se connecter avant d'utiliser le bot. De cette manière, vous serez certain que seuls les employés de votre organisation y accèdent, même si l'ID d'application du bot venait à être révélé. Reportez-vous à la page dédiée à [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) sur GitHub pour obtenir un exemple de code d'authentification des utilisateurs à Azure Active Directory, au moyen de bots.

Les bots peuvent être testés à l'aide de l'[émulateur Bot Framework](https://go.microsoft.com/fwlink/?linkid=854373) avant de les déployer dans Teams.

<a name="side-load-your-own-bot-for-private-chat"></a>Chargement de version test de votre propre bot pour une conversation privée
---------------------------------------

1.  Lorsque vous avez créé votre bot, accédez à la page de **tableau de bord** [](https://go.microsoft.com/fwlink/?linkid=854374) du bot que vous avez développé et sous **Détails**, copiez l'**ID d'application Microsoft**.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  Dans le volet **Conversation** de Microsoft Teams, sélectionnez l'icône **Ajouter une conversation**. Dans **À :,** collez l'**ID d'application Microsoft** de votre bot.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3.  L'ID d'application sera convertie en **nom de bot** et vous pourrez démarrer une conversation avec ce bot.
