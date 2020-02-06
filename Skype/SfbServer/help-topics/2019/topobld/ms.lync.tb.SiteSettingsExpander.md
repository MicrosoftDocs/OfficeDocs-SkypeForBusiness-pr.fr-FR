---
title: Expandeur des paramètres du site du serveur Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Pour modifier les propriétés d’un site existant, procédez comme suit :'
ms.openlocfilehash: a8240030bd05ae865cb54343a460c8be414546a3
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798291"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="812bd-103">Expandeur des paramètres du site du serveur Lync</span><span class="sxs-lookup"><span data-stu-id="812bd-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="812bd-104">Pour modifier les propriétés d’un site existant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="812bd-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="812bd-105">Propriétés du site</span><span class="sxs-lookup"><span data-stu-id="812bd-105">Site properties</span></span>

<span data-ttu-id="812bd-106">Dans les propriétés du site, vous pouvez modifier ou modifier le nom du site (obligatoire), la description (facultatif), la ville (facultatif), l’État ou la province (facultatif) et le code de pays/région (facultatif).</span><span class="sxs-lookup"><span data-stu-id="812bd-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="812bd-107">Pour plus d’informations sur les propriétés de site, voir [Ajouter des sites de succursales à votre topologie](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span><span class="sxs-lookup"><span data-stu-id="812bd-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="812bd-108">Propriétés d’itinéraire de Fédération</span><span class="sxs-lookup"><span data-stu-id="812bd-108">Federation Route properties</span></span>

<span data-ttu-id="812bd-109">Pour définir une affectation de l’itinéraire de Fédération de site, vous devez d’abord disposer de la Fédération sur un serveur Edge ou un pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="812bd-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="812bd-110">Si la Fédération n’est pas activée sur un serveur Edge ou un pool, les paramètres d’attribution de l’itinéraire de Fédération pour le site ne seront pas disponibles à des fins de modification.</span><span class="sxs-lookup"><span data-stu-id="812bd-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="812bd-111">Si le paramètre de Fédération sur le serveur Edge ou le pool a été configuré, sélectionnez **activer** au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="812bd-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="812bd-112">Sélectionnez ensuite une arête ou un réalisateur dans la liste déroulante à définir comme itinéraire de Fédération.</span><span class="sxs-lookup"><span data-stu-id="812bd-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="812bd-113">Ce paramètre affecte tous les sites.</span><span class="sxs-lookup"><span data-stu-id="812bd-113">This setting will affect all sites.</span></span> <span data-ttu-id="812bd-114">Assurez-vous que le paramètre que vous configurez sur ce site est approprié pour tous les sites.</span><span class="sxs-lookup"><span data-stu-id="812bd-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="812bd-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="812bd-115">See also</span></span>

<span data-ttu-id="812bd-116">Pour plus d’informations, reportez-vous à la rubrique [topologies pour l’accès des utilisateurs externes](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span><span class="sxs-lookup"><span data-stu-id="812bd-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>


