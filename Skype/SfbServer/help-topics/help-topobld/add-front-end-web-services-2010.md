---
title: Ajouter des services web frontaux 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
ms.openlocfilehash: ab64d473c3b0493e7d578c5cfa9f55475d1d06ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897659"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="9293f-104">Ajouter des services web frontaux 2010</span><span class="sxs-lookup"><span data-stu-id="9293f-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="9293f-105">L’URL de base correspond à l’identité des services web pour l’URL, moins https://.</span><span class="sxs-lookup"><span data-stu-id="9293f-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="9293f-106">Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="9293f-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="9293f-107">Impossible de remplacer l’interne des Services Web pool nom de domaine complet (FQDN) pour un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="9293f-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="9293f-108">Si vous configurez le nom de domaine DNS (Domain Name System) équilibrage de charge pour un pool frontal Enterprise Edition, vous pouvez spécifier une autre base URL interne (qui doit être différent du nom de domaine complet du pool et peut être, par exemple, interne -\<votre URL de base\>).</span><span class="sxs-lookup"><span data-stu-id="9293f-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="9293f-109">Vous pouvez spécifier une URL de base externe qui est différente de votre URL interne de base pour différencier les noms de domaines.</span><span class="sxs-lookup"><span data-stu-id="9293f-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="9293f-110">Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9293f-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="9293f-111">Vous définissez l’URL de base externe en utilisant le nom de domaine contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9293f-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="9293f-112">Ceci est important pour les serveurs proxy inverse pour un déploiement de serveur edge.</span><span class="sxs-lookup"><span data-stu-id="9293f-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="9293f-113">Le nom de domaine d’URL base externe doit être le même que le nom de domaine du nom de domaine complet du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="9293f-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="9293f-114">Messagerie instantanée et présence requiert l’accès HTTP au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="9293f-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

