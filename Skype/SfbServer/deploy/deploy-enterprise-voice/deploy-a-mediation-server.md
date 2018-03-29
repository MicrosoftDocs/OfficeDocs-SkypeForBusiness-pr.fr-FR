---
title: Déploiement d’un serveur de médiation dans le générateur de topologie dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Résumé : Apprenez à les définir et de déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server 2015.'
ms.openlocfilehash: bfb915528ba73851d3bd60cc8ff3b33b968376e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server-2015"></a><span data-ttu-id="7db4c-103">Déploiement d’un serveur de médiation dans le générateur de topologie dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7db4c-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7db4c-104">**Résumé :** Apprenez à les définir et de déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7db4c-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7db4c-105">La charge de travail de Voix Entreprise, conférence à distance avancées Voix Entreprise des applications et (application de groupe réponse, application d’appel Park, contrôle admission des appels (CAC) et ainsi de suite), sont disponibles dans les pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="7db4c-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="7db4c-106">La fonctionnalité du serveur de médiation est intégrée dans le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="7db4c-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="7db4c-107">Un serveur de médiation autonome distinct n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="7db4c-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="7db4c-108">La seule exception est si vous configurez une jonction SIP (Session Initiation Protocol) pour la connexion à un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="7db4c-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="7db4c-109">Pour vous connecter à votre infrastructure de Voix Entreprise à votre fournisseur de jonction SIP, un serveur de médiation distincte doit être déployé.</span><span class="sxs-lookup"><span data-stu-id="7db4c-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="7db4c-110">La connexion entre Skype pour Business Server (soit un serveur de médiation concernant un pool frontal ou un serveur de médiation autonome) et une passerelle est définie comme une association logique appelée un trunk.</span><span class="sxs-lookup"><span data-stu-id="7db4c-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="7db4c-111">Les rubriques de cette section décrivent comment définir un tronc et comment déployer un serveur de médiation autonome, si vous vous connectez à un SIP trunk.</span><span class="sxs-lookup"><span data-stu-id="7db4c-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="7db4c-112">Définition d’un serveur de médiation dans le générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="7db4c-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="7db4c-113">Vous pouvez ajouter un serveur de médiation en tant que colocalisé rôle sur un pool frontal, ou définir un autonome pool de serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="7db4c-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="7db4c-114">Pour ajouter un serveur de médiation pour un pool frontal</span><span class="sxs-lookup"><span data-stu-id="7db4c-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="7db4c-115">Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="7db4c-116">Dans le Générateur de topologies, dans l’arborescence de la console, développez le nom du site pour lequel vous souhaitez définir un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="7db4c-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="7db4c-117">Dans l’arborescence de la console, cliquez sur le type de pool frontal que vous voulez, puis cliquez sur **Nouveau Front End pool..**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="7db4c-118">Naviguez dans l’Assistant **Définition d’un nouveau pool frontal** jusqu’à ce que vous accédiez à la page **Sélectionner des rôles serveur colocalisés**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="7db4c-119">Dans **rôles de Select server colocalisé**, cochez l’option **Serveur de médiation colocaliser**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7db4c-120">Si le type de pool frontal que vous avez sélectionné est la version Enterprise Edition, le composant serveur de médiation va être installé sur tous les serveurs frontaux de ce pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="7db4c-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="7db4c-121">Le **pool du tronçon suivant** utilisé par le serveur de médiation sera le pool frontal où le serveur de médiation se trouve sur.</span><span class="sxs-lookup"><span data-stu-id="7db4c-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="7db4c-122">Le **pool de bord** utilisé par le serveur de médiation sera le même pool de bord associé au pool frontal où le serveur de médiation se trouve sur.</span><span class="sxs-lookup"><span data-stu-id="7db4c-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="7db4c-123">Cliquez sur **Utiliser par défaut** pour utiliser ce pool frontal pour acheminer les appels vers le RTC.</span><span class="sxs-lookup"><span data-stu-id="7db4c-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="7db4c-124">Cliquez sur **Terminer** lorsque vous avez terminé l’association d’un ou plusieurs collègues au pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="7db4c-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7db4c-125">Avant de passer à l’étape suivante dans le processus de déploiement de Voix Entreprise, assurez-vous que le pool de serveur de médiation (c'est-à-dire Front-End colocalisé de pool avec le composant serveur de médiation) utilise les noms de domaine complets que vous avez spécifié.</span><span class="sxs-lookup"><span data-stu-id="7db4c-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="7db4c-126">Cliquez sur le nœud **Skype pour Business Server 2015** , puis cliquez sur **Publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="7db4c-127">Pour ajouter un serveur de médiation autonome</span><span class="sxs-lookup"><span data-stu-id="7db4c-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="7db4c-128">Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="7db4c-129">Dans le Générateur de topologies, dans l’arborescence de la console, développez le nom du site pour lequel vous souhaitez définir un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="7db4c-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="7db4c-130">Dans l’arborescence de la console, cliquez sur le nœud **pools de médiation** , puis cliquez sur **pool de serveur de médiation**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="7db4c-131">**Définir un nouveau Pool de médiation**, tapez le nom de domaine pleinement qualifié (FQDN) du pool serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="7db4c-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="7db4c-132">Effectuez ensuite l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7db4c-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="7db4c-133">Si vous souhaitez déployer plusieurs serveurs de médiation dans le pool pour fournir une haute disponibilité, puis sélectionnez **plusieurs pool d’ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7db4c-134">Vous devez déployer (... /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) pour prendre en charge les pools de serveur de médiation qui ont plusieurs serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="7db4c-134">You must deploy  (../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="7db4c-135">Si vous souhaitez ne déployer qu’un seul serveur de médiation dans le pool, car vous n’avez pas besoin de haute disponibilité, puis sélectionnez le **pool d’un seul ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="7db4c-136">Ignorez l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="7db4c-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="7db4c-137">Si vous avez sélectionné **Pool de plusieurs ordinateurs** à l’étape précédente, dans l’élément **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Nom de domaine complet de l’ordinateur**, tapez le nom de domaine complet de chaque serveur présent dans le pool, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="7db4c-138">Répétez cette étape pour tous les autres serveurs de médiation que vous souhaitez ajouter à la liste.</span><span class="sxs-lookup"><span data-stu-id="7db4c-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="7db4c-139">Une fois que vous avez défini tous les ordinateurs du pool, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="7db4c-140">Dans la page **Sélectionnez le tronçon suivant** , cliquez sur **pool du tronçon suivant**, cliquez sur le nom de domaine complet du pool Front-End qui utilisent ce pool de serveur de médiation, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="7db4c-141">Dans la page **Sélectionner un serveur Edge**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7db4c-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="7db4c-142">Si vous souhaitez fournir la connectivité RTPC aux utilisateurs externes de Voix Entreprise, sous **Sélectionnez le Pool bord utilisé par ce serveur de médiation**, cliquez sur le nom de domaine complet du pool de serveur de transport Edge qui utilisera ce pool de serveur de médiation pour assurer la connectivité RTPC les utilisateurs externes, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="7db4c-143">Si vous ne souhaitez pas permettre aux utilisateurs externes de Voix Entreprise, ou si vous ne souhaitez pas fournir la connectivité RTPC aux utilisateurs lorsqu’ils sont en dehors du réseau interne, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="7db4c-144">Cliquez sur le nœud **Skype pour Business Server 2015** , puis cliquez sur **Publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="7db4c-145">Définir les Ports à l’écoute de serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="7db4c-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="7db4c-146">Suivez les étapes de cette rubrique pour utiliser le Générateur de topologies pour définir les ports d’écoute à un serveur de médiation ou pool accepte les connexions entrantes à partir d’un homologue de passerelle.</span><span class="sxs-lookup"><span data-stu-id="7db4c-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="7db4c-147">Pour modifier les Ports à l’écoute de serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="7db4c-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="7db4c-148">Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="7db4c-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="7db4c-149">Dans le Générateur de topologies, dans l’arborescence de la console, développez le nœud **pools de médiation** et sélectionnez le serveur de médiation précédemment créé.</span><span class="sxs-lookup"><span data-stu-id="7db4c-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="7db4c-150">Par défaut, les ports d’écoute SIP sur le serveur de médiation sont 5070 pour le trafic Skype pour Business Server TLS et 5067 pour le trafic TLS à partir des pairs (par exemple, des passerelles, PBX ou SBCs).</span><span class="sxs-lookup"><span data-stu-id="7db4c-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="7db4c-151">Le port TCP est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="7db4c-151">TCP port is disabled by default.</span></span> <span data-ttu-id="7db4c-152">Vous devez activer le port TCP si vous disposez de passerelles qui ne prennent pas en charge le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="7db4c-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="7db4c-153">Spécifiez que la souhaité TLS ou TCP écoute plage de ports du serveur de médiation acceptera des connexions entrantes à partir des passerelles RTPC.</span><span class="sxs-lookup"><span data-stu-id="7db4c-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7db4c-p107">Vous n’êtes pas obligé d’entrer une plage de ports TCP si l’option **Activer le port TCP** n’est pas activée. Ce paramètre est facultatif.</span><span class="sxs-lookup"><span data-stu-id="7db4c-p107">Entering a TCP port range is not required if **Enable TCP port** is not checked. This setting is optional.</span></span>
  

