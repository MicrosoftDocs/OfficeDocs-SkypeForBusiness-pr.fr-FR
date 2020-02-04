---
title: 'Skype Entreprise Server 2015 : tâches quotidiennes'
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
ms.openlocfilehash: 9d63aff308b23e52284988a184e5e9d72beaca26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="88733-102">Tâches quotidiennes dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="88733-102">Daily tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88733-103">_**Dernière modification de la rubrique :** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="88733-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="88733-104">Pour garantir la disponibilité et la fiabilité du déploiement de Lync Server 2013, vous devez faire partie du moniteur de routine quotidienne et des éléments de test qui sont très importants pour le fonctionnement du système, y compris la plateforme physique, le système d’exploitation et tout service important de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88733-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="88733-105">La maintenance préventive et la surveillance proactive vous permettent d’identifier les erreurs potentielles et les problèmes susceptibles d’affecter le déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88733-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="88733-106">L’analyse du déploiement de Lync Server 2013 implique de vérifier les problèmes liés aux connexions, services, ressources serveur et ressources système.</span><span class="sxs-lookup"><span data-stu-id="88733-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="88733-107">Les systèmes d’exploitation Windows Server, avec System Center Operations Manager et Lync Server vous fournissent de nombreux outils et services d’analyse pour vous permettre de vérifier que l’organisation du serveur Lync fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="88733-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="88733-108">Lorsque ces technologies sont mises en œuvre conjointement, les administrateurs peuvent recevoir des avertissements lorsque des problèmes se produisent ou avant.</span><span class="sxs-lookup"><span data-stu-id="88733-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="88733-109">Principaux avantages de la surveillance quotidienne :</span><span class="sxs-lookup"><span data-stu-id="88733-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="88733-110">Elle permet de répondre aux exigences de performances et de disponibilité des contrats de niveau de service (SLA) définis.</span><span class="sxs-lookup"><span data-stu-id="88733-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="88733-111">Elle permet d’effectuer correctement des tâches d’administration spécifiques, comme les opérations de sauvegarde quotidiennes et la vérification de l’intégrité des serveurs.</span><span class="sxs-lookup"><span data-stu-id="88733-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="88733-112">Elle permet de détecter les problèmes, comme des goulets d’étranglement affectant les performances des serveurs ou la nécessité de recourir à des ressources supplémentaires, et de les prendre en compte avant qu’ils affectent la productivité.</span><span class="sxs-lookup"><span data-stu-id="88733-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="88733-113">Les tâches de maintenance quotidiennes permettent à l’équipe d’administration de définir un critère ou une valeur de référence pour les opérations normales des systèmes dans l’organisation et de détecter les activités anormales.</span><span class="sxs-lookup"><span data-stu-id="88733-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="88733-114">Il est important de mettre en œuvre ces tâches de maintenance quotidienne de sorte que l’équipe d’administration puisse capturer et tenir à jour des données sur l’infrastructure 2013 de Lync Server, telles que des niveaux d’utilisation, des goulets d’étranglement de performance possibles et des changements d’administration.</span><span class="sxs-lookup"><span data-stu-id="88733-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="88733-115">Pour faciliter l’organisation des tâches quotidiennes, utilisez la [Liste de contrôle des tâches quotidiennes](lync-server-2013-operations-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="88733-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="88733-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="88733-116">See Also</span></span>


[<span data-ttu-id="88733-117">Liste de contrôle des tâches quotidiennes</span><span class="sxs-lookup"><span data-stu-id="88733-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

