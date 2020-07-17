---
title: Connexion du pool pilote aux serveurs Edge hérités
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
ms.openlocfilehash: 313d2201be5f5919aeec37087a02bf7f400d7ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="62518-102">Connexion du pool pilote aux serveurs Edge hérités</span><span class="sxs-lookup"><span data-stu-id="62518-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62518-103">_**Dernière modification de la rubrique :** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="62518-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="62518-104">Après avoir déployé Lync Server 2013, vous devez configurer un itinéraire de Fédération pour votre site.</span><span class="sxs-lookup"><span data-stu-id="62518-104">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="62518-105">Pour utiliser l’itinéraire fédéré utilisé par Lync Server 2010, Lync Server 2013 doit être configuré pour utiliser cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="62518-105">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="62518-106">Pour activer le site Lync Server 2013 afin qu’il utilise le directeur et le serveur Edge du déploiement de Lync Server 2010, utilisez le générateur de topologie pour associer le pool de serveurs Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="62518-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="62518-107">Pour associer le pool Edge hérité à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="62518-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="62518-108">Ouvrez le **Générateur de topologie**.</span><span class="sxs-lookup"><span data-stu-id="62518-108">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="62518-109">Sélectionnez votre site, qui est affiché juste en dessous du nœud **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="62518-109">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="62518-110">Dans le menu **Actions**, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="62518-110">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="62518-111">Dans le volet gauche, sélectionnez **Itinéraire de fédération**.</span><span class="sxs-lookup"><span data-stu-id="62518-111">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="62518-112">Sous **attribution**de l’itinéraire de Fédération du site, sélectionnez **activer la Fédération SIP**, puis sélectionnez le directeur Lync Server 2010 ou le serveur Edge Lync Server 2010 si aucun directeur n’est mentionné.</span><span class="sxs-lookup"><span data-stu-id="62518-112">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="62518-113">![Modifier les propriétés, page itinéraire de Fédération](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Modifier les propriétés, page itinéraire de Fédération")</span><span class="sxs-lookup"><span data-stu-id="62518-113">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="62518-114">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="62518-114">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="62518-115">Dans le générateur de topologie, sous le nœud Lync Server 2013, naviguez jusqu’aux **Pools frontaux** **Standard Edition Server** ou Enterprise Edition, cliquez avec le bouton droit sur le pool, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="62518-115">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="62518-116">Sous **Associations**, activez la case à cocher en regard de **Associer un pool de serveurs Edge (pour les composants médias)**.</span><span class="sxs-lookup"><span data-stu-id="62518-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="62518-117">Dans la liste, sélectionnez le serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="62518-117">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="62518-118">![Boîte de dialogue Modifier les propriétés, sélection du serveur Edge hérité](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, sélection du serveur Edge hérité")</span><span class="sxs-lookup"><span data-stu-id="62518-118">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="62518-119">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="62518-119">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="62518-120">Dans le **Générateur de topologie**, sélectionnez le nœud de niveau supérieur, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="62518-120">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="62518-121">Depuis le menu **Actions**, cliquez sur **Publier la topologie**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="62518-121">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="62518-122">Une fois l’**Assistant Publication** terminé, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="62518-122">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

