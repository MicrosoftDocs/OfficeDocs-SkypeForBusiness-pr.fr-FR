---
title: 'Service web : ajouter un directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
ms.openlocfilehash: df8f6d88e57be2abd3c4a5081188f6e22849da0f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796553"
---
# <a name="add-director-web-service"></a><span data-ttu-id="dc868-104">Service web : ajouter un directeur</span><span class="sxs-lookup"><span data-stu-id="dc868-104">Add Director Web Service</span></span>
 
<span data-ttu-id="dc868-105">L’URL de base correspond à l’identité des services web pour l’URL, moins https://.</span><span class="sxs-lookup"><span data-stu-id="dc868-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="dc868-106">Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="dc868-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="dc868-107">Vous ne pouvez pas remplacer le nom de domaine complet (FQDN) du pool de services Web interne si vous déployez un seul directeur.</span><span class="sxs-lookup"><span data-stu-id="dc868-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="dc868-108">Si vous configurez un équilibrage de charge DNS (Domain Name System) pour la réserve de directeurs, vous pouvez spécifier une autre URL de base interne (qui doit être différente de celle du nom de domaine complet\<\>).</span><span class="sxs-lookup"><span data-stu-id="dc868-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="dc868-109">Vous pouvez spécifier une URL de base externe qui est différente de votre URL de base interne pour différencier le nom de domaine.</span><span class="sxs-lookup"><span data-stu-id="dc868-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="dc868-110">Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com.</span><span class="sxs-lookup"><span data-stu-id="dc868-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="dc868-111">Vous devez définir l’URL de base externe à l’aide du nom de domaine contoso.com.</span><span class="sxs-lookup"><span data-stu-id="dc868-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="dc868-112">C’est important pour les serveurs proxy inverse d’un déploiement Edge.</span><span class="sxs-lookup"><span data-stu-id="dc868-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="dc868-113">Le nom de domaine de l’URL de base externe doit être le même que le nom de domaine du nom de domaine complet (FQDN) du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="dc868-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

