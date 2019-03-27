---
title: Connexion du pool pilote aux serveurs Edge hérités
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après avoir déployé Skype pour Business Server 2019, vous devez configurer un itinéraire de fédération pour votre site. Pour pouvoir utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype pour Business Server 2019 doit être configuré pour utiliser cet itinéraire.
ms.openlocfilehash: 5a3498041b4af762d184cd56e3883a90612b13e0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874744"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="0bb5b-104">Connexion du pool pilote aux serveurs Edge hérités</span><span class="sxs-lookup"><span data-stu-id="0bb5b-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="0bb5b-105">Après avoir déployé Skype pour Business Server 2019, vous devez configurer un itinéraire de fédération pour votre site.</span><span class="sxs-lookup"><span data-stu-id="0bb5b-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="0bb5b-106">Pour pouvoir utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype pour Business Server 2019 doit être configuré pour utiliser cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="0bb5b-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="0bb5b-107">Pour activer le Skype pour Business Server 2019 site à utiliser le directeur et le serveur de périphérie du déploiement hérité, utilisez le Générateur de topologie pour associer le pool Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="0bb5b-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="0bb5b-108">Pour associer le pool Edge hérité à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="0bb5b-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="0bb5b-109">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="0bb5b-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="0bb5b-110">Sélectionnez votre site, qui est directement sous le nœud **Skype pour Business Server** .</span><span class="sxs-lookup"><span data-stu-id="0bb5b-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="0bb5b-111">Dans le menu **Actions** , cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="0bb5b-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="0bb5b-112">Dans le volet gauche, sélectionnez **itinéraire de fédération**.</span><span class="sxs-lookup"><span data-stu-id="0bb5b-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="0bb5b-113">Sous **attribution itinéraire de fédération du Site**, sélectionnez **Activer la fédération SIP**, puis sélectionnez le directeur hérité, ou le serveur Edge hérité si aucun directeur n’est répertorié.</span><span class="sxs-lookup"><span data-stu-id="0bb5b-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="0bb5b-114">Cliquez sur **OK** pour fermer la page **Modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="0bb5b-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="0bb5b-115">Dans le Générateur de topologie, sous le Skype pour nœud Business Server 2019, accédez au **serveur Standard Edition server** ou **pools frontaux Enterprise Edition**, avec le bouton droit de la liste, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="0bb5b-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="0bb5b-116">Sous **Associations**, activez la case à cocher en regard de **pool Edge associé (pour les composants multimédias)**.</span><span class="sxs-lookup"><span data-stu-id="0bb5b-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="0bb5b-117">Dans la liste, sélectionnez le serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="0bb5b-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="0bb5b-118">Cliquez sur **OK** pour fermer la page **Modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="0bb5b-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="0bb5b-119">Dans **Le Générateur de topologie**, sélectionnez le nœud de niveau supérieur, **Skype pour Business Server**.</span><span class="sxs-lookup"><span data-stu-id="0bb5b-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="0bb5b-120">Dans le menu **Action** , cliquez sur **Publier la topologie**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="0bb5b-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="0bb5b-121">Lorsque l' **Assistant Publication** a terminé, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="0bb5b-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

