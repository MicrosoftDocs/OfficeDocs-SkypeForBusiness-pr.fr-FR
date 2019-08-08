---
title: Utiliser des connecteurs Office 365 et personnalisés dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: Les connecteurs permettent à votre équipe de rester informée en fournissant directement à votre canal du contenu et des mises à jour provenant des services que vous utilisez fréquemment.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a8235ce9eb950df0c04ab41949500a640376e612
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245207"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>Utiliser des connecteurs Office 365 et personnalisés dans Microsoft Teams
=======================================================

Les liens permettent de mettre à jour votre équipe en fournissant des mises à jour de contenu et de service fréquemment utilisées directement dans un canal. Les connecteurs permettent aux utilisateurs de Microsoft teams de recevoir des mises à jour de services populaires, tels que Twitter, Trello, Wunderlist, GitHub et Azure DevOps services dans le flux de conversation de leur équipe.

Tout membre d’une équipe peut relier son équipe aux services Cloud populaires avec les connecteurs si les autorisations de l’équipe le permettent, et tous les membres de l’équipe sont avertis des activités de ce service. Les connecteurs continuent de fonctionner même après que le membre qui a initialement configuré le connecteur est resté. Les membres d’une équipe disposant de l’autorisation d’ajout d’une fonction peuvent modifier les connecteurs configurés par d’autres membres.

Les connecteurs 365 Office peuvent être utilisés avec Microsoft teams et les groupes Office 365, ce qui permet à tous les membres de rester synchronisés et de recevoir rapidement des informations pertinentes. Microsoft teams et Exchange utilisent le même modèle de connecteur, ce qui vous permet d’utiliser les mêmes connecteurs dans les deux plateformes. Il est toutefois important de noter que la désactivation de connecteurs pour le groupe Office 365 dont dépend une équipe peut également désactiver la possibilité de créer des liens pour cette équipe.

<a name="add-a-connector-to-a-channel"></a>Ajouter un connecteur à un canal
----------------------------

Pour l’instant, vous pouvez ajouter des connecteurs à l’aide des clients de bureau et Web Microsoft Teams. Toutefois, les informations publiées par ces connecteurs peuvent être affichées dans **tous les clients** , y compris sur les appareils mobiles.

1. Pour ajouter un connecteur à un canal, cliquez sur les **points de suspension (...),** à droite du nom d’un canal, puis cliquez sur **connecteurs**.

    ![Capture d’écran de l’interface équipes avec l’option connecteurs sélectionnée](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. Vous pouvez choisir parmi un large éventail de connecteurs disponibles, puis cliquez sur **Ajouter**.

    ![Capture d’écran de la boîte de dialogue connecteurs montrant les connecteurs disponibles.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. Renseignez les informations requises pour le connecteur sélectionné et cliquez sur **Enregistrer**. Chaque connecteur nécessite un ensemble d'informations pour fonctionner correctement et certains peuvent également requérir l'ouverture d'une session au service à l'aide des liens fournis dans la page de configuration du connecteur.

    ![Capture d'écran de la page de configuration du connecteur RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. Les données fournies par le connecteur sont automatiquement publiées dans le canal.

    ![Capture d'écran de l'interface Teams affichant une conversation dans un canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>Développer des connecteurs personnalisés
-----------------------------

Il est très facile de développer des connecteurs personnalisés qui peuvent être intégrés à vos applications métier. Pour créer un point de terminaison d' **** un canal qui collecte des données à partir de n’importe quelle application à l’aide de méthodes http post, vous pouvez utiliser le connecteur webhook intégré.

1. Ajoutez le **webhook entrant** comme tout autre connecteur.

    ![Capture d'écran avec l'option d'ajout du connecteur Webhook entrant.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2. Pour créer un webhook, spécifiez un **nom**, mettez à jour l'image du webhook si nécessaire et cliquez sur **Créer**.

    ![Capture d’écran de la page de configuration pour le connecteur webhook entrant.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3. Les applications qui envoient des données à ce canal nécessitent l’URL du connecteur webhook. Une URL unique est créée lors de la création du webhook. Partagez cette URL avec vos développeurs de sorte qu’ils puissent configurer leurs applications en fonction de la transmission des données, le cas échéant.

    ![Capture d'écran de l'URL unique du Webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4. Lorsqu'une application externe envoie des données vers un connecteur, le message s'affiche dans la liste de conversations du canal sous forme de message spécial appelé **Carte de connecteur**.

    ![Capture d'écran de l'interface Teams affichant un message Carte de connecteur.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

     Les développeurs peuvent configurer leurs applications de manière à ce qu’elles créent ces cartes en envoyant une requête HTTP avec une charge utile JSON simple à l’adresse webhook d’une équipe, qui est une URL unique de ce point de terminaison fourni par l’Assistant. Faites en sorte que vos développeurs se réfèrent à la [prise en main de connecteurs Office 365 pour Microsoft teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), sur le réseau de développement Microsoft, qui comporte des instructions détaillées et des exemples de connecteurs. D’autres ressources incluent [connecter des applications à vos groupes dans Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) et le [Centre de développement Office-Microsoft teams](https://go.microsoft.com/fwlink/?linkid=855784).
