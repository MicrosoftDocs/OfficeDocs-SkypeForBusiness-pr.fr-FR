---
title: Utiliser des connecteurs Office 365 et personnalisés dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara, lucarras
description: Les connecteurs permettent à votre équipe de rester informée en fournissant directement à votre canal du contenu et des mises à jour provenant des services que vous utilisez fréquemment.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a5243e32b100f648a71b5e07e55061bd8b3d6aa
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19570079"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>Utiliser des connecteurs Office 365 et personnalisés dans Microsoft Teams
=======================================================

Les connecteurs permettent à votre équipe de rester informée en fournissant directement à votre canal du contenu et des mises à jour provenant des services que vous utilisez fréquemment. Grâce aux connecteurs, les utilisateurs de Microsoft Teams peuvent recevoir des mises à jour de services populaires, tels que Twitter, Trello, Wunderlist, GitHub et VSTS, dans le flux de conversations de leur équipe.

N’importe quel membre d’une équipe peut se connecter leur équipe aux services de cloud populaires avec les connecteurs si l’utilisation de l’équipe des autorisations, et tous les membres de l’équipe sont avertis des activités de ce service. Connecteurs continuent de fonctionner même après le membre qui est initialement le connecteur a quitté le programme d’installation. N’importe quel membre de l’équipe avec les autorisations à ajouter/supprimer peut modifier le programme d’installation de connecteurs par d’autres membres.

Les connecteurs Office 365 peuvent être utilisés avec des groupes Microsoft Teams et Office 365, ce qui facilite la synchronisation de tous les membres et leur permet de recevoir rapidement des informations pertinentes. Microsoft Teams et Exchange utilisent le même modèle de connecteurs, ce qui vous permet d'utiliser les mêmes connecteurs sur les deux plateformes.

Actuellement, les connecteurs peuvent être ajoutés à l'aide des clients de bureau et Web Microsoft Teams. Toutefois, les informations publiées par ces connecteurs peuvent être affichées à l'aide de **tous les clients** y compris mobiles.

1.  Pour ajouter un connecteur à un canal, cliquez sur les **points de suspension (…),** à droite du nom du canal, puis sur **Connecteurs.**

    ![Capture d'écran de l'interface Teams avec un nom de canal sélectionné et l'option Connecteurs sélectionnée.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  Les utilisateurs peuvent effectuer une sélection parmi divers connecteurs disponibles, puis cliquer sur **Ajouter**.

    ![Capture d'écran de la boîte de dialogue Connecteurs affichant les connecteurs disponibles pour être ajoutés.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3.  Renseignez les informations requises pour le connecteur sélectionné et cliquez sur **Enregistrer**. Chaque connecteur nécessite un ensemble d'informations pour fonctionner correctement et certains peuvent également requérir l'ouverture d'une session au service à l'aide des liens fournis dans la page de configuration du connecteur.

    ![Capture d'écran de la page de configuration du connecteur RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4.  Les données fournies par le connecteur sont automatiquement publiées dans le canal.

    ![Capture d'écran de l'interface Teams affichant une conversation dans un canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>Développer des connecteurs personnalisés
-----------------------------

Développer des connecteurs personnalisés pouvant être intégrés à vos applications métier est très simple. Vous pouvez utiliser le connecteur **Webhook entrant** intégré pour créer un point de terminaison qui envoie les données à partir d'une application à l'aide des méthodes POST pour HTTP.

1.  Ajoutez le **webhook entrant** comme tout autre connecteur.

    ![Capture d'écran avec l'option d'ajout du connecteur Webhook entrant.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2.  Pour créer un webhook, spécifiez un **nom**, mettez à jour l'image du webhook si nécessaire et cliquez sur **Créer**.

    ![Capture d'écran de la page de configuration du connecteur Webhook entrant. ](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  Les applications qui envoient des données vers ce canal requièrent l'URL du connecteur webhook. Une **URL unique** est créée lors de la création du **webhook**. Partagez cette URL avec vos développeurs, pour leur permettre de configurer leurs applications pour envoyer des données lorsque nécessaire.

    ![Capture d'écran de l'URL unique du Webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  Lorsqu'une application externe envoie des données vers un connecteur, le message s'affiche dans la liste de conversations du canal sous forme de message spécial appelé **Carte de connecteur**.

    ![Capture d'écran de l'interface Teams affichant un message Carte de connecteur.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

Les développeurs peuvent configurer leurs applications pour créer ces cartes, en envoyant une demande HTTP avec une charge JSON simple à l'adresse de webhook d'une équipe Microsoft, qui est une URL unique de ce point de terminaison fournie par l'assistant. Vos développeurs peuvent consulter l'article [Prise en main des connecteurs Office 365 pour Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855783), sur la page Microsoft Developer Network, pour obtenir des instructions détaillées et des exemples de connecteur. D'autres ressources telles que l'article [Connecter aux applications à vos groupes dans Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) et le [Centre de développement Office de Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784) sont également disponibles.
