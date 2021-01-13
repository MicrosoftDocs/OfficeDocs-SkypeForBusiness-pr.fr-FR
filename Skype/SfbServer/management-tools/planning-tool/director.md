---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Un directeur est un serveur exécutant le logiciel de communication Skype Entreprise Server 2015 qui peut authentifier les demandes des utilisateurs, mais qui n’a pas de compte d’utilisateur.
ms.openlocfilehash: 76315e9f63e1121119f3823187c379985c4914f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834934"
---
# <a name="director-planning-tool"></a><span data-ttu-id="2dcd2-103">Director (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="2dcd2-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="2dcd2-104">Un directeur est un serveur exécutant le logiciel de communication Skype Entreprise Server 2015 qui peut authentifier les demandes des utilisateurs, mais qui n’a pas de compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2dcd2-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="2dcd2-105">Ce rôle est facultatif, vous pouvez choisir de déployer un directeur dans les deux scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="2dcd2-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="2dcd2-106">Si vous activez l’accès par des utilisateurs externes en déployant des serveurs Edge, vous devez également déployer un directeur.</span><span class="sxs-lookup"><span data-stu-id="2dcd2-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="2dcd2-107">Dans ce scénario, le directeur authentifier les utilisateurs externes, puis transmet leur trafic aux serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="2dcd2-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="2dcd2-108">Lorsqu’un directeur est utilisé pour authentifier des utilisateurs externes, il décharge les serveurs du pool frontal de la surcharge d’authentification de ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2dcd2-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="2dcd2-109">Elle permet également d’isoler les pools frontux internes du trafic malveillant tel que les attaques par déni de service.</span><span class="sxs-lookup"><span data-stu-id="2dcd2-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="2dcd2-110">Si le réseau est saturé par du trafic externe non valide dans le cadre d’une telle attaque, tout ce trafic s’arrête au niveau du directeur.</span><span class="sxs-lookup"><span data-stu-id="2dcd2-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="2dcd2-111">Si vous déployez plusieurs pools frontux sur un site central, en ajoutant un directeur à ce site, vous pouvez rationaliser les demandes d’authentification et améliorer les performances.</span><span class="sxs-lookup"><span data-stu-id="2dcd2-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="2dcd2-112">Dans ce scénario, toutes les demandes sont d’abord reçues par le directeur, qui les a ensuite route vers le pool frontal correct.</span><span class="sxs-lookup"><span data-stu-id="2dcd2-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

