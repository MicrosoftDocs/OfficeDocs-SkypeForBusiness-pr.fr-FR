---
title: Connexion du pool pilote aux serveurs Edge hérités
description: Connectez le pool pilote aux serveurs Edge hérités.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ede2256efabf561be6b3f99543437087cb5c3890
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550270"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="b9617-103">Connexion du pool pilote aux serveurs Edge hérités</span><span class="sxs-lookup"><span data-stu-id="b9617-103">Connect pilot pool to legacy Edge Servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9617-104">_**Dernière modification de la rubrique :** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="b9617-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="b9617-105">Après avoir déployé Lync Server 2013, vous devez configurer un itinéraire de Fédération pour votre site.</span><span class="sxs-lookup"><span data-stu-id="b9617-105">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="b9617-106">Pour utiliser l’itinéraire fédéré utilisé par Lync Server 2010, Lync Server 2013 doit être configuré pour utiliser cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="b9617-106">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="b9617-107">Pour activer le site Lync Server 2013 afin qu’il utilise le directeur et le serveur Edge du déploiement de Lync Server 2010, utilisez le générateur de topologie pour associer le pool de serveurs Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="b9617-107">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="b9617-108">Pour associer le pool Edge hérité à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="b9617-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="b9617-109">Ouvrez le **Générateur de topologie**.</span><span class="sxs-lookup"><span data-stu-id="b9617-109">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="b9617-110">Sélectionnez votre site, qui est affiché juste en dessous du nœud **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b9617-110">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="b9617-111">Dans le menu **Actions**, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b9617-111">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="b9617-112">Dans le volet gauche, sélectionnez **Itinéraire de fédération**.</span><span class="sxs-lookup"><span data-stu-id="b9617-112">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="b9617-113">Sous **attribution**de l’itinéraire de Fédération du site, sélectionnez **activer la Fédération SIP**, puis sélectionnez le directeur Lync Server 2010 ou le serveur Edge Lync Server 2010 si aucun directeur n’est mentionné.</span><span class="sxs-lookup"><span data-stu-id="b9617-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="b9617-114">![Modifier les propriétés, page itinéraire de Fédération](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Modifier les propriétés, page itinéraire de Fédération")</span><span class="sxs-lookup"><span data-stu-id="b9617-114">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="b9617-115">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b9617-115">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="b9617-116">Dans le générateur de topologie, sous le nœud Lync Server 2013, naviguez jusqu’aux **Pools frontaux** **Standard Edition Server** ou Enterprise Edition, cliquez avec le bouton droit sur le pool, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b9617-116">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="b9617-117">Sous **Associations**, activez la case à cocher en regard de **Associer un pool de serveurs Edge (pour les composants médias)**.</span><span class="sxs-lookup"><span data-stu-id="b9617-117">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="b9617-118">Dans la liste, sélectionnez le serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="b9617-118">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="b9617-119">![Boîte de dialogue Modifier les propriétés, sélection du serveur Edge hérité](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, sélection du serveur Edge hérité")</span><span class="sxs-lookup"><span data-stu-id="b9617-119">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="b9617-120">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b9617-120">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="b9617-121">Dans le **Générateur de topologie**, sélectionnez le nœud de niveau supérieur, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b9617-121">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="b9617-122">Depuis le menu **Actions**, cliquez sur **Publier la topologie**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b9617-122">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="b9617-123">Une fois l’**Assistant Publication** terminé, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b9617-123">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

