---
title: "Utiliser des connecteurs Office 365 et personnalisés dans Microsoft Teams | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: tutorial
ms.service: msteams
description: "Les connecteurs permettent à votre équipe de rester informée en fournissant directement à votre canal du contenu et des mises à jour provenant des services que vous utilisez fréquemment."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: bfd68ee3671d7f0cc073d35c79013f0d6c3d7f26
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2017
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>Utiliser des connecteurs Office 365 et personnalisés dans Microsoft Teams
=======================================================

Les connecteurs permettent à votre équipe de rester informée en fournissant directement à votre canal du contenu et des mises à jour provenant des services que vous utilisez fréquemment. Grâce aux connecteurs, les utilisateurs de Microsoft Teams peuvent recevoir des mises à jour de services populaires, tels que Twitter, Trello, Wunderlist, GitHub et VSTS, dans le flux de conversations de leur équipe.

Chaque membre d'une équipe peut associer son équipe à des services cloud populaires à l'aide des connecteurs, et tous les membres sont informés des activités de ce service. Si un utilisateur est supprimé d'une équipe, tous les connecteurs ajoutés à cette équipe par l'utilisateur en question cesseront de fonctionner. Les réunions restent programmées, car elles appartiennent au calendrier du groupe.

Les connecteurs Office 365 peuvent être utilisés avec des groupes Microsoft Teams et Office 365, ce qui facilite la synchronisation de tous les membres et leur permet de recevoir rapidement des informations pertinentes. Microsoft Teams et Exchange utilisent le même modèle de connecteurs, ce qui vous permet d'utiliser les mêmes connecteurs sur les deux plateformes.

Actuellement, les connecteurs peuvent être ajoutés à l'aide des clients de bureau et Web Microsoft Teams. Toutefois, les informations publiées par ces connecteurs peuvent être affichées à l'aide de **tous les clients** y compris mobiles.

1.  Pour ajouter un connecteur à un canal, cliquez sur les **points de suspension (…),** à droite du nom du canal, puis sur **Connecteurs.**

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  Les utilisateurs peuvent effectuer une sélection parmi divers connecteurs disponibles, puis cliquer sur **Ajouter**.

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3.  Renseignez les informations requises pour le connecteur sélectionné et cliquez sur **Enregistrer**. Chaque connecteur nécessite un ensemble d'informations pour fonctionner correctement et certains peuvent également requérir l'ouverture d'une session au service à l'aide des liens fournis dans la page de configuration du connecteur.

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4.  Les données fournies par le connecteur sont automatiquement publiées dans le canal.

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>Développer des connecteurs personnalisés
-----------------------------

Développer des connecteurs personnalisés pouvant être intégrés à vos applications métier est très simple. Vous pouvez utiliser le connecteur **Webhook entrant** intégré pour créer un point de terminaison qui envoie les données à partir d'une application à l'aide des méthodes POST pour HTTP.

1.  Ajoutez le **webhook entrant** comme tout autre connecteur.

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2.  Pour créer un webhook, spécifiez un **nom**, mettez à jour l'image du webhook si nécessaire et cliquez sur **Créer**.

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  Les applications qui envoient des données vers ce canal requièrent l'URL du connecteur webhook. Une **URL unique** est créée lors de la création du **webhook**. Partagez cette URL avec vos développeurs, pour leur permettre de configurer leurs applications pour envoyer des données lorsque nécessaire.

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  Lorsqu'une application externe envoie des données vers un connecteur, le message s'affiche dans la liste de conversations du canal sous forme de message spécial appelé **Carte de connecteur**.

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

Les développeurs peuvent configurer leurs applications pour créer ces cartes, en envoyant une demande HTTP avec une charge JSON simple à l'adresse de webhook d'une équipe Microsoft, qui est une URL unique de ce point de terminaison fournie par l'assistant. Vos développeurs peuvent consulter l'article [Prise en main des connecteurs Office 365 pour Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855783), sur la page Microsoft Developer Network, pour obtenir des instructions détaillées et des exemples de connecteur. D'autres ressources telles que l'article [Connecter aux applications à vos groupes dans Outlook](https://support.office.com/en-us/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) et le [Centre de développement Office de Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784) sont également disponibles.
