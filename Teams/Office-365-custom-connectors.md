---
title: Utiliser Microsoft 365 et des connecteurs personnalisés
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
ms.openlocfilehash: 908469913944aea2a27feb8a35b0e5e5620aae3f
ms.sourcegitcommit: 44de1da5617f57f8c37780ad3451c0128f60b1f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50076416"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>Utiliser Microsoft 365 et des connecteurs personnalisés dans Microsoft Teams
=======================================================

Les connecteurs vous aideront à maintenir votre équipe à jour en leur adant directement dans un canal le contenu fréquemment utilisé et les mises à jour de service. Avec les connecteurs, les utilisateurs de Microsoft Teams peuvent recevoir des mises à jour de services populaires tels que Trello, Wunderlist, GitHub et Azure DevOps Services dans le flux de conversation de leur équipe.

Tout membre d’une équipe peut connecter son équipe aux services cloud populaires avec les connecteurs si les autorisations de l’équipe le permettent et tous les membres de l’équipe sont informés des activités de ce service. Les connecteurs continueront à fonctionner même après le membre qui a initialement configuré le connecteur gauche. Tout membre de l’équipe autorisée à ajouter\supprimer peut modifier la configuration des connecteurs par les autres membres.

Les connecteurs Microsoft 365 peuvent être utilisés avec Microsoft Teams et les groupes Microsoft 365, ce qui permet à tous les membres de rester synchronisés et de recevoir rapidement les informations pertinentes. Microsoft Teams et Exchange utilisent le même modèle de connecteur, ce qui vous permet d’utiliser les mêmes connecteurs sur les deux plateformes. Il est toutefois utile de noter que la désactivation des connecteurs pour le groupe Microsoft 365 dont dépend une équipe désactivera la possibilité de créer des connecteurs pour cette équipe également.

<a name="add-a-connector-to-a-channel"></a>Ajouter un connecteur à un canal
----------------------------

Pour l’instant, vous pouvez ajouter des connecteurs à l’aide des clients de bureau et web de Microsoft Teams. Toutefois, les informations publiées par ces connecteurs peuvent être affichées dans **tous les clients, y compris** les appareils mobiles.

1. Pour ajouter un connecteur à un canal, cliquez sur les **ellipses (...),** à droite du nom d’un canal, puis cliquez **sur Connecteurs.**

    > [!div class="mx-imgBorder"]
    > ![Capture d’écran de l’interface de Teams avec l’option Connecteurs sélectionnée.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. Vous pouvez sélectionner parmi une série de connecteurs disponibles, puis cliquer sur **Ajouter.**

    > [!div class="mx-imgBorder"]
    > ![Capture d’écran de la boîte de dialogue Connecteurs affichant les connecteurs disponibles](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. Renseignez les informations requises pour le connecteur sélectionné et cliquez sur **Enregistrer**. Chaque connecteur nécessite un ensemble d'informations pour fonctionner correctement et certains peuvent également requérir l'ouverture d'une session au service à l'aide des liens fournis dans la page de configuration du connecteur.

    > [!div class="mx-imgBorder"]
    > ![Capture d'écran de la page de configuration du connecteur RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. Les données fournies par le connecteur sont automatiquement publiées dans le canal.

    > [!div class="mx-imgBorder"]
    > ![Capture d'écran de l'interface Teams affichant une conversation dans un canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> **Notification de mise à jour d’URL de connecteur**
>
> Les connecteurs Teams sont en cours de transition vers une nouvelle URL pour renforcer la sécurité. Au cours de cette transition, vous recevrez certaines notifications de mise à jour du connecteur configuré pour utiliser la nouvelle URL. Il est vivement recommandé de mettre à jour votre connecteur immédiatement pour éviter toute interruption des services de connecteur. Pour mettre à jour l’URL, vous devez suivre les étapes suivantes :
> 1. Dans la page de configuration des connecteurs, un message « Attention requise » s’affiche sous le bouton « Gérer » pour les connexions qui doivent être mises à jour.
> ![Capture d’écran du message « Attention requise ».](media/Teams_Attention_Required_message.png)
> 2. Pour les connecteurs d’espace web entrants, les utilisateurs peuvent recréer la connexion en sélectionnant simplement Mettre à jour **l’URL** et en utilisant l’URL de site web nouvellement générée.
> ![Capture d’écran du bouton « Mettre à jour l’URL ».](media/Teams_update_URL_button.png)
> 3. Pour les autres types de connecteurs, l’utilisateur doit supprimer le connecteur et recréer la configuration du connecteur.
> 4. Un message « URL est à jour » s’affichera une fois l’URL correctement mise à jour.
> ![Capture d’écran du message « L’URL est à jour ».](media/Teams_URL_up_to_date.png)


<a name="develop-custom-connectors"></a>Développer des connecteurs personnalisés
----------------------------

Vous pouvez également créer des connecteurs personnalisés, ainsi que des sites web entrants et sortants. Pour plus d’informations, consultez notre [documentation sur les développeurs](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).
