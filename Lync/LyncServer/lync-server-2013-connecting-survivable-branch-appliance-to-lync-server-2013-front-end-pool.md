---
title: Connexion d’un Survivable Branch Appliance à un pool de serveurs frontaux Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77d22a71272ae7dd3c426b0439f7a3765ca6848c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="9e7c1-102">Connexion d’un Survivable Branch Appliance à un pool de serveurs frontaux Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e7c1-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e7c1-103">_**Dernière modification de la rubrique:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="9e7c1-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="9e7c1-104">Chaque appareil de branchement Survivable (SBA) est associé à un pool frontal, qui fait office d’agent de sauvegarde pour le SBA.</span><span class="sxs-lookup"><span data-stu-id="9e7c1-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="9e7c1-105">Lorsque le pool frontal est mis à niveau vers Lync Server 2013, le SBA doit être désassocié du pool frontal lors de la mise à niveau du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="9e7c1-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="9e7c1-106">Après la mise à niveau du pool frontal, le SBA peut être associé au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="9e7c1-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="9e7c1-107">Cela implique la suppression de l’SBA de la topologie dans le générateur de topologie, puis l’ajout de l’SBA, là encore, au générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="9e7c1-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="9e7c1-108">Les utilisateurs hébergés sur le SBA doivent être déplacés vers un autre pool frontal avant de supprimer l’SBA de la topologie.</span><span class="sxs-lookup"><span data-stu-id="9e7c1-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="9e7c1-109">Après l’ajout de l’SBA à la topologie, ces utilisateurs peuvent être replacés vers l’SBA.</span><span class="sxs-lookup"><span data-stu-id="9e7c1-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="9e7c1-110">Ces étapes sont décrites ci-dessous:</span><span class="sxs-lookup"><span data-stu-id="9e7c1-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="9e7c1-111">Déplacez les utilisateurs de succursales hébergés sur SBA vers un autre pool frontal.</span><span class="sxs-lookup"><span data-stu-id="9e7c1-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="9e7c1-112">Supprimez SBA de votre topologie pour dissocier le pool frontal existant en tant qu’Bureau d’enregistrement de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9e7c1-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="9e7c1-113">Mettez à niveau le pool frontal vers Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9e7c1-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="9e7c1-114">Ajoutez SBA dans votre topologie.</span><span class="sxs-lookup"><span data-stu-id="9e7c1-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="9e7c1-115">Associez le nouveau pool frontal à l’SBA en tant qu’Bureau d’enregistrement de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9e7c1-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="9e7c1-116">Transférez les utilisateurs de succursale vers le SBA.</span><span class="sxs-lookup"><span data-stu-id="9e7c1-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9e7c1-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9e7c1-117">In This Section</span></span>

  - [<span data-ttu-id="9e7c1-118">Ajout d’un site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie</span><span class="sxs-lookup"><span data-stu-id="9e7c1-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="9e7c1-119">Ajout d’un site de succursale Survivable Branch Appliance Lync Server 2010 à votre topologie</span><span class="sxs-lookup"><span data-stu-id="9e7c1-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

