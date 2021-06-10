---
title: Utiliser des Microsoft 365 et des connecteurs personnalisés
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
description: Avec les connecteurs, votre équipe reste au courant des dernières activités, en leur fournissant directement dans un canal du contenu et des mises à jour de services que vous utilisez fréquemment.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77b1c99847ca35de51af5e062593a29c18e98999
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855793"
---
# <a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="5d044-103">Utiliser des Microsoft 365 et des connecteurs personnalisés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d044-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>

<span data-ttu-id="5d044-104">Les connecteurs vous aideront à maintenir votre équipe à jour en leur adant le contenu fréquemment utilisé et les mises à jour de service directement dans un canal.</span><span class="sxs-lookup"><span data-stu-id="5d044-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="5d044-105">Avec les connecteurs, vos utilisateurs Microsoft Teams peuvent recevoir des mises à jour de services populaires tels que Trello, Wunderlist, GitHub et Azure DevOps Services dans le flux de conversation de leur équipe.</span><span class="sxs-lookup"><span data-stu-id="5d044-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="5d044-106">Tout membre d’une équipe peut connecter son équipe aux services cloud populaires avec les connecteurs si les autorisations d’équipe le permettent et tous les membres de l’équipe sont informés des activités de ce service.</span><span class="sxs-lookup"><span data-stu-id="5d044-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="5d044-107">Les connecteurs continueront à fonctionner même après le membre qui a initialement configuré le connecteur gauche.</span><span class="sxs-lookup"><span data-stu-id="5d044-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="5d044-108">Tout membre de l’équipe autorisée à ajouter\supprimer peut modifier la configuration des connecteurs par les autres membres.</span><span class="sxs-lookup"><span data-stu-id="5d044-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="5d044-109">Microsoft 365 connecteurs peuvent être utilisés avec les groupes Microsoft Teams et Microsoft 365, ce qui permet à tous les membres de rester synchronisés et de recevoir rapidement des informations pertinentes.</span><span class="sxs-lookup"><span data-stu-id="5d044-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members to stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="5d044-110">Les Microsoft Teams et Exchange utilisent le même modèle de connecteur, ce qui vous permet d’utiliser les mêmes connecteurs sur les deux plateformes.</span><span class="sxs-lookup"><span data-stu-id="5d044-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="5d044-111">Il est toutefois intéressant de noter que la désactivation des connecteurs pour le groupe Microsoft 365 dont dépend une équipe désactivera également la possibilité de créer des connecteurs pour cette équipe.</span><span class="sxs-lookup"><span data-stu-id="5d044-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

