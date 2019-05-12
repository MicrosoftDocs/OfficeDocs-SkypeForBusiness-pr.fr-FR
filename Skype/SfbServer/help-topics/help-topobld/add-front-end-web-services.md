---
title: Ajouter des services web frontaux
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
ms.openlocfilehash: fc67ed792ab121bc4a9aaa0c72bcf764a2dadf1d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897683"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="def8f-104">Ajouter des services web frontaux</span><span class="sxs-lookup"><span data-stu-id="def8f-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="def8f-105">L’URL de base correspond à l’identité des services web pour l’URL, moins https://.</span><span class="sxs-lookup"><span data-stu-id="def8f-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="def8f-106">Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="def8f-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="def8f-107">Impossible de remplacer l’interne des Services Web pool nom de domaine complet (FQDN) pour un serveur Standard Edition server.</span><span class="sxs-lookup"><span data-stu-id="def8f-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="def8f-108">Si vous configurez le nom de domaine DNS (Domain Name System) équilibrage de charge pour un pool frontal Enterprise Edition, vous pouvez spécifier une autre URL base interne, qui doit être différente de celui du pool (par exemple, interne -\<votre URL de base\>).</span><span class="sxs-lookup"><span data-stu-id="def8f-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="def8f-109">Vous pouvez spécifier une URL de base externe qui est différente de votre URL interne de base pour différencier les noms de domaines.</span><span class="sxs-lookup"><span data-stu-id="def8f-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="def8f-110">Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com.</span><span class="sxs-lookup"><span data-stu-id="def8f-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="def8f-111">Vous définissez l’URL de base externe en utilisant le nom de domaine contoso.com.</span><span class="sxs-lookup"><span data-stu-id="def8f-111">You would define the external base URL using the contoso.com domain name.</span></span> <span data-ttu-id="def8f-112">Ceci est important pour les serveurs proxy inverse pour un déploiement de serveur edge.</span><span class="sxs-lookup"><span data-stu-id="def8f-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="def8f-113">Le nom de domaine d’URL base externe doit être le même que le nom de domaine du nom de domaine complet du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="def8f-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="def8f-114">Messagerie instantanée et présence requiert l’accès HTTP au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="def8f-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

