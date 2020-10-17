---
title: 'Lync Server 2013 : planification du jumelage de pools frontaux'
description: 'Lync Server 2013 : planification du jumelage de pools frontaux.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac235cf682e286132836e13b34b457adf2bfc233
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562790"
---
# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="7d4b4-103">Planification du jumelage de pools frontaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d4b4-103">Planning for Front End pool pairing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d4b4-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7d4b4-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7d4b4-105">Pour les meilleures capacités de récupération d’urgence dans Lync Server 2013, déployez des paires de pools frontaux sur deux sites géographiquement dispersés.</span><span class="sxs-lookup"><span data-stu-id="7d4b4-105">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="7d4b4-106">Chaque site contient un pool frontal couplé à un pool frontal correspondant dans l’autre site.</span><span class="sxs-lookup"><span data-stu-id="7d4b4-106">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="7d4b4-107">Les deux sites sont actifs et le service de sauvegarde Lync Server fournit une réplication de données en temps réel pour maintenir les pools synchronisés.</span><span class="sxs-lookup"><span data-stu-id="7d4b4-107">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="7d4b4-108">Le service de sauvegarde est une nouvelle fonctionnalité de Lync Server 2013, conçue pour prendre en charge la solution de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="7d4b4-108">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="7d4b4-109">Il est installé sur un pool frontal lorsque vous couplez le pool avec un autre pool frontal.</span><span class="sxs-lookup"><span data-stu-id="7d4b4-109">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="7d4b4-p102">Si le pool dans un site échoue, vous pouvez basculer les utilisateurs de ce pool vers le pool dans l’autre site, qui fournit alors les services à tous les utilisateurs dans les deux pools. À des fins de planification de capacité, chaque pool doit être conçu pour gérer les charges de travail de tous les utilisateurs dans les deux pools en cas de sinistre.</span><span class="sxs-lookup"><span data-stu-id="7d4b4-p102">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools. For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7d4b4-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7d4b4-112">In This Section</span></span>

  - [<span data-ttu-id="7d4b4-113">Options de jumelage des pools prises en charge et meilleures pratiques pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d4b4-113">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="7d4b4-114">Relations de serveur d’inscriptions de sauvegarde dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d4b4-114">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="7d4b4-115">Temps de récupération pour le basculement de pool et la restauration automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d4b4-115">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="7d4b4-116">Basculement du magasin central de gestion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d4b4-116">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="7d4b4-117">Sécurité des données de jumelage des pools frontaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d4b4-117">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

