---
title: Directeur (outil de planification)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Un directeur est un serveur exécutant Skype pour le logiciel de communication Business Server 2015 qui peut authentifier les demandes de l’utilisateur, mais ne pas accueil des comptes d’utilisateurs.
ms.openlocfilehash: b379388b05e4beda934b13517f36bc792b6f0748
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="director-planning-tool"></a><span data-ttu-id="227d7-103">Directeur (outil de planification)</span><span class="sxs-lookup"><span data-stu-id="227d7-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="227d7-104">Un directeur est un serveur exécutant Skype pour le logiciel de communication Business Server 2015 qui peut authentifier les demandes de l’utilisateur, mais ne pas accueil des comptes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="227d7-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="227d7-105">Ce rôle est facultatif, que vous choisissez de déployer un directeur dans les deux scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="227d7-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="227d7-106">Si vous activez l’accès par des utilisateurs externes en déployant les serveurs Edge, vous devez également déployer un directeur.</span><span class="sxs-lookup"><span data-stu-id="227d7-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="227d7-107">Dans ce scénario, le directeur authentifie les utilisateurs externes et transmet ensuite le trafic vers les serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="227d7-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="227d7-108">Lorsqu’un directeur est utilisé pour authentifier les utilisateurs externes, il évite les serveurs du pool Front-End de la charge de l’authentification de ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="227d7-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="227d7-109">Il permet également d’isoler les pools de Front-End internes de trafic malveillant, comme les attaques de déni de service.</span><span class="sxs-lookup"><span data-stu-id="227d7-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="227d7-110">Si le réseau est inondé de trafic d’externe non valide dans une telle attaque, ce trafic se termine sur le directeur.</span><span class="sxs-lookup"><span data-stu-id="227d7-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="227d7-111">Si vous déployez plusieurs pools de Front-End sur un site central, vous pouvez rationaliser les demandes d’authentification et améliorer les performances en ajoutant un directeur à ce site.</span><span class="sxs-lookup"><span data-stu-id="227d7-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="227d7-112">Dans ce scénario, toutes les demandes en premier au directeur, qui les achemine ensuite dans le pool de Front-End approprié.</span><span class="sxs-lookup"><span data-stu-id="227d7-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

