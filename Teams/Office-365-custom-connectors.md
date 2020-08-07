---
title: Utiliser Microsoft 365 et les connecteurs personnalisés
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Les connecteurs permettent à votre équipe de rester informée en fournissant directement à votre canal du contenu et des mises à jour provenant des services que vous utilisez fréquemment.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e704dd6a9a796be4f9e361972cd2e6b38e48ce51
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582471"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>Utiliser Microsoft 365 et les connecteurs personnalisés de Microsoft teams
=======================================================

Les liens permettent de mettre à jour votre équipe en fournissant des mises à jour de contenu et de service fréquemment utilisées directement dans un canal. Les connecteurs permettent aux utilisateurs de Microsoft teams de recevoir des mises à jour de services populaires, tels que Twitter, Trello, Wunderlist, GitHub et Azure DevOps services dans le flux de conversation de leur équipe.

Tout membre d’une équipe peut relier son équipe aux services Cloud populaires avec les connecteurs si les autorisations de l’équipe le permettent, et tous les membres de l’équipe sont avertis des activités de ce service. Les connecteurs continuent de fonctionner même après que le membre qui a initialement configuré le connecteur est resté. Les membres d’une équipe disposant de l’autorisation d’ajout d’une fonction peuvent modifier les connecteurs configurés par d’autres membres.

Les connecteurs Microsoft 365 peuvent être utilisés avec Microsoft teams et les groupes Microsoft 365, ce qui permet à tous les membres de rester synchronisés et de recevoir rapidement des informations pertinentes. Microsoft teams et Exchange utilisent le même modèle de connecteur, ce qui vous permet d’utiliser les mêmes connecteurs dans les deux plateformes. Il est toutefois important de noter que la désactivation de connecteurs pour le groupe Microsoft 365 dont dépend une équipe entraîne la désactivation de la possibilité de créer des liens pour cette équipe.

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
----------------------------

Vous pouvez également créer des connecteurs personnalisés ainsi que des raccordements Web entrants et sortants. Pour plus d’informations, consultez notre [documentation sur les développeurs](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).
