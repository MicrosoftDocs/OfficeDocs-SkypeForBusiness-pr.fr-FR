---
title: Connexion du pool pilote aux serveurs Edge hérités
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40d54a7432451901a32cb8e31d201ef732a731bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="d479b-102">Connexion du pool pilote aux serveurs Edge hérités</span><span class="sxs-lookup"><span data-stu-id="d479b-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d479b-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d479b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d479b-104">Après le déploiement de Lync Server 2013, un itinéraire de Fédération pour ce site n’est pas configuré.</span><span class="sxs-lookup"><span data-stu-id="d479b-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="d479b-105">Pour pouvoir utiliser l’itinéraire fédéré utilisé par Office Communications Server 2007 R2, Lync Server 2013 doit être configuré pour utiliser cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="d479b-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="d479b-106">Pour permettre au site Lync Server 2013 d’utiliser le serveur directeur et le serveur de périphérie du BackCompatSite, utilisez le générateur de topologie pour associer le pool de bords hérité.</span><span class="sxs-lookup"><span data-stu-id="d479b-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="d479b-107">Pour associer le pool de bords antérieurs à l’aide du générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="d479b-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="d479b-108">Ouvrez la topologie du pool de pilotes dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="d479b-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="d479b-109">Sélectionnez votre site Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d479b-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="d479b-110">Dans le menu **action** , cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d479b-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="d479b-111">Sous **affectation**de l’itinéraire de Fédération de site, sélectionnez **activer la Fédération SIP**, puis sélectionnez le directeur Office Communications Server 2007 R2 ou le serveur Office Communications Server 2007 R2, si aucun directeur n’est répertorié.</span><span class="sxs-lookup"><span data-stu-id="d479b-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="d479b-112">![Boîte de dialogue Modifier les propriétés, page itinéraire de Fédération] (images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page itinéraire de Fédération")</span><span class="sxs-lookup"><span data-stu-id="d479b-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="d479b-113">Cliquez sur **OK** pour fermer la page **modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="d479b-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="d479b-114">Dans le générateur de topologie, sous le nœud Lync Server 2013, accédez aux **Pools front end Server ou Enterprise Edition** **standard** , cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d479b-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="d479b-115">Sous **associations**, activez la case à cocher en regard de **associer le pool de bords (pour les composants multimédias)**.</span><span class="sxs-lookup"><span data-stu-id="d479b-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="d479b-116">Dans la liste, sélectionnez l’interface du serveur Edge pour le BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="d479b-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="d479b-117">![Boîte de dialogue Modifier les propriétés, page général] (images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page général")</span><span class="sxs-lookup"><span data-stu-id="d479b-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="d479b-118">Cliquez sur **OK** pour fermer la page **modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="d479b-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="d479b-119">Dans **Générateur de topologie**, sélectionnez le nœud supérieur, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d479b-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="d479b-120">Dans le menu **action** , cliquez sur **publier la topologie**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="d479b-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="d479b-121">À la fin de l' **Assistant Publication** , cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="d479b-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

