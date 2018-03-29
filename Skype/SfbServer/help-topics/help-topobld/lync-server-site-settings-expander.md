---
title: Développement de paramètres de Site Lync Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Pour modifier les propriétés d’un site existant, effectuez le des opérations suivantes :'
ms.openlocfilehash: 6ae0154da4e53cffb9d0b6bb02a2eda3cb0cbaa8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="fa1d5-103">Développement de paramètres de Site Lync Server</span><span class="sxs-lookup"><span data-stu-id="fa1d5-103">Lync Server Site Settings Expander</span></span>
 
<span data-ttu-id="fa1d5-104">Pour modifier les propriétés d’un site existant, effectuez le des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="fa1d5-104">To edit the properties of an existing site, do the following:</span></span>
  
## 

### <a name="site-properties"></a><span data-ttu-id="fa1d5-105">Propriétés du site</span><span class="sxs-lookup"><span data-stu-id="fa1d5-105">Site properties</span></span>

<span data-ttu-id="fa1d5-106">Dans les propriétés du site, vous pouvez modifier ou modifier le site nom (obligatoire), Description (facultative), Ville (facultatif), État/Province (facultative) et le Code de pays/région (facultatif).</span><span class="sxs-lookup"><span data-stu-id="fa1d5-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>
  
<span data-ttu-id="fa1d5-107">Pour plus d’informations sur les propriétés du site, consultez [Ajout de Sites à la topologie de votre branche](http://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span><span class="sxs-lookup"><span data-stu-id="fa1d5-107">For details about site properties, see [Add Branch Sites to Your Topology](http://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>
  
### <a name="federation-route-properties"></a><span data-ttu-id="fa1d5-108">Propriétés d’itinéraire de fédération</span><span class="sxs-lookup"><span data-stu-id="fa1d5-108">Federation Route properties</span></span>

<span data-ttu-id="fa1d5-109">Pour définir une affectation d’itinéraire de fédération site, vous devez avoir activé sur un serveur Edge ou un pool de serveur de transport Edge de fédération.</span><span class="sxs-lookup"><span data-stu-id="fa1d5-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="fa1d5-110">Si la fédération n’est pas activée sur un serveur Edge ou du pool, les paramètres d’affectation de gamme fédération pour le site ne sera pas disponibles pour la modification.</span><span class="sxs-lookup"><span data-stu-id="fa1d5-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>
  
<span data-ttu-id="fa1d5-111">Si le paramètre de fédération au niveau du serveur Edge ou du pool a été configuré, sélectionnez **Activer** au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="fa1d5-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="fa1d5-112">Puis sélectionnez une arête ou un directeur à partir de la liste déroulante pour définir que l’itinéraire de fédération.</span><span class="sxs-lookup"><span data-stu-id="fa1d5-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="fa1d5-113">Ce paramètre affecte tous les sites.</span><span class="sxs-lookup"><span data-stu-id="fa1d5-113">This setting will affect all sites.</span></span> <span data-ttu-id="fa1d5-114">Assurez-vous que le paramètre que vous configurez sur ce site est approprié pour tous les sites.</span><span class="sxs-lookup"><span data-stu-id="fa1d5-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span> 
  
### 

<span data-ttu-id="fa1d5-115">Pour plus d’informations, consultez [Topologies pour l’accès des utilisateurs externes](http://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span><span class="sxs-lookup"><span data-stu-id="fa1d5-115">For details, see [Topologies for External User Access](http://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>
  

