---
title: Ajouter des services web frontaux 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
ms.openlocfilehash: 48d2cc4c8ce9bc1074ae42e385265b34f24c662e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685127"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="f182c-104">Ajouter des services web frontaux 2010</span><span class="sxs-lookup"><span data-stu-id="f182c-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="f182c-105">L’URL de base correspond à l’identité des services web pour l’URL, moins https://.</span><span class="sxs-lookup"><span data-stu-id="f182c-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="f182c-106">Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="f182c-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="f182c-107">Vous ne pouvez pas remplacer le nom de domaine complet (FQDN) du pool de services Web interne pour un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="f182c-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="f182c-108">Si vous configurez l’équilibrage de charge DNS (Domain Name System) pour un pool frontal Enterprise Edition, vous pouvez spécifier une autre URL de base interne (qui doit être différente du nom de domaine complet du pool et peut-\<être, par exemple\>, une URL de base).</span><span class="sxs-lookup"><span data-stu-id="f182c-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="f182c-109">Vous pouvez spécifier une URL de base externe qui est différente de votre URL de base interne pour différencier le nom de domaine.</span><span class="sxs-lookup"><span data-stu-id="f182c-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="f182c-110">Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f182c-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="f182c-111">Vous devez définir l’URL de base externe à l’aide du nom de domaine contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f182c-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="f182c-112">C’est important pour les serveurs proxy inverse d’un déploiement Edge.</span><span class="sxs-lookup"><span data-stu-id="f182c-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="f182c-113">Le nom de domaine de l’URL de base externe doit être le même que le nom de domaine du nom de domaine complet (FQDN) du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="f182c-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="f182c-114">La messagerie instantanée et la présence nécessitent un accès HTTP au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="f182c-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

