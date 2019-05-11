---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: Un directeur est un serveur exécutant Skype pour le logiciel de communication Business Server qui peut authentifier les demandes des utilisateurs, mais qui n’héberge pas des comptes d’utilisateurs.
ms.openlocfilehash: 9ba73f88ba58abd25cdbd11b2efa5129b0322cfd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889499"
---
# <a name="director-planning-tool"></a><span data-ttu-id="6172e-103">Director (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="6172e-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="6172e-104">Un directeur est un serveur exécutant Skype pour le logiciel de communication Business Server qui peut authentifier les demandes des utilisateurs, mais qui n’héberge pas des comptes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6172e-104">A Director is a server running Skype for Business Server communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="6172e-105">Ce rôle est facultatif, que choisissez de déployer un directeur dans les deux scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="6172e-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="6172e-106">Si vous activez l’accès des utilisateurs externes en déployant des serveurs de périphérie, vous devez également déployer un directeur.</span><span class="sxs-lookup"><span data-stu-id="6172e-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="6172e-107">Dans ce scénario, le directeur authentifie les utilisateurs externes, puis transmet le trafic sur les serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="6172e-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="6172e-108">Lorsqu’un directeur est utilisé pour authentifier des utilisateurs externes, il évite les serveurs du pool frontal à partir de la charge de l’authentification de ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6172e-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="6172e-109">Il permet également d’isoler les pools frontaux internes du trafic malveillant, telles que les attaques par déni de service.</span><span class="sxs-lookup"><span data-stu-id="6172e-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="6172e-110">Si le réseau est réparti avec le trafic externe non valide dans ce type d’attaque, ce trafic se termine sur le directeur.</span><span class="sxs-lookup"><span data-stu-id="6172e-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="6172e-111">Si vous déployez plusieurs pools frontaux à un site central, vous pouvez simplifier les demandes d’authentification et améliorer les performances en ajoutant un directeur à ce site.</span><span class="sxs-lookup"><span data-stu-id="6172e-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="6172e-112">Dans ce scénario, toutes les demandes en premier pour le directeur, qui route vers le pool frontal correct.</span><span class="sxs-lookup"><span data-stu-id="6172e-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

