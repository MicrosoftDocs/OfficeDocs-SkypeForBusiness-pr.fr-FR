---
title: Connexion du pool pilote aux serveurs Edge hérités
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après le déploiement de Skype entreprise Server 2019, vous devez configurer un itinéraire de Fédération pour votre site. Pour utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype entreprise Server 2019 doit être configuré pour utiliser cet itinéraire.
ms.openlocfilehash: 20aacda86c6c49b319859d6f1c175ce6258caddb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288627"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="564c5-104">Connexion du pool pilote aux serveurs Edge hérités</span><span class="sxs-lookup"><span data-stu-id="564c5-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="564c5-105">Après le déploiement de Skype entreprise Server 2019, vous devez configurer un itinéraire de Fédération pour votre site.</span><span class="sxs-lookup"><span data-stu-id="564c5-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="564c5-106">Pour utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype entreprise Server 2019 doit être configuré pour utiliser cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="564c5-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="564c5-107">Pour permettre au site 2019 de Skype entreprise Server d’utiliser le directeur et le serveur Edge du déploiement hérité, utilisez le générateur de topologie pour associer le pool de périphériques hérité.</span><span class="sxs-lookup"><span data-stu-id="564c5-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="564c5-108">Pour associer le pool de bords antérieurs à l’aide du générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="564c5-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="564c5-109">Ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="564c5-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="564c5-110">Sélectionnez votre site, qui se trouve juste en dessous du nœud **Skype entreprise Server** .</span><span class="sxs-lookup"><span data-stu-id="564c5-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="564c5-111">Dans le menu **actions** , cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="564c5-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="564c5-112">Dans le volet gauche, sélectionnez **gamme de Fédération**.</span><span class="sxs-lookup"><span data-stu-id="564c5-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="564c5-113">Sous **affectation**de l’itinéraire de la Fédération de sites, sélectionnez **activer la Fédération SIP**, puis sélectionnez le directeur hérité ou le serveur de périphérie hérité si aucun réalisateur n’est répertorié.</span><span class="sxs-lookup"><span data-stu-id="564c5-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="564c5-114">Cliquez sur **OK** pour fermer la page **modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="564c5-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="564c5-115">Dans le générateur de topologie, sous le nœud Skype entreprise Server 2019, naviguez jusqu’au pool **Standard Edition Server** ou **Enterprise Edition**, cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="564c5-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="564c5-116">Sous **associations**, activez la case à cocher en regard de **associer le pool de bords (pour les composants multimédias)**.</span><span class="sxs-lookup"><span data-stu-id="564c5-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="564c5-117">Dans la liste, sélectionnez le serveur de bord hérité.</span><span class="sxs-lookup"><span data-stu-id="564c5-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="564c5-118">Cliquez sur **OK** pour fermer la page **modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="564c5-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="564c5-119">Dans le **Générateur de topologie**, sélectionnez le nœud supérieur, **Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="564c5-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="564c5-120">Dans le menu **action** , cliquez sur **publier la topologie**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="564c5-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="564c5-121">À la fin de l' **Assistant Publication** , cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="564c5-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

