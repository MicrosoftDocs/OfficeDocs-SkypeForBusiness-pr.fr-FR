---
title: Connexion du pool pilote aux serveurs Edge hérités
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Après avoir déployé Skype entreprise Server 2019, vous devez configurer un itinéraire de Fédération pour votre site. Pour pouvoir utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype entreprise Server 2019 doit être configuré pour utiliser cet itinéraire.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753924"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="b55dc-104">Connexion du pool pilote aux serveurs Edge hérités</span><span class="sxs-lookup"><span data-stu-id="b55dc-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="b55dc-105">Après avoir déployé Skype entreprise Server 2019, vous devez configurer un itinéraire de Fédération pour votre site.</span><span class="sxs-lookup"><span data-stu-id="b55dc-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="b55dc-106">Pour pouvoir utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype entreprise Server 2019 doit être configuré pour utiliser cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="b55dc-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="b55dc-107">Pour activer le site Skype entreprise Server 2019 afin qu’il utilise le directeur et le serveur Edge du déploiement hérité, utilisez le générateur de topologie pour associer le pool de serveurs Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="b55dc-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="b55dc-108">Pour associer le pool Edge hérité à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="b55dc-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="b55dc-109">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b55dc-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="b55dc-110">Sélectionnez votre site, qui se trouve directement sous le nœud **Skype entreprise Server** .</span><span class="sxs-lookup"><span data-stu-id="b55dc-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="b55dc-111">Dans le menu **Actions**, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b55dc-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="b55dc-112">Dans le volet gauche, sélectionnez **Itinéraire de fédération**.</span><span class="sxs-lookup"><span data-stu-id="b55dc-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="b55dc-113">Sous **attribution**de l’itinéraire de Fédération du site, sélectionnez **activer la Fédération SIP**, puis sélectionnez le directeur hérité ou le serveur Edge hérité si aucun directeur n’est mentionné.</span><span class="sxs-lookup"><span data-stu-id="b55dc-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="b55dc-114">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b55dc-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="b55dc-115">Dans le générateur de topologie, sous le nœud Skype entreprise Server 2019, naviguez jusqu’aux **Pools frontaux** **Standard Edition Server** ou Enterprise Edition, cliquez avec le bouton droit sur le pool, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b55dc-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="b55dc-116">Sous **Associations**, activez la case à cocher en regard de **Associer un pool de serveurs Edge (pour les composants médias)**.</span><span class="sxs-lookup"><span data-stu-id="b55dc-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="b55dc-117">Dans la liste, sélectionnez le serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="b55dc-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="b55dc-118">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b55dc-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="b55dc-119">Dans le **Générateur de topologies**, sélectionnez le nœud de niveau supérieur, **Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="b55dc-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="b55dc-120">Depuis le menu **Actions**, cliquez sur **Publier la topologie**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b55dc-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="b55dc-121">Une fois l’**Assistant Publication** terminé, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b55dc-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

