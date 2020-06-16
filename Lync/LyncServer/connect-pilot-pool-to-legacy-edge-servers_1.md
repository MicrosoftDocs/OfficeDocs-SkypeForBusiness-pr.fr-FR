---
title: Connexion du pool pilote aux serveurs Edge hérités
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b83877505bfc9c2accc2057a9ebb1fb62355b3d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="8a139-102">Connexion du pool pilote aux serveurs Edge hérités</span><span class="sxs-lookup"><span data-stu-id="8a139-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a139-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8a139-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8a139-104">Après le déploiement de Lync Server 2013, un itinéraire de Fédération pour ce site n’est pas configuré.</span><span class="sxs-lookup"><span data-stu-id="8a139-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="8a139-105">Pour utiliser l’itinéraire fédéré utilisé par Office Communications Server 2007 R2, Lync Server 2013 doit être configuré pour utiliser cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="8a139-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="8a139-106">Pour activer le site Lync Server 2013 afin qu’il utilise le directeur et le serveur Edge du BackCompatSite, utilisez le générateur de topologie pour associer le pool de serveurs Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="8a139-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="8a139-107">Pour associer le pool Edge hérité à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="8a139-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="8a139-108">Ouvrez la topologie du pool pilote dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="8a139-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="8a139-109">Sélectionnez votre site Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8a139-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="8a139-110">Dans le menu **Actions**, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8a139-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="8a139-111">Sous **attribution**de l’itinéraire de Fédération du site, sélectionnez **activer la Fédération SIP**, puis sélectionnez le directeur Office Communications Server 2007 R2 ou le serveur Edge Office Communications Server 2007 R2 si aucun directeur n’est mentionné.</span><span class="sxs-lookup"><span data-stu-id="8a139-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="8a139-112">![Boîte de dialogue Modifier les propriétés, page itinéraire de Fédération](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page itinéraire de Fédération")</span><span class="sxs-lookup"><span data-stu-id="8a139-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="8a139-113">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8a139-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="8a139-114">Dans le générateur de topologie, sous le nœud Lync Server 2013, naviguez jusqu’aux **Pools frontaux** **Standard Edition Server** ou Enterprise Edition, cliquez avec le bouton droit sur le pool, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8a139-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="8a139-115">Sous **Associations**, activez la case à cocher en regard de **Associer un pool de serveurs Edge (pour les composants médias)**.</span><span class="sxs-lookup"><span data-stu-id="8a139-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="8a139-116">Dans la liste, sélectionnez l’interface de serveur Edge pour le BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="8a139-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="8a139-117">![Boîte de dialogue Modifier les propriétés, page général](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page général")</span><span class="sxs-lookup"><span data-stu-id="8a139-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="8a139-118">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8a139-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="8a139-119">Dans le **Générateur de topologie**, sélectionnez le nœud de niveau supérieur, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8a139-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="8a139-120">Depuis le menu **Actions**, cliquez sur **Publier la topologie**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8a139-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="8a139-121">Une fois l’**Assistant Publication** terminé, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="8a139-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

