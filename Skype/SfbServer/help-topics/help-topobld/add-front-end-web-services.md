---
title: Ajouter des services web frontaux
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est , l’URL de https://pool01.contoso.net base est pool01.contoso.net.
ms.openlocfilehash: 171cc8c912e1a1204d07be2c52c0e96bc1369991
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823984"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="d4206-104">Ajouter des services web frontaux</span><span class="sxs-lookup"><span data-stu-id="d4206-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="d4206-105">L’URL de base correspond à l’identité des services web pour l’URL, moins https://.</span><span class="sxs-lookup"><span data-stu-id="d4206-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="d4206-106">Par exemple, si l’URL complète des services Web du pool est , l’URL de https://pool01.contoso.net base est pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="d4206-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="d4206-107">Vous ne pouvez pas remplacer le nom de domaine complet (FQDN) du pool de services Web internes pour un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="d4206-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="d4206-108">Si vous configurez l’équilibrage de charge DNS (Domain Name System) pour un pool frontal Enterprise Edition, vous pouvez spécifier une URL de base interne différente, qui doit être différente du nom de domaine complet du pool (par exemple, internal- \<your base URL\> ).</span><span class="sxs-lookup"><span data-stu-id="d4206-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="d4206-p104">Vous pouvez indiquer une URL de base externe qui diffère de votre URL de base interne afin de distinguer les noms de domaine. Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Définissez alors l’URL de base externe à l’aide du nom de domaine contoso.com. Cette caractéristique est importante pour les serveurs proxy inverses dans le cas d’un déploiement de périphérie. Le nom de domaine de l’URL de base externe est le même que le nom de domaine du nom de domaine complet du proxy inverse. La messagerie instantanée et la présence ont besoin d'un accès HTTP au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="d4206-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy. Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