> [!NOTE]
> <span data-ttu-id="5d044-112">Les connecteurs sont désactivés par défaut dans Cloud de la communauté du secteur public environnements.</span><span class="sxs-lookup"><span data-stu-id="5d044-112">Connectors are disabled by default in GCC environments.</span></span> <span data-ttu-id="5d044-113">Si vous avez besoin de les activer, définissez les paramètres ConnectorsEnabled ou ConnectorsEnabledForTeams sur $true avec l’cmdlet [Set-OrganizationConfig.](/powershell/module/exchange/set-organizationconfig)</span><span class="sxs-lookup"><span data-stu-id="5d044-113">If you need to enable them, set the ConnectorsEnabled or ConnectorsEnabledForTeams parameters to $true with the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet.</span></span> <span data-ttu-id="5d044-114">Auparavant, vous [devrez vous connecter Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="5d044-114">You previously need to [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="5d044-115">Les connecteurs sont désactivés par défaut dans les environnements Cloud Community Administration (Cloud de la communauté du secteur public).</span><span class="sxs-lookup"><span data-stu-id="5d044-115">Connectors are disabled by default in the Government Cloud Community (GCC) environments.</span></span> <span data-ttu-id="5d044-116">Si vous avez besoin de les activer, définissez les paramètres ConnectorsEnabled ou ConnectorsEnabledForTeams sur $true avec l’cmdlet [SetOrganizationConfig.](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="5d044-116">If you need to enable them, set the ConnectorsEnabled or ConnectorsEnabledForTeams parameters to $true with the [SetOrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) cmdlet.</span></span> <span data-ttu-id="5d044-117">Auparavant, vous devaient vous connecter [à Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="5d044-117">You previously needed to connect to the [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="add-a-connector-to-a-channel"></a><span data-ttu-id="5d044-118">Ajouter un connecteur à un canal</span><span class="sxs-lookup"><span data-stu-id="5d044-118">Add a connector to a channel</span></span>

<span data-ttu-id="5d044-119">Pour l’instant, vous pouvez ajouter des connecteurs à l’aide Microsoft Teams clients de bureau et Web.</span><span class="sxs-lookup"><span data-stu-id="5d044-119">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="5d044-120">Toutefois, les informations publiées par ces connecteurs peuvent être affichées dans **tous les clients, y compris** les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="5d044-120">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="5d044-121">Pour ajouter un connecteur à un canal, cliquez sur les **ellipses (...),** à droite du nom d’un canal, puis cliquez **sur Connecteurs.**</span><span class="sxs-lookup"><span data-stu-id="5d044-121">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d044-122">![Capture d’écran Teams l’interface utilisateur avec l’option Connecteurs sélectionnée.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="5d044-122">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="5d044-123">Vous pouvez sélectionner parmi une série de connecteurs disponibles, puis cliquer sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="5d044-123">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d044-124">![Capture d’écran de la boîte de dialogue Connecteurs affichant les connecteurs disponibles](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="5d044-124">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="5d044-p107">Renseignez les informations requises pour le connecteur sélectionné et cliquez sur **Enregistrer**. Chaque connecteur nécessite un ensemble d'informations pour fonctionner correctement et certains peuvent également requérir l'ouverture d'une session au service à l'aide des liens fournis dans la page de configuration du connecteur.</span><span class="sxs-lookup"><span data-stu-id="5d044-p107">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d044-127">![Capture d'écran de la page de configuration du connecteur RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="5d044-127">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="5d044-128">Les données fournies par le connecteur sont automatiquement publiées dans le canal.</span><span class="sxs-lookup"><span data-stu-id="5d044-128">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d044-129">![Capture d'écran de l'interface Teams affichant une conversation dans un canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="5d044-129">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="5d044-130">**Notification de mise à jour d’URL de connecteur**</span><span class="sxs-lookup"><span data-stu-id="5d044-130">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="5d044-131">Les Teams connecteurs sont en cours de transition vers une nouvelle URL pour renforcer la sécurité.</span><span class="sxs-lookup"><span data-stu-id="5d044-131">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="5d044-132">Au cours de cette transition, vous recevrez certaines notifications de mise à jour du connecteur configuré pour utiliser la nouvelle URL.</span><span class="sxs-lookup"><span data-stu-id="5d044-132">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="5d044-133">Il est vivement recommandé de mettre à jour votre connecteur immédiatement pour éviter toute interruption des services de connecteur.</span><span class="sxs-lookup"><span data-stu-id="5d044-133">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="5d044-134">Pour mettre à jour l’URL, vous devez suivre les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="5d044-134">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="5d044-135">Dans la page de configuration des connecteurs, un message « Attention requise » s’affiche sous le bouton « Gérer » pour les connexions qui doivent être mises à jour.</span><span class="sxs-lookup"><span data-stu-id="5d044-135">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="5d044-136">![Capture d’écran du message « Attention requise ».](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="5d044-136">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="5d044-137">Pour les connecteurs de site web entrants, les utilisateurs peuvent recréer la connexion en sélectionnant simplement Mettre à jour **l’URL** et en utilisant l’URL de site web nouvellement générée.</span><span class="sxs-lookup"><span data-stu-id="5d044-137">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="5d044-138">![Capture d’écran du bouton « Mettre à jour l’URL ».](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="5d044-138">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="5d044-139">Pour les autres types de connecteurs, l’utilisateur doit supprimer le connecteur et recréer la configuration du connecteur.</span><span class="sxs-lookup"><span data-stu-id="5d044-139">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="5d044-140">Un message « L’URL est à jour » s’affichera une fois l’URL correctement mise à jour.</span><span class="sxs-lookup"><span data-stu-id="5d044-140">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="5d044-141">![Capture d’écran du message « L’URL est à jour ».](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="5d044-141">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


## <a name="develop-custom-connectors"></a><span data-ttu-id="5d044-142">Développer des connecteurs personnalisés</span><span class="sxs-lookup"><span data-stu-id="5d044-142">Develop custom connectors</span></span>


<span data-ttu-id="5d044-143">Vous pouvez également créer des connecteurs personnalisés, ainsi que des sites web entrants et sortants.</span><span class="sxs-lookup"><span data-stu-id="5d044-143">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="5d044-144">Pour plus d’informations, consultez notre [documentation sur les développeurs](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).</span><span class="sxs-lookup"><span data-stu-id="5d044-144">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
