---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: Un directeur est un serveur exécutant un logiciel de communication Skype entreprise Server capable d’authentifier les demandes des utilisateurs, mais qui ne possède pas de compte d’utilisateur particulier.
ms.openlocfilehash: 529c9c0feea8d5ed3e28ee132f64c73228c6bd60
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689859"
---
# <a name="director-planning-tool"></a><span data-ttu-id="678f2-103">Director (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="678f2-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="678f2-104">Un directeur est un serveur exécutant un logiciel de communication Skype entreprise Server capable d’authentifier les demandes des utilisateurs, mais qui ne possède pas de compte d’utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="678f2-104">A Director is a server running Skype for Business Server communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="678f2-105">Ce rôle est facultatif, vous pouvez choisir de déployer un réalisateur dans les deux scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="678f2-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="678f2-106">Si vous autorisez l’accès par des utilisateurs externes en déployant des serveurs de périphérie, vous devez également déployer un directeur.</span><span class="sxs-lookup"><span data-stu-id="678f2-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="678f2-107">Dans ce scénario, le directeur authentifie les utilisateurs externes, puis transmet leur trafic aux serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="678f2-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="678f2-108">Lorsqu’un directeur est utilisé pour authentifier des utilisateurs externes, il allège la surcharge des serveurs du pool frontal en effectuant une authentification de ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="678f2-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="678f2-109">Il permet également d’isoler les listes frontales internes du trafic malveillant, par exemple pour les attaques par déni de service.</span><span class="sxs-lookup"><span data-stu-id="678f2-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="678f2-110">Si le réseau est inondé de trafic externe non valide lors d’une telle attaque, il se termine au directeur.</span><span class="sxs-lookup"><span data-stu-id="678f2-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="678f2-111">Si vous déployez plusieurs pools front-end sur un site central, en ajoutant un réalisateur à ce site, vous pouvez rationaliser les demandes d’authentification et améliorer les performances.</span><span class="sxs-lookup"><span data-stu-id="678f2-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="678f2-112">Dans ce scénario, toutes les demandes sont d’abord adressées au directeur, qui les route vers le pool frontal approprié.</span><span class="sxs-lookup"><span data-stu-id="678f2-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

