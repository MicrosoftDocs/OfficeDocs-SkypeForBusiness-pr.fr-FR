---
title: Options de jumelage des pools et meilleures pratiques de Lync Server 2013 prises en charge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c73108f832aaa10b0539aa6fd56b4f4a7bb0cbb1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="3eb42-102">Options de jumelage des pools prises en charge et meilleures pratiques pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3eb42-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3eb42-103">_**Dernière modification de la rubrique :** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="3eb42-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="3eb42-p101">La distance entre deux centres de données devant inclure des pools frontaux jumelés l’un à l’autre n’est pas soumise à des restrictions. Nous vous recommandons d’utiliser deux centres de données qui se trouvent dans la même région du monde, reliés par des connexions haut débit. Il est préférable que les deux centres de données soient assez éloignés pour ne pas subir en même temps une même défaillance.</span><span class="sxs-lookup"><span data-stu-id="3eb42-p101">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other. We recommend that you use two data centers in the same world region, with high-speed links between them. It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="3eb42-107">Il est possible d’avoir deux centres de données situés dans des régions du monde différentes, mais cette situation peut entraîner une perte de données plus importante en raison de la latence de la réplication de données.</span><span class="sxs-lookup"><span data-stu-id="3eb42-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="3eb42-108">Lorsque vous planifiez le jumelage des pools, gardez à l’esprit que seuls les jumelages suivants sont pris en charge :</span><span class="sxs-lookup"><span data-stu-id="3eb42-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="3eb42-p102">Les pools Enterprise Edition peuvent uniquement être jumelés avec d’autres pools Enterprise Edition. De même, les pools Standard Edition peuvent uniquement être jumelés avec d’autres pools Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3eb42-p102">Enterprise Edition pools can be paired only with other Enterprise Edition pools. Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="3eb42-p103">Les pools physiques peuvent uniquement être jumelés avec d’autres pools physiques. De même, les pools virtuels peuvent uniquement être jumelés avec d’autres pools virtuels.</span><span class="sxs-lookup"><span data-stu-id="3eb42-p103">Physical pools can be paired only with other physical pools. Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="3eb42-113">Les pools associés doivent exécuter le même système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="3eb42-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="3eb42-114">Ni le Générateur de topologie, ni la validation des topologies n’empêcheront le jumelage de deux pools qui ne suit pas ces recommandations.</span><span class="sxs-lookup"><span data-stu-id="3eb42-114">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations.</span></span> <span data-ttu-id="3eb42-115">Par exemple, le Générateur de topologie vous permet de jumeler un pool Enterprise Edition avec un pool Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3eb42-115">For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool.</span></span> <span data-ttu-id="3eb42-116">Toutefois, ces types de jumelage ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="3eb42-116">However, these types of pairings are not supported.</span></span>

<span data-ttu-id="3eb42-117">Chaque pool d’un jumelage doit être capable de traiter les demandes de tous les utilisateurs des deux pools en cas d’incident.</span><span class="sxs-lookup"><span data-stu-id="3eb42-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="3eb42-118">Si vous jumelez des pools Enterprise Edition, vous pouvez également implémenter une disponibilité importante sur les serveurs principaux, mais pour le jumelage des pools Standard Edition, seules les mesures de récupération d’urgence sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="3eb42-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

