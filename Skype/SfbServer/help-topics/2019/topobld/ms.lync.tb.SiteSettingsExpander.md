---
title: Expanseur des paramètres du site du serveur Lync
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour modifier les propriétés d’un site existant, procédez comme suit :'
ms.openlocfilehash: 4bcf07ef1b550fb96ce503f31b4026ccc4ae6960
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115374"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="27c4d-103">Expandeur des paramètres du site du serveur Lync</span><span class="sxs-lookup"><span data-stu-id="27c4d-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="27c4d-104">Pour modifier les propriétés d’un site existant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="27c4d-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="27c4d-105">Propriétés du site</span><span class="sxs-lookup"><span data-stu-id="27c4d-105">Site properties</span></span>

<span data-ttu-id="27c4d-106">Dans les propriétés du site, vous pouvez changer ou modifier le nom du site (obligatoire), la description (facultatif), la ville (facultatif), le département/province (facultatif) et le code pays/région (facultatif).</span><span class="sxs-lookup"><span data-stu-id="27c4d-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="27c4d-107">Pour plus d’informations sur les propriétés du site, voir [Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology).</span><span class="sxs-lookup"><span data-stu-id="27c4d-107">For details about site properties, see [Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="27c4d-108">Propriétés des itinéraires de fédération</span><span class="sxs-lookup"><span data-stu-id="27c4d-108">Federation Route properties</span></span>

<span data-ttu-id="27c4d-p101">Pour configurer l’itinéraire de fédération d’un site, vous devez d’abord activer la fédération sur le serveur Edge ou le pool de serveurs Edge. Si la fédération n’est pas activée sur un serveur ou un pool de serveurs Edge, il ne sera pas possible de modifier les paramètres d’affectation de l’itinéraire de fédération du site.</span><span class="sxs-lookup"><span data-stu-id="27c4d-p101">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool. If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="27c4d-p102">Si le paramètre de fédération du serveur ou pool de serveurs Edge a été configuré, sélectionnez **Activer** au niveau du site. Sélectionnez ensuite un serveur Edge ou un directeur dans la liste déroulante à configurer comme itinéraire de fédération.</span><span class="sxs-lookup"><span data-stu-id="27c4d-p102">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level. Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="27c4d-p103">Ce paramètre affectera tous les sites. Assurez-vous que le paramètre que vous configurez pour ce site s’adapte à tous les sites.</span><span class="sxs-lookup"><span data-stu-id="27c4d-p103">This setting will affect all sites. Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="27c4d-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="27c4d-115">See also</span></span>

<span data-ttu-id="27c4d-116">Pour plus d’informations, voir [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access).</span><span class="sxs-lookup"><span data-stu-id="27c4d-116">For details, see [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access).</span></span>