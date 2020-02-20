---
title: 'Lync Server 2013 : nouvelles fonctionnalités de l’application Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2538c6698875a0a96ce4e7dc7a46aa7cb9ed8e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="b86fe-102">Nouvelles fonctionnalités de l’application Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b86fe-102">New Response Group application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b86fe-103">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="b86fe-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="b86fe-104">L’application Response Group vous permet de router et de placer en file d’attente des appels entrants vers des entités désignées pour des objectifs spéciaux (par exemple, un service clientèle, un service d’assistance interne ou un service d’assistance téléphonique général dédié à un service).</span><span class="sxs-lookup"><span data-stu-id="b86fe-104">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="b86fe-105">Les fonctionnalités d’application Response Group suivantes sont nouvelles dans Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="b86fe-105">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="b86fe-106">**Rôle de gestionnaire**</span><span class="sxs-lookup"><span data-stu-id="b86fe-106">**Manager role**</span></span>
    
    <span data-ttu-id="b86fe-107">Lync Server 2013 introduit un nouveau rôle gestionnaire de groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="b86fe-107">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="b86fe-108">À présent, il existe deux rôles de gestion pour les groupes Response Group : Response Group Manager et l’administrateur Response Group.</span><span class="sxs-lookup"><span data-stu-id="b86fe-108">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="b86fe-109">Alors que les administrateurs de groupes de réponse peuvent toujours configurer un élément pour un groupe Response Group, les gestionnaires peuvent configurer uniquement certains éléments, uniquement pour les groupes Response Group qu’ils possèdent.</span><span class="sxs-lookup"><span data-stu-id="b86fe-109">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="b86fe-110">Cette amélioration du modèle d’administration tire parti de l’extensibilité Response Group, en particulier pour les scénarios de déploiement de grande taille.</span><span class="sxs-lookup"><span data-stu-id="b86fe-110">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="b86fe-111">**Haute disponibilité**</span><span class="sxs-lookup"><span data-stu-id="b86fe-111">**High availability**</span></span>
    
    <span data-ttu-id="b86fe-112">La prise en charge de la haute disponibilité pour l’application Response Group, sous la forme de la mise en miroir SQL Server, est activée dans le cadre de la configuration globale et du déploiement de la haute disponibilité pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b86fe-112">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="b86fe-113">Si vous configurez la haute disponibilité et si vous perdez la connectivité au serveur principal, la fonctionnalité Response Group n’est pas affectée, car elle tire profit du serveur principal en miroir.</span><span class="sxs-lookup"><span data-stu-id="b86fe-113">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="b86fe-114">La prise en charge de la mise en miroir SQL Server pour l’application Response Group ne peut pas être activée ou configurée de manière individuelle en dehors de la configuration globale de la haute disponibilité de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b86fe-114">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="b86fe-115">**Récupération d’urgence**</span><span class="sxs-lookup"><span data-stu-id="b86fe-115">**Disaster recovery**</span></span>
    
    <span data-ttu-id="b86fe-116">La prise en charge de la récupération d’urgence pour l’application Response Group est activée dans le cadre de la configuration et du déploiement des pools frontaux couplés, qui font partie de la configuration globale de la récupération d’urgence de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b86fe-116">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="b86fe-117">En outre, les applets de commande d’importation et d’exportation Response Group prennent en charge le processus de basculement vers le pool de sauvegarde, ainsi que le processus de restauration automatique vers le pool principal ou un nouveau pool.</span><span class="sxs-lookup"><span data-stu-id="b86fe-117">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="b86fe-118">Si une panne survient dans le pool principal, les groupes Response Group peuvent faire l’objet d’un basculement vers le pool de sauvegarde, puis d’une restauration automatique vers le pool principal ou un nouveau pool une fois la panne terminée.</span><span class="sxs-lookup"><span data-stu-id="b86fe-118">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b86fe-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b86fe-119">See Also</span></span>


[<span data-ttu-id="b86fe-120">Planification des groupes Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b86fe-120">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

