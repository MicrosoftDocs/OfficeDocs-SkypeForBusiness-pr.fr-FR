---
title: Expandeur des paramètres du site du serveur Lync
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Pour modifier les propriétés d’un site existant, procédez comme suit :'
ms.openlocfilehash: 0c6caf08060a94836d0c14169e550634c26e7dc9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200122"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="219f6-103">Expandeur des paramètres du site du serveur Lync</span><span class="sxs-lookup"><span data-stu-id="219f6-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="219f6-104">Pour modifier les propriétés d’un site existant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="219f6-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="219f6-105">Propriétés du site</span><span class="sxs-lookup"><span data-stu-id="219f6-105">Site properties</span></span>

<span data-ttu-id="219f6-106">Dans les propriétés du site, vous pouvez changer ou modifier le nom (obligatoire) du site, Description (facultative), Ville (facultatif), Département/Province (facultative) et le Code de pays/région (facultatif).</span><span class="sxs-lookup"><span data-stu-id="219f6-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="219f6-107">Pour plus d’informations sur les propriétés du site, voir [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span><span class="sxs-lookup"><span data-stu-id="219f6-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="219f6-108">Propriétés des itinéraires de fédération</span><span class="sxs-lookup"><span data-stu-id="219f6-108">Federation Route properties</span></span>

<span data-ttu-id="219f6-109">Pour définir une attribution itinéraire fédération du site, vous devez au préalable avoir fédération activée sur un serveur Edge ou un pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="219f6-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="219f6-110">Si la fédération n’est pas activée sur un serveur Edge ou le pool, les paramètres d’affectation fédération itinéraire pour le site ne sera pas disponibles pour la modification.</span><span class="sxs-lookup"><span data-stu-id="219f6-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="219f6-111">Si le paramètre de fédération au pool ou serveur Edge a été configuré, sélectionnez **Activer** au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="219f6-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="219f6-112">Puis sélectionnez un contour ou un directeur dans la liste déroulante pour définir en tant que l’itinéraire de fédération.</span><span class="sxs-lookup"><span data-stu-id="219f6-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="219f6-113">Ce paramètre affecte tous les sites.</span><span class="sxs-lookup"><span data-stu-id="219f6-113">This setting will affect all sites.</span></span> <span data-ttu-id="219f6-114">N’oubliez pas que le paramètre que vous configurez sur ce site est approprié pour tous les sites.</span><span class="sxs-lookup"><span data-stu-id="219f6-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="219f6-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="219f6-115">See also</span></span>

<span data-ttu-id="219f6-116">Pour plus d’informations, voir [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span><span class="sxs-lookup"><span data-stu-id="219f6-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>


