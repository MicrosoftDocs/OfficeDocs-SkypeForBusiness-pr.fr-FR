---
title: Déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Résumé : Découvrez comment définir et de déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server.'
ms.openlocfilehash: 558c1324b488d36f69f760a2dc0484f22586d93c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885605"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="b290a-103">Déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="b290a-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="b290a-104">**Résumé :** Apprenez à définir et de déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="b290a-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="b290a-105">Les charges de travail voix entreprise, conférence rendez-vous et applications Enterprise Voice avancées (application Response Group, application parcage d’appel, le contrôle d’admission des appels (CAC) et ainsi de suite), sont disponibles dans les pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="b290a-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="b290a-106">La fonctionnalité du serveur de médiation est intégrée dans le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b290a-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="b290a-107">Un serveur de médiation autonome distinct n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="b290a-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="b290a-108">La seule exception est si vous configurez une jonction SIP (Session Initiation Protocol) pour la connexion à un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="b290a-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="b290a-109">Pour vous connecter à votre infrastructure Enterprise Voice à votre fournisseur de jonction SIP, un serveur de médiation distinct doit être déployé.</span><span class="sxs-lookup"><span data-stu-id="b290a-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="b290a-110">La connexion entre Skype pour Business Server (soit un serveur de médiation colocalisé sur un pool frontal ou un serveur de médiation autonome) et une passerelle est définie comme une association logique appelée une jonction.</span><span class="sxs-lookup"><span data-stu-id="b290a-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="b290a-111">Les rubriques de cette section décrivent comment définir une jonction et comment déployer un serveur de médiation autonome, si vous vous connectez à une jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="b290a-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="b290a-112">Définition d’un serveur de médiation dans le générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="b290a-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="b290a-113">Vous pouvez ajouter un serveur de médiation en tant qu’un rôle colocalisé sur un pool frontal ou définir un pool de serveurs de médiation autonome.</span><span class="sxs-lookup"><span data-stu-id="b290a-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="b290a-114">Pour ajouter un serveur de médiation à un pool frontal</span><span class="sxs-lookup"><span data-stu-id="b290a-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="b290a-115">Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour le Générateur de 2015Topology Business Server**.</span><span class="sxs-lookup"><span data-stu-id="b290a-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="b290a-116">Dans le Générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous souhaitez définir un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="b290a-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="b290a-117">Dans l’arborescence de la console, cliquez sur le type de pool frontal que vous souhaitez, puis cliquez sur **Nouveau Front End pool..**.</span><span class="sxs-lookup"><span data-stu-id="b290a-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="b290a-118">Naviguez dans l’Assistant **Définition d’un nouveau pool frontal** jusqu’à ce que vous accédiez à la page **Sélectionner des rôles serveur colocalisés**.</span><span class="sxs-lookup"><span data-stu-id="b290a-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="b290a-119">**Rôles serveur colocalisés Select**, activez l’option **Colocaliser le serveur de médiation**.</span><span class="sxs-lookup"><span data-stu-id="b290a-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b290a-120">Si le type de pool frontal que vous avez sélectionné est la version Enterprise Edition, le composant serveur de médiation s’être installé sur tous les serveurs frontaux de ce pool frontal.</span><span class="sxs-lookup"><span data-stu-id="b290a-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="b290a-121">Le **pool du tronçon suivant** utilisé par le serveur de médiation sera le pool frontal lequel le serveur de médiation est colocalisé.</span><span class="sxs-lookup"><span data-stu-id="b290a-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="b290a-122">Le **pool de serveurs Edge** utilisé par le serveur de médiation sera le même pool Edge associé au pool frontal lequel le serveur de médiation est colocalisé.</span><span class="sxs-lookup"><span data-stu-id="b290a-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="b290a-123">Cliquez sur **Utiliser par défaut** pour utiliser ce pool frontal pour acheminer les appels vers le réseau RTC.</span><span class="sxs-lookup"><span data-stu-id="b290a-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="b290a-124">Cliquez sur **Terminer** lorsque vous avez terminé d’associer un ou plusieurs homologues au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="b290a-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b290a-125">Avant de passer à la prochaine étape du processus de déploiement de voix entreprise, assurez-vous que le pool de serveur de médiation (c'est-à-dire Front-End pool avec le composant serveur de médiation colocalisé) à l’aide de noms de domaines complets que vous avez spécifié.</span><span class="sxs-lookup"><span data-stu-id="b290a-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="b290a-126">Cliquez sur le nœud **Skype pour Business Server 2015** , puis cliquez sur **Publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="b290a-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="b290a-127">Pour ajouter un serveur de médiation autonome</span><span class="sxs-lookup"><span data-stu-id="b290a-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="b290a-128">Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour le Générateur de 2015Topology Business Server**.</span><span class="sxs-lookup"><span data-stu-id="b290a-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="b290a-129">Dans le Générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous souhaitez définir un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="b290a-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="b290a-130">Dans l’arborescence de la console, cliquez sur le nœud **pools de médiation** , puis cliquez sur **pool de serveur de médiation**.</span><span class="sxs-lookup"><span data-stu-id="b290a-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="b290a-131">**Définir un nouveau Pool de médiation**, tapez le nom de domaine complet (FQDN) du pool serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="b290a-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="b290a-132">Effectuez ensuite l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b290a-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="b290a-133">Si vous souhaitez déployer plusieurs serveurs de médiation du pool pour fournir une haute disponibilité, puis sélectionnez le **pool de plusieurs ordinateurs**.</span><span class="sxs-lookup"><span data-stu-id="b290a-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="b290a-134">Vous devez [déployer](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) pour prendre en charge les pools de serveurs de médiation contient plusieurs serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="b290a-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="b290a-135">Si vous souhaitez ne déployer qu’un seul serveur de médiation du pool, car vous n’avez pas besoin de haute disponibilité, puis sélectionnez le **pool d’un seul ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="b290a-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="b290a-136">Ignorez l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="b290a-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="b290a-137">Si vous avez sélectionné **Pool de plusieurs ordinateurs** à l’étape précédente, dans l’élément **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Nom de domaine complet de l’ordinateur**, tapez le nom de domaine complet de chaque serveur présent dans le pool, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b290a-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="b290a-138">Répétez cette étape pour tous les autres serveurs de médiation que vous souhaitez ajouter au pool.</span><span class="sxs-lookup"><span data-stu-id="b290a-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="b290a-139">Une fois que vous avez défini tous les ordinateurs du pool, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b290a-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="b290a-140">Dans la page **Sélectionner le tronçon suivant** , cliquez sur **pool du tronçon suivant**, cliquez sur le nom de domaine complet du pool frontal qui utilisera ce pool de serveur de médiation, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="b290a-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="b290a-141">Dans la page **Sélectionner un serveur Edge**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b290a-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="b290a-142">Si vous souhaitez fournir une connectivité PSTN aux utilisateurs externes activés pour Enterprise Voice, sous **Sélectionnez le Pool Edge utilisé par ce serveur de médiation**, cliquez sur le nom de domaine complet du pool Edge Server qui utilise ce pool de serveur de médiation pour fournir une connectivité PSTN à les utilisateurs externes, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="b290a-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="b290a-143">Si vous n’envisagez pas permettre aux utilisateurs externes pour Enterprise Voice, ou si vous ne souhaitez pas fournir une connectivité PSTN aux utilisateurs lorsqu’ils sont en dehors du réseau interne, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="b290a-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="b290a-144">Cliquez sur le nœud **Skype pour Business Server 2015** , puis cliquez sur **Publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="b290a-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="b290a-145">Définir les Ports d’écoute de serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="b290a-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="b290a-146">Suivez les étapes décrites dans cette rubrique pour utiliser le Générateur de topologie pour définir les ports d’écoute à un serveur de médiation ou un pool pour accepter les connexions entrantes à partir d’un homologue de passerelle.</span><span class="sxs-lookup"><span data-stu-id="b290a-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="b290a-147">Pour modifier les Ports d’écoute de serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="b290a-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="b290a-148">Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour le Générateur de 2015Topology Business Server**.</span><span class="sxs-lookup"><span data-stu-id="b290a-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="b290a-149">Dans le Générateur de topologie, dans l’arborescence de la console, développez le nœud **pools de médiation** et cliquez sur le serveur de médiation créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="b290a-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="b290a-150">Par défaut, les ports d’écoute SIP sur le serveur de médiation sont 5070 pour le trafic TLS Skype pour Business Server et 5067 pour le trafic TLS de homologues (tels que les passerelles, PBX ou SBC).</span><span class="sxs-lookup"><span data-stu-id="b290a-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="b290a-151">Le port TCP est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="b290a-151">TCP port is disabled by default.</span></span> <span data-ttu-id="b290a-152">Vous devez activer le port TCP si vous disposez de passerelles qui ne prennent pas en charge le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="b290a-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="b290a-153">Spécifiez que la souhaitée TLS ou TCP d’écoute plage de ports du serveur de médiation accepter les connexions entrantes à partir de passerelles PSTN.</span><span class="sxs-lookup"><span data-stu-id="b290a-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b290a-p107">Vous n’êtes pas obligé d’entrer une plage de ports TCP si l’option **Activer le port TCP** n’est pas activée. Ce paramètre est facultatif.</span><span class="sxs-lookup"><span data-stu-id="b290a-p107">Entering a TCP port range is not required if **Enable TCP port** is not checked. This setting is optional.</span></span>
  

