---
title: 'Service web : ajouter un directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net , l’URL de base est pool01.contoso.net.
ms.openlocfilehash: 5d965eb591afca8d7154d8fd12af741ddaf65084
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219465"
---
# <a name="add-director-web-service"></a><span data-ttu-id="d9877-104">Service web : ajouter un directeur</span><span class="sxs-lookup"><span data-stu-id="d9877-104">Add Director Web Service</span></span>
 
<span data-ttu-id="d9877-105">L’URL de base correspond à l’identité des services web pour l’URL, moins https://.</span><span class="sxs-lookup"><span data-stu-id="d9877-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="d9877-106">Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net , l’URL de base est pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="d9877-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="d9877-107">Vous ne pouvez pas remplacer le nom de domaine complet (FQDN) du pool de services web internes si vous ne déployez qu’un seul directeur.</span><span class="sxs-lookup"><span data-stu-id="d9877-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="d9877-108">Si vous configurez un équilibrage de charge DNS (Domain Name System) pour le pool de directeurs, vous pouvez spécifier une URL de base interne différente (qui doit être différente du nom de domaine complet du pool et peut être, par exemple, Internal \<your base URL\> ).</span><span class="sxs-lookup"><span data-stu-id="d9877-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="d9877-p104">Vous pouvez indiquer une URL de base externe qui diffère de votre URL de base interne afin de distinguer les noms de domaine. Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Définissez alors l’URL à l’aide du nom de domaine contoso.com. Cette caractéristique est importante pour les serveurs proxy inverses dans le cas d’un déploiement Edge. Le nom de domaine de l’URL de base externe est le même que le nom de domaine du nom de domaine complet du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="d9877-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

