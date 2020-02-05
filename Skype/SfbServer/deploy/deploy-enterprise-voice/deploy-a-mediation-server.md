---
title: Déploiement d’un serveur de médiation dans le générateur de topologies dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Résumé : Découvrez comment définir et déployer un serveur de médiation dans le générateur de topologies dans Skype entreprise Server.'
ms.openlocfilehash: c651ff3e254165161642c4e729d0d4e3f2983023
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767687"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="dca3e-103">Déploiement d’un serveur de médiation dans le générateur de topologies dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="dca3e-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="dca3e-104">**Résumé :** Apprenez à définir et déployer un serveur de médiation dans le générateur de topologies de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="dca3e-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="dca3e-105">La charge de travail voix entreprise, les conférences rendez-vous et les applications Advanced Enterprise voix (application de groupe de réponse, application de stationnement d’appel, contrôle d’admission des appels (CAC), etc.), sont disponibles dans des regroupements front-end.</span><span class="sxs-lookup"><span data-stu-id="dca3e-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="dca3e-106">Les fonctionnalités du serveur de médiation sont intégrées au serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="dca3e-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="dca3e-107">Il n’est pas nécessaire de disposer d’un serveur de médiation autonome séparé.</span><span class="sxs-lookup"><span data-stu-id="dca3e-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="dca3e-108">La seule exception est si vous configurez une jonction SIP (Session Initiation Protocol) pour la connexion à un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="dca3e-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="dca3e-109">Pour connecter l’infrastructure vocale de votre entreprise à votre fournisseur SIP Trunk, un serveur de médiation distinct doit être déployé.</span><span class="sxs-lookup"><span data-stu-id="dca3e-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="dca3e-110">La connexion entre Skype entreprise Server (un serveur de médiation localisé sur un pool frontal ou un serveur de médiation autonome) et une passerelle est définie comme une association logique appelée Trunk.</span><span class="sxs-lookup"><span data-stu-id="dca3e-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="dca3e-111">Les rubriques de cette section expliquent comment définir un élément Trunk et comment déployer un serveur de médiation autonome si vous vous connectez à un Trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="dca3e-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="dca3e-112">Définition d’un serveur de médiation dans le générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="dca3e-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="dca3e-113">Vous pouvez ajouter un serveur de médiation en tant que rôle colocalisé sur une réserve frontale ou définir un pool de serveurs de médiation autonome distinct.</span><span class="sxs-lookup"><span data-stu-id="dca3e-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="dca3e-114">Pour ajouter un serveur de médiation à un pool frontal</span><span class="sxs-lookup"><span data-stu-id="dca3e-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="dca3e-115">Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **Skype entreprise Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="dca3e-116">Dans le générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous voulez définir un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="dca3e-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="dca3e-117">Dans l’arborescence de la console, cliquez avec le bouton droit sur le type de réserve frontale souhaité, puis cliquez sur **nouveau pool frontal..**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="dca3e-118">Naviguez dans l’Assistant **Définition d’un nouveau pool frontal** jusqu’à ce que vous accédiez à la page **Sélectionner des rôles serveur colocalisés**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="dca3e-119">Dans **sélection de rôles de serveur colocalisés**, activez l’option **Collocate médiation Server**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dca3e-120">Si le type de réserve frontale que vous avez sélectionné est l’édition entreprise, le composant serveur de médiation sera installé sur tous les serveurs front-end de cette liste frontale.</span><span class="sxs-lookup"><span data-stu-id="dca3e-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="dca3e-121">Le **pool de prochains tronçons** utilisé par le serveur de médiation sera le pool frontal sur lequel est colocalisé le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="dca3e-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="dca3e-122">Le **pool Edge** utilisé par le serveur de médiation sera le même pool de périphérie associé au pool frontal sur lequel est localisé le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="dca3e-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="dca3e-123">Cliquez sur **définir par défaut** pour utiliser ce pool frontal pour acheminer les appels vers le RTC.</span><span class="sxs-lookup"><span data-stu-id="dca3e-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="dca3e-124">Cliquez sur **Terminer** lorsque vous avez terminé d’associer un ou plusieurs homologues au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="dca3e-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dca3e-125">Avant de passer à l’étape suivante du processus de déploiement de voix entreprise, assurez-vous que le pool de serveurs de médiation (c’est-à-dire le pool frontal doté du composant de serveur de médiation) utilise les noms de domaine complets que vous avez spécifiés.</span><span class="sxs-lookup"><span data-stu-id="dca3e-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="dca3e-126">Cliquez avec le bouton droit sur le nœud **Skype entreprise Server 2015** , puis cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="dca3e-127">Pour ajouter un serveur de médiation autonome</span><span class="sxs-lookup"><span data-stu-id="dca3e-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="dca3e-128">Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **Skype entreprise Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="dca3e-129">Dans le générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous voulez définir un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="dca3e-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="dca3e-130">Dans l’arborescence de la console, cliquez avec le bouton droit sur le nœud **pools de médiation** , puis cliquez sur **pool de serveurs de médiation**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="dca3e-131">Dans **définir un nouveau pool de médiation**, tapez le nom de domaine complet (FQDN) du pool de serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="dca3e-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="dca3e-132">Effectuez ensuite l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="dca3e-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="dca3e-133">Si vous voulez déployer plusieurs serveurs de médiation dans le pool afin d’offrir une disponibilité élevée, sélectionnez **plusieurs pools d’ordinateurs**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="dca3e-134">Vous devez [déployer](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) pour prendre en charge les pools de serveurs de médiation qui disposent de plusieurs serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="dca3e-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="dca3e-135">Si vous voulez déployer un seul serveur de médiation dans le pool, car vous n’avez pas besoin d’une haute disponibilité, sélectionnez **pool d’ordinateurs unique**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="dca3e-136">Ignorez l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="dca3e-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="dca3e-137">Si vous avez sélectionné **Pool de plusieurs ordinateurs** à l’étape précédente, dans l’élément **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Nom de domaine complet de l’ordinateur**, tapez le nom de domaine complet de chaque serveur présent dans le pool, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="dca3e-138">Répétez cette étape pour tous les autres serveurs de médiation que vous souhaitez ajouter au pool.</span><span class="sxs-lookup"><span data-stu-id="dca3e-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="dca3e-139">Une fois que vous avez défini tous les ordinateurs du pool, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="dca3e-140">Dans la page **Sélectionner le tronçon suivant** , cliquez sur **réserve de sauts suivant**, sur le nom de domaine complet (FQDN) du pool frontal qui utilisera ce pool de serveurs de médiation, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="dca3e-141">Dans la page **Sélectionner un serveur Edge**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="dca3e-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="dca3e-142">Si vous voulez fournir une connectivité RTC aux utilisateurs externes activés pour l’entreprise voix, sous **Sélectionner le pool de périphériques utilisés par ce serveur de médiation**, cliquez sur le nom de domaine complet du pool de serveur Edge qui utilisera ce pool de serveurs de médiation pour fournir une connectivité PSTN aux utilisateurs externes, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="dca3e-143">Si vous envisagez de ne pas autoriser les utilisateurs externes pour les voix d’entreprise, ou si vous ne souhaitez pas fournir de connectivité RTC aux utilisateurs en dehors du réseau interne, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="dca3e-144">Cliquez avec le bouton droit sur le nœud **Skype entreprise Server 2015** , puis cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="dca3e-145">Définir les ports d’écoute du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="dca3e-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="dca3e-146">Suivez les étapes décrites dans cette rubrique pour utiliser le générateur de topologie pour définir les ports d’écoute d’un serveur de médiation ou d’un pool qui acceptera les connexions entrantes d’un homologue de passerelle.</span><span class="sxs-lookup"><span data-stu-id="dca3e-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="dca3e-147">Pour modifier les ports d’écoute du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="dca3e-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="dca3e-148">Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **Skype entreprise Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="dca3e-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="dca3e-149">Dans le générateur de topologie, dans l’arborescence de la console, développez le nœud **pools de médiation** , puis cliquez avec le bouton droit sur le serveur de médiation précédemment créé.</span><span class="sxs-lookup"><span data-stu-id="dca3e-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="dca3e-150">Par défaut, les ports d’écoute SIP sur le serveur de médiation sont 5070 pour le trafic TLS de Skype entreprise Server et 5067 pour le trafic TLS d’homologues (par exemple, les passerelles, PBXes ou SBCs).</span><span class="sxs-lookup"><span data-stu-id="dca3e-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="dca3e-151">Le port TCP est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="dca3e-151">TCP port is disabled by default.</span></span> <span data-ttu-id="dca3e-152">Vous devez activer le port TCP si vous disposez de passerelles qui ne prennent pas en charge le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="dca3e-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="dca3e-153">Spécifiez la plage de port d’écoute TCP ou TLS souhaitée le serveur de médiation acceptera les connexions entrantes des passerelles RTC.</span><span class="sxs-lookup"><span data-stu-id="dca3e-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dca3e-p107">Vous n’êtes pas obligé d’entrer une plage de ports TCP si l’option **Activer le port TCP** n’est pas activée. Ce paramètre est facultatif.</span><span class="sxs-lookup"><span data-stu-id="dca3e-p107">Entering a TCP port range is not required if **Enable TCP port** is not checked. This setting is optional.</span></span>
  

