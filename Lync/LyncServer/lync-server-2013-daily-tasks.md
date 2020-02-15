---
title: 'Lync Server 2013 : tâches quotidiennes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Daily tasks
ms:assetid: f7a5f99e-5d2b-445d-9ba1-cbfcfeff16ae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720351(v=OCS.15)
ms:contentKeyID: 63969666
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc14c72f614e6e062afc089236182def0d86e634
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="ab126-102">Tâches quotidiennes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab126-102">Daily tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab126-103">_**Dernière modification de la rubrique :** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="ab126-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="ab126-104">Pour garantir la disponibilité et la fiabilité du déploiement de Lync Server 2013, vous devez faire partie de la surveillance de routine quotidienne et des éléments de test qui sont très importants pour le fonctionnement du système, qui inclut la plateforme physique, le système d’exploitation et tous les services Lync Server 2013 importants.</span><span class="sxs-lookup"><span data-stu-id="ab126-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="ab126-105">La maintenance préventive et la surveillance proactive vous aideront à identifier les erreurs et les problèmes potentiels susceptibles d’avoir un impact négatif sur le déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab126-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="ab126-106">La surveillance du déploiement de Lync Server 2013 implique de vérifier les problèmes liés aux connexions, aux services, aux ressources du serveur et aux ressources système.</span><span class="sxs-lookup"><span data-stu-id="ab126-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="ab126-107">Les systèmes d’exploitation Windows Server, ainsi que System Center Operations Manager et Lync Server, vous offrent un grand nombre d’outils et de services de surveillance pour vous aider à garantir le bon fonctionnement de l’organisation Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ab126-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="ab126-108">Lorsque ces technologies sont implémentées ensemble, les administrateurs peuvent recevoir des alertes quand ou avant des problèmes.</span><span class="sxs-lookup"><span data-stu-id="ab126-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="ab126-109">Les principaux avantages de la surveillance quotidienne sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="ab126-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="ab126-110">Répondre aux exigences en matière de performances et de disponibilité des SLA définis.</span><span class="sxs-lookup"><span data-stu-id="ab126-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="ab126-111">Exécution réussie de tâches d’administration spécifiques, telles que les opérations de sauvegarde quotidiennes et la vérification de l’intégrité du serveur.</span><span class="sxs-lookup"><span data-stu-id="ab126-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="ab126-112">Détecter et résoudre les problèmes, tels que les goulots d’étranglement des performances du serveur, ou avoir besoin de ressources supplémentaires avant qu’elles aient une incidence sur la productivité.</span><span class="sxs-lookup"><span data-stu-id="ab126-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="ab126-113">Les tâches de maintenance quotidiennes aident l’équipe d’administration à définir ou établir un critère ou une référence pour les opérations système normales au sein de l’organisation et à détecter toute activité anormale.</span><span class="sxs-lookup"><span data-stu-id="ab126-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="ab126-114">Il est important d’implémenter ces tâches de maintenance quotidiennes afin que l’équipe administrative puisse capturer et gérer les données relatives à l’infrastructure Lync Server 2013, telles que les niveaux d’utilisation, les goulots d’étranglement des performances possibles et les modifications administratives.</span><span class="sxs-lookup"><span data-stu-id="ab126-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="ab126-115">Pour vous aider à organiser les performances des tâches quotidiennes, utilisez la [liste de vérification des tâches quotidiennes](lync-server-2013-operations-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="ab126-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ab126-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ab126-116">See Also</span></span>


[<span data-ttu-id="ab126-117">Liste de vérification des tâches quotidiennes</span><span class="sxs-lookup"><span data-stu-id="ab126-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

