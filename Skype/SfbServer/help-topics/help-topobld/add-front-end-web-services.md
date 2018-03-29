---
title: Ajouter des Services Web Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
ms.openlocfilehash: 6626bb14221aaa909219451d26b76b0cd15bc576
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="2b06d-104">Ajouter des Services Web Front-End</span><span class="sxs-lookup"><span data-stu-id="2b06d-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="2b06d-105">L’URL de base correspond à l’identité des services web pour l’URL, moins https://.</span><span class="sxs-lookup"><span data-stu-id="2b06d-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="2b06d-106">Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="2b06d-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="2b06d-107">Vous ne pouvez pas substituer l’interne des Services Web pool nom de domaine complet (FQDN) d’un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2b06d-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="2b06d-108">Si vous configurez le système de nom de domaine (DNS) équilibrage de charge pour un pool Enterprise Edition Front-End, vous pouvez spécifier une autre URL base interne, qui doit être différente du nom de domaine complet du pool (par exemple, interne -\<votre URL de base de\>).</span><span class="sxs-lookup"><span data-stu-id="2b06d-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="2b06d-109">Vous pouvez spécifier une URL de base externe qui est différente de votre URL de base interne pour différencier les noms de domaines.</span><span class="sxs-lookup"><span data-stu-id="2b06d-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="2b06d-110">Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Vous définissez l’URL externe de base en utilisant le nom de domaine de contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2b06d-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL using the contoso.com domain name.</span></span> <span data-ttu-id="2b06d-111">Ceci est important pour les serveurs proxy inverse pour un déploiement de bord.</span><span class="sxs-lookup"><span data-stu-id="2b06d-111">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="2b06d-112">Le nom de domaine base URL externe doit être le même que le nom de domaine de nom de domaine complet du serveur proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="2b06d-112">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="2b06d-113">La messagerie instantanée et présence requiert l’accès HTTP au pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="2b06d-113">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

