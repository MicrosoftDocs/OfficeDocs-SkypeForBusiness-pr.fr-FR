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
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: Les connecteurs permettent à votre équipe de rester informée en fournissant directement à votre canal du contenu et des mises à jour provenant des services que vous utilisez fréquemment.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 05f892791c3f299cbd146d7a34b0062cc957486f
ms.sourcegitcommit: dc70fd277d9542d831741e14dba9ae22367210ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909330"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="9b696-103">Utiliser des connecteurs Office 365 et personnalisés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9b696-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="9b696-p101">Les liens permettent de mettre à jour votre équipe en fournissant des mises à jour de contenu et de service fréquemment utilisées directement dans un canal. Les connecteurs permettent aux utilisateurs de Microsoft teams de recevoir des mises à jour de services populaires, tels que Twitter, Trello, Wunderlist, GitHub et Azure DevOps services dans le flux de conversation de leur équipe.</span><span class="sxs-lookup"><span data-stu-id="9b696-p101">Connectors keep your team current by delivering frequently used content and service updates directly into a channel. With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="9b696-106">Tout membre d’une équipe peut relier son équipe aux services Cloud populaires avec les connecteurs si les autorisations de l’équipe le permettent, et tous les membres de l’équipe sont avertis des activités de ce service.</span><span class="sxs-lookup"><span data-stu-id="9b696-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="9b696-107">Les connecteurs continuent de fonctionner même après que le membre qui a initialement configuré le connecteur est resté.</span><span class="sxs-lookup"><span data-stu-id="9b696-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="9b696-108">Les membres d’une équipe disposant de l’autorisation d’ajout d’une fonction peuvent modifier les connecteurs configurés par d’autres membres.</span><span class="sxs-lookup"><span data-stu-id="9b696-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="9b696-109">Les connecteurs 365 Office peuvent être utilisés avec Microsoft teams et les groupes Office 365, ce qui permet à tous les membres de rester synchronisés et de recevoir rapidement des informations pertinentes.</span><span class="sxs-lookup"><span data-stu-id="9b696-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="9b696-110">Microsoft teams et Exchange utilisent le même modèle de connecteur, ce qui vous permet d’utiliser les mêmes connecteurs dans les deux plateformes.</span><span class="sxs-lookup"><span data-stu-id="9b696-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="9b696-111">Il est toutefois important de noter que la désactivation de connecteurs pour le groupe Office 365 dont dépend une équipe peut également désactiver la possibilité de créer des liens pour cette équipe.</span><span class="sxs-lookup"><span data-stu-id="9b696-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="9b696-112">Ajouter un connecteur à un canal</span><span class="sxs-lookup"><span data-stu-id="9b696-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="9b696-113">Pour l’instant, vous pouvez ajouter des connecteurs à l’aide des clients de bureau et Web Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9b696-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="9b696-114">Toutefois, les informations publiées par ces connecteurs peuvent être affichées dans **tous les clients** , y compris sur les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="9b696-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="9b696-115">Pour ajouter un connecteur à un canal, cliquez sur les **points de suspension (...),** à droite du nom d’un canal, puis cliquez sur **connecteurs**.</span><span class="sxs-lookup"><span data-stu-id="9b696-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![Capture d’écran de l’interface équipes avec l’option connecteurs sélectionnée](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="9b696-117">Vous pouvez choisir parmi un large éventail de connecteurs disponibles, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="9b696-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![Capture d’écran de la boîte de dialogue connecteurs montrant les connecteurs disponibles.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="9b696-p105">Renseignez les informations requises pour le connecteur sélectionné et cliquez sur **Enregistrer**. Chaque connecteur nécessite un ensemble d'informations pour fonctionner correctement et certains peuvent également requérir l'ouverture d'une session au service à l'aide des liens fournis dans la page de configuration du connecteur.</span><span class="sxs-lookup"><span data-stu-id="9b696-p105">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![Capture d'écran de la page de configuration du connecteur RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="9b696-122">Les données fournies par le connecteur sont automatiquement publiées dans le canal.</span><span class="sxs-lookup"><span data-stu-id="9b696-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Capture d'écran de l'interface Teams affichant une conversation dans un canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="9b696-124">Développer des connecteurs personnalisés</span><span class="sxs-lookup"><span data-stu-id="9b696-124">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="9b696-125">Vous pouvez également créer des connecteurs personnalisés ainsi que des raccordements Web entrants et sortants.</span><span class="sxs-lookup"><span data-stu-id="9b696-125">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="9b696-126">Pour plus d’informations, consultez [la documentation du développeur](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) .</span><span class="sxs-lookup"><span data-stu-id="9b696-126">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
