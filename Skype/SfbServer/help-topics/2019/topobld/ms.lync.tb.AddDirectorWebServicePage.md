---
title: 'Service web : ajouter un directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
ms.openlocfilehash: 816ba625db8a2665d706a38c8a4a7d99544ad87e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889121"
---
# <a name="add-director-web-service"></a><span data-ttu-id="5d98d-104">Service web : ajouter un directeur</span><span class="sxs-lookup"><span data-stu-id="5d98d-104">Add Director Web Service</span></span>
 
<span data-ttu-id="5d98d-105">L’URL de base correspond à l’identité des services web pour l’URL, moins https://.</span><span class="sxs-lookup"><span data-stu-id="5d98d-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="5d98d-106">Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="5d98d-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="5d98d-107">Impossible de remplacer le nom de domaine complet de pool (FQDN) des Services Web interne si vous déployez uniquement un directeur unique.</span><span class="sxs-lookup"><span data-stu-id="5d98d-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="5d98d-108">Si vous configurez une nom de domaine DNS (Domain Name System) équilibrage de charge pour le pool de directeurs, vous pouvez spécifier une autre base URL interne (qui doit être différent du nom de domaine complet du pool et peut être, par exemple, interne -\<votre URL de base\>).</span><span class="sxs-lookup"><span data-stu-id="5d98d-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="5d98d-109">Vous pouvez spécifier une URL de base externe qui est différente de votre URL interne de base pour différencier les noms de domaines.</span><span class="sxs-lookup"><span data-stu-id="5d98d-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="5d98d-110">Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5d98d-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="5d98d-111">Vous définissez l’URL de base externe en utilisant le nom de domaine contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5d98d-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="5d98d-112">Ceci est important pour les serveurs proxy inverse pour un déploiement de serveur edge.</span><span class="sxs-lookup"><span data-stu-id="5d98d-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="5d98d-113">Le nom de domaine d’URL base externe doit être le même que le nom de domaine du nom de domaine complet du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="5d98d-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

