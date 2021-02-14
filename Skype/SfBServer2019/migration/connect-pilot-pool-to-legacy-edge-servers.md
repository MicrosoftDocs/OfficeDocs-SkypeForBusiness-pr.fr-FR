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
description: Après avoir déployé Skype Entreprise Server 2019, vous devez configurer un itinéraire de fédération pour votre site. Pour utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype Entreprise Server 2019 doit être configuré pour utiliser cet itinéraire.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753924"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="22b10-104">Connexion du pool pilote aux serveurs Edge hérités</span><span class="sxs-lookup"><span data-stu-id="22b10-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="22b10-105">Après avoir déployé Skype Entreprise Server 2019, vous devez configurer un itinéraire de fédération pour votre site.</span><span class="sxs-lookup"><span data-stu-id="22b10-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="22b10-106">Pour utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype Entreprise Server 2019 doit être configuré pour utiliser cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="22b10-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="22b10-107">Pour permettre au site Skype Entreprise Server 2019 d’utiliser le directeur et le serveur Edge du déploiement hérité, utilisez le Générateur de topologie pour associer le pool edge hérité.</span><span class="sxs-lookup"><span data-stu-id="22b10-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="22b10-108">Pour associer le pool Edge hérité à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="22b10-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="22b10-109">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="22b10-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="22b10-110">Sélectionnez votre site, qui se trouve directement sous le nœud Skype Entreprise **Server.**</span><span class="sxs-lookup"><span data-stu-id="22b10-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="22b10-111">Dans le menu **Actions**, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="22b10-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="22b10-112">Dans le volet gauche, sélectionnez **Itinéraire de fédération**.</span><span class="sxs-lookup"><span data-stu-id="22b10-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="22b10-113">Sous **Attribution de l’itinéraire** de fédération du site, sélectionnez Activer la fédération **SIP,** puis sélectionnez le directeur hérité ou le serveur Edge hérité si aucun directeur n’est répertorié.</span><span class="sxs-lookup"><span data-stu-id="22b10-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="22b10-114">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="22b10-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="22b10-115">Dans le Générateur de topologie, sous le nœud Skype Entreprise Server 2019, accédez au serveur **Standard Edition** ou aux pools frontux **Enterprise Edition,** cliquez avec le bouton droit sur le pool, puis cliquez sur Modifier les propriétés. </span><span class="sxs-lookup"><span data-stu-id="22b10-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="22b10-116">Sous **Associations**, activez la case à cocher en regard de **Associer un pool de serveurs Edge (pour les composants médias)**.</span><span class="sxs-lookup"><span data-stu-id="22b10-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="22b10-117">Dans la liste, sélectionnez le serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="22b10-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="22b10-118">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="22b10-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="22b10-119">Dans **le Générateur de topologie,** sélectionnez le nœud le plus haut, Skype Entreprise **Server.**</span><span class="sxs-lookup"><span data-stu-id="22b10-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="22b10-120">Depuis le menu **Actions**, cliquez sur **Publier la topologie**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="22b10-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="22b10-121">Une fois l’**Assistant Publication** terminé, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="22b10-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

