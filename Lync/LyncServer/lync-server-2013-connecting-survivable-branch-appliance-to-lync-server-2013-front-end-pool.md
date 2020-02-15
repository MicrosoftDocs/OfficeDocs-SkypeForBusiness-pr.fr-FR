---
title: Connexion d’un Survivable Branch Appliance à un pool de serveurs frontaux Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d23b501738010a8e5e5ed1c5c2e9a8608b0709e4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="7b266-102">Connexion d’un Survivable Branch Appliance à un pool de serveurs frontaux Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b266-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b266-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="7b266-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="7b266-104">Chaque Survivable Branch Appliance (SBA) est associé à un pool de serveurs frontaux, qui sert de serveur d’inscriptions de sauvegarde pour le SBA.</span><span class="sxs-lookup"><span data-stu-id="7b266-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="7b266-105">Lorsque le pool frontal est mis à niveau vers Lync Server 2013, le SBA doit être désassocié du pool frontal pendant la mise à niveau du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="7b266-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="7b266-106">Une fois le pool frontal mis à niveau, le SBA peut être réassocié au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="7b266-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="7b266-107">Cela implique de supprimer le SBA de la topologie dans le Générateur de topologie, puis de l’ajouter à nouveau au Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="7b266-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="7b266-108">Les utilisateurs hébergés sur le SBA doivent être déplacés vers un autre pool frontal avant de supprimer le SBA de la topologie.</span><span class="sxs-lookup"><span data-stu-id="7b266-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="7b266-109">Une fois que le SBA a été rajouté à la topologie, ces utilisateurs peuvent réintégrer le SBA.</span><span class="sxs-lookup"><span data-stu-id="7b266-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="7b266-110">Voici un récapitulatif de ces étapes :</span><span class="sxs-lookup"><span data-stu-id="7b266-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="7b266-111">Déplacez les utilisateurs de succursale hébergés sur SBA vers un autre pool frontal.</span><span class="sxs-lookup"><span data-stu-id="7b266-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="7b266-112">Supprimez SBA de votre topologie pour dissocier le pool frontal existant en tant que serveur d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7b266-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="7b266-113">Mettez à niveau le pool frontal vers Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b266-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="7b266-114">Rajoutez le SBA à votre topologie.</span><span class="sxs-lookup"><span data-stu-id="7b266-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="7b266-115">Associez le nouveau pool frontal au SBA en tant que serveur d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7b266-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="7b266-116">Réintégrez les utilisateurs au SBA.</span><span class="sxs-lookup"><span data-stu-id="7b266-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7b266-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7b266-117">In This Section</span></span>

  - [<span data-ttu-id="7b266-118">Ajouter le site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie</span><span class="sxs-lookup"><span data-stu-id="7b266-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="7b266-119">Ajouter le site de succursale Survivable Branch Appliance Lync Server 2010 à votre topologie</span><span class="sxs-lookup"><span data-stu-id="7b266-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

