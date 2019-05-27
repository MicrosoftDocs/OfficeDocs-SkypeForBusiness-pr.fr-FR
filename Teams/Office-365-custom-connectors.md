---
title: Utiliser des connecteurs Office 365 et personnalisés dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: Les connecteurs permettent à votre équipe de rester informée en fournissant directement à votre canal du contenu et des mises à jour provenant des services que vous utilisez fréquemment.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2167022e3187924f5283ab5bee3a6b220595fd64
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "34432855"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>Utiliser des connecteurs Office 365 et personnalisés dans Microsoft Teams
=======================================================

Les connecteurs permettent à votre équipe de rester informée en fournissant directement à votre canal du contenu et des mises à jour provenant des services que vous utilisez fréquemment. Les connecteurs permettent aux utilisateurs de Microsoft teams de recevoir des mises à jour de services populaires, tels que Twitter, Trello, Wunderlist, GitHub et Azure DevOps services dans le flux de conversation de leur équipe.

Tout membre d’une équipe peut relier son équipe aux services Cloud populaires avec les connecteurs si les autorisations de l’équipe le permettent, et tous les membres de l’équipe sont avertis des activités de ce service. Les connecteurs continuent de fonctionner même après que le membre qui a initialement configuré le connecteur est resté. Les membres d’une équipe disposant de l’autorisation d’ajout d’une fonction peuvent modifier les connecteurs configurés par d’autres membres.

Les connecteurs 365 Office peuvent être utilisés avec Microsoft teams et les groupes Office 365, ce qui permet à tous les membres de rester synchronisés et de recevoir rapidement des informations pertinentes. Microsoft teams et Exchange utilisent le même modèle de connecteur, ce qui vous permet d’utiliser les mêmes connecteurs dans les deux plateformes. Il est toutefois important de noter que la désactivation de connecteurs pour le groupe Office 365 dont dépend une équipe peut également désactiver la possibilité de créer des liens pour cette équipe.

Actuellement, les connecteurs peuvent être ajoutés à l'aide des clients de bureau et Web Microsoft Teams. Toutefois, les informations publiées par ces connecteurs peuvent être affichées à l'aide de **tous les clients** y compris mobiles.

1.  Pour ajouter un connecteur à un canal, cliquez sur les **points de suspension (…),** à droite du nom du canal, puis sur **Connecteurs.**

    ![Capture d’écran de l’interface équipes avec l’option connecteurs sélectionnée](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  Les utilisateurs peuvent effectuer une sélection parmi divers connecteurs disponibles, puis cliquer sur **Ajouter**.

    ![Capture d’écran de la boîte de dialogue connecteurs montrant les connecteurs disponibles.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

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

    ![Capture d’écran de la page de configuration pour le connecteur webhook entrant.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  Les applications qui envoient des données vers ce canal requièrent l'URL du connecteur webhook. Une **URL unique** est créée lors de la création du **webhook**. Partagez cette URL avec vos développeurs, pour leur permettre de configurer leurs applications pour envoyer des données lorsque nécessaire.

    ![Capture d'écran de l'URL unique du Webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  Lorsqu'une application externe envoie des données vers un connecteur, le message s'affiche dans la liste de conversations du canal sous forme de message spécial appelé **Carte de connecteur**.

    ![Capture d'écran de l'interface Teams affichant un message Carte de connecteur.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

Les développeurs peuvent configurer leurs applications pour créer ces cartes, en envoyant une demande HTTP avec une charge JSON simple à l'adresse de webhook d'une équipe Microsoft, qui est une URL unique de ce point de terminaison fournie par l'assistant. Vos développeurs peuvent consulter l'article [Prise en main des connecteurs Office 365 pour Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), sur la page Microsoft Developer Network, pour obtenir des instructions détaillées et des exemples de connecteur. D'autres ressources telles que l'article [Connecter aux applications à vos groupes dans Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) et le [Centre de développement Office de Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784) sont également disponibles.
