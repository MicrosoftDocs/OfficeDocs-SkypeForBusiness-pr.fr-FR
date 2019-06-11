---
title: 'Lync Server 2013: définir un serveur de médiation dans le générateur de topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f1356217b9effe3f2282f6931b601e84aa46770
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="f0b11-102">Définir un serveur de médiation dans le générateur de topologies de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0b11-102">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0b11-103">_**Dernière modification de la rubrique:** 2013-03-25_</span><span class="sxs-lookup"><span data-stu-id="f0b11-103">_**Topic Last Modified:** 2013-03-25_</span></span>

<span data-ttu-id="f0b11-104">Suivez les étapes décrites dans cette rubrique pour utiliser le générateur de topologie pour définir un serveur de médiation autonome ou un pool colocalisé avec un pool frontal sur un site pour lequel vous n’avez pas encore déployé Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="f0b11-104">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or a pool collocated with a Front End pool at a site for which you did not previously deploy Enterprise Voice.</span></span>

<span data-ttu-id="f0b11-105">Vous pouvez définir une topologie à l’aide d’un compte membre du groupe administrateurs.</span><span class="sxs-lookup"><span data-stu-id="f0b11-105">You can define a topology using an account that is a member of the Administrators group.</span></span>

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a><span data-ttu-id="f0b11-106">Définir un serveur de médiation en tant que pool frontal</span><span class="sxs-lookup"><span data-stu-id="f0b11-106">Define Mediation Server collocated to a Front End pool</span></span>

<span data-ttu-id="f0b11-107">Suivez les étapes décrites dans cette rubrique pour utiliser le générateur de topologie pour définir un serveur de médiation colocalisé vers un pool frontal dans un site sur lequel Enterprise Voice n’a pas encore été déployé.</span><span class="sxs-lookup"><span data-stu-id="f0b11-107">Follow the steps in this topic to use Topology Builder to define a Mediation Server collocated to a Front End pool in a site where Enterprise Voice has not been previously deployed.</span></span>

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="f0b11-108">Pour ajouter un serveur de médiation à un pool frontal</span><span class="sxs-lookup"><span data-stu-id="f0b11-108">To Add a Mediation Server to a Front End pool</span></span>

1.  <span data-ttu-id="f0b11-109">Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f0b11-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="f0b11-110">Dans le générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous voulez définir un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="f0b11-110">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>

3.  <span data-ttu-id="f0b11-111">Dans l’arborescence de la console, cliquez avec le bouton droit sur le type de réserve frontale souhaité, puis cliquez sur **nouveau pool frontal..**.</span><span class="sxs-lookup"><span data-stu-id="f0b11-111">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>

4.  <span data-ttu-id="f0b11-112">Naviguez dans l’Assistant **Définition d’un nouveau pool frontal** jusqu’à ce que vous accédiez à la page **Sélectionner des rôles serveur colocalisés**.</span><span class="sxs-lookup"><span data-stu-id="f0b11-112">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>

5.  <span data-ttu-id="f0b11-113">Dans **sélection de rôles de serveur**colocalisés, activez l’option **Collocate médiation Server**.</span><span class="sxs-lookup"><span data-stu-id="f0b11-113">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="f0b11-114">Si le type de réserve frontale que vous avez sélectionné est l’édition entreprise, le composant serveur de médiation sera installé sur tous les serveurs front-end de cette liste frontale.</span><span class="sxs-lookup"><span data-stu-id="f0b11-114">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f0b11-115">Le <STRONG>pool de prochains tronçons</STRONG> utilisé par le serveur de médiation sera le pool frontal sur lequel est colocalisé le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="f0b11-115">The <STRONG>Next hop pool</STRONG> used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f0b11-116">Le <STRONG>pool Edge</STRONG> utilisé par le serveur de médiation sera le même pool de périphérie associé au pool frontal sur lequel est localisé le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="f0b11-116">The <STRONG>Edge pool</STRONG> used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="f0b11-117">Cliquez sur **définir par défaut** pour utiliser ce pool frontal pour acheminer les appels à partir de Microsoft Office Communications Server 2007 R2 vers PSTN.</span><span class="sxs-lookup"><span data-stu-id="f0b11-117">Click **Make Default** to use this Front End pool to route calls from Microsoft Office Communications Server 2007 R2 to the PSTN.</span></span>

7.  <span data-ttu-id="f0b11-118">Cliquez sur **Terminer** lorsque vous avez terminé d’associer un ou plusieurs homologues au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="f0b11-118">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f0b11-119">Avant de passer à l’étape suivante du processus de déploiement de voix entreprise, assurez-vous que le pool de serveurs de médiation (c’est-à-dire le pool frontal doté du composant de serveur de médiation) utilise les noms de domaine complets que vous avez spécifiés.</span><span class="sxs-lookup"><span data-stu-id="f0b11-119">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span>

    
    </div>

8.  <span data-ttu-id="f0b11-120">Ensuite, suivez les procédures décrites dans la rubrique [publier la topologie de Lync Server 2013](lync-server-2013-publish-the-topology.md) dans la documentation du Guide de déploiement pour ajouter le serveur de médiation à votre topologie avant de passer à l’étape suivante de la modification des ports d’écoute du serveur de médiation, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f0b11-120">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment Guide documentation to add the Mediation Server to your topology before proceeding to the next step of modifying the listening ports of the Mediation Server if needed.</span></span> <span data-ttu-id="f0b11-121">Vous devez publier votre topologie chaque fois que vous utilisez le générateur de topologie pour définir ou modifier votre topologie.</span><span class="sxs-lookup"><span data-stu-id="f0b11-121">You must publish your topology each time you use Topology Builder to define or modify your topology.</span></span>

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a><span data-ttu-id="f0b11-122">Définir un serveur de médiation autonome</span><span class="sxs-lookup"><span data-stu-id="f0b11-122">Define stand-alone Mediation Server</span></span>

<span data-ttu-id="f0b11-123">Suivez les étapes décrites dans cette rubrique pour utiliser le générateur de topologie pour définir un serveur de médiation autonome ou un pool sur un site sur lequel Enterprise Voice n’a pas encore été déployé.</span><span class="sxs-lookup"><span data-stu-id="f0b11-123">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or pool at a site where Enterprise Voice has not been previously deployed.</span></span>

<span data-ttu-id="f0b11-124">Si vous avez déjà déployé des serveurs de médiation colocalisés vers ce site, vous pouvez ignorer cette section et [installer les fichiers pour le serveur de médiation dans Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) avant de procéder à la [configuration de Trunks dans Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="f0b11-124">If you already deployed Mediation Servers collocated to Front End pools at this site, you can skip this section and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) before proceeding to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f0b11-125">Cette section suppose que vous avez déjà configuré au moins un pool frontal, comme décrit dans la rubrique <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">définir et configurer un pool frontal ou un serveur Standard Edition dans Lync server 2013</A> et <A href="lync-server-2013-publish-the-topology.md">publier la topologie dans Lync Server 2013</A> dans le Guide de déploiement. accompagnant.</span><span class="sxs-lookup"><span data-stu-id="f0b11-125">This section assumes that you have already setup at least one Front End pool, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment Guide documentation.</span></span>



</div>

<div>

## <a name="to-add-a-mediation-server"></a><span data-ttu-id="f0b11-126">Pour ajouter un serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="f0b11-126">To Add a Mediation Server</span></span>

1.  <span data-ttu-id="f0b11-127">Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f0b11-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="f0b11-128">Dans le générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous voulez définir un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="f0b11-128">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>

3.  <span data-ttu-id="f0b11-129">Dans l’arborescence de la console, cliquez avec le bouton droit sur le nœud Pools de **médiation** , puis cliquez sur **pool de serveurs de médiation**.</span><span class="sxs-lookup"><span data-stu-id="f0b11-129">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>

4.  <span data-ttu-id="f0b11-130">Dans **définir un nouveau pool de médiation**, tapez le nom de domaine complet (FQDN) du pool de serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="f0b11-130">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>

5.  <span data-ttu-id="f0b11-131">Effectuez ensuite l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f0b11-131">Next, do one of the following:</span></span>
    
      - <span data-ttu-id="f0b11-132">Si vous voulez déployer plusieurs serveurs de médiation dans le pool afin d’offrir une disponibilité élevée, sélectionnez **plusieurs pools d’ordinateurs**.</span><span class="sxs-lookup"><span data-stu-id="f0b11-132">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f0b11-133">Vous devez déployer l’équilibrage de charge DNS pour prendre en charge les pools de serveurs de médiation qui disposent de plusieurs serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="f0b11-133">You must deploy DNS load balancing to support Mediation Server pools that have multiple Mediation Servers.</span></span> <span data-ttu-id="f0b11-134">Pour plus d’informations, consultez la section utilisation de l’équilibrage de charge DNS sur les pools de serveurs de médiation de l' <A href="lync-server-2013-dns-load-balancing.md">équilibrage de charge DNS dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="f0b11-134">For details, see the Using DNS Load Balancing on Mediation Server Pools section of <A href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</A> in the Planning documentation.</span></span>

        
        </div>
    
      - <span data-ttu-id="f0b11-135">Si vous voulez déployer un seul serveur de médiation dans le pool, car vous n’avez pas besoin d’une haute disponibilité, sélectionnez **pool d’ordinateurs unique**.</span><span class="sxs-lookup"><span data-stu-id="f0b11-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="f0b11-136">Ignorez l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="f0b11-136">Skip the following step.</span></span>

6.  <span data-ttu-id="f0b11-137">Si vous avez sélectionné **Pool de plusieurs ordinateurs** à l’étape précédente, dans l’élément **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Nom de domaine complet de l’ordinateur**, tapez le nom de domaine complet de chaque serveur présent dans le pool, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f0b11-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="f0b11-138">Répétez cette étape pour tous les autres serveurs de médiation que vous souhaitez ajouter au pool.</span><span class="sxs-lookup"><span data-stu-id="f0b11-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="f0b11-139">Une fois que vous avez défini tous les ordinateurs du pool, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f0b11-139">When you have defined all the computers in the pool, click **Next**.</span></span>

7.  <span data-ttu-id="f0b11-140">Dans la page **Sélectionner le tronçon suivant** , cliquez sur **réserve de sauts suivant**, sur le nom de domaine complet (FQDN) du pool frontal qui utilisera ce pool de serveurs de médiation, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f0b11-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>

8.  <span data-ttu-id="f0b11-141">Dans la page **Sélectionner un serveur Edge**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f0b11-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
      - <span data-ttu-id="f0b11-142">Si vous voulez fournir une connectivité RTC aux utilisateurs externes activés pour Enterprise Voice, sous **Sélectionner le pool de périphériques utilisés par ce serveur de médiation**, cliquez sur le nom de domaine complet (FQDN) du pool de serveur Edge qui utilisera ce pool de serveurs de médiation pour fournir une connectivité PSTN à utilisateurs externes, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f0b11-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
      - <span data-ttu-id="f0b11-143">Si vous envisagez de ne pas autoriser les utilisateurs externes pour les voix d’entreprise, ou si vous ne souhaitez pas fournir de connectivité RTC aux utilisateurs en dehors du réseau interne, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f0b11-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>

9.  <span data-ttu-id="f0b11-144">Ensuite, suivez les procédures décrites dans [publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md) dans la documentation de déploiement pour ajouter le serveur de médiation à la topologie.</span><span class="sxs-lookup"><span data-stu-id="f0b11-144">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation to add the Mediation Server to the topology.</span></span> <span data-ttu-id="f0b11-145">Vous devez publier votre topologie chaque fois que vous utilisez le générateur de topologie pour créer ou modifier votre topologie de manière à ce que les données puissent être utilisées pour installer les fichiers des serveurs exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0b11-145">You must publish your topology each time you use Topology Builder to build or modify your topology so that the data can be used to install the files for servers that are running Lync Server.</span></span> <span data-ttu-id="f0b11-146">Passez ensuite aux étapes suivantes pour modifier les ports d’écoute sur le serveur de médiation, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f0b11-146">Then continue to the next steps to modify the listening ports on the Mediation Server, if necessary.</span></span>

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="f0b11-147">Définir les ports d’écoute du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="f0b11-147">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="f0b11-148">Suivez les étapes décrites dans cette rubrique pour utiliser le générateur de topologie pour définir les ports d’écoute d’un serveur de médiation ou d’un pool qui acceptera les connexions entrantes d’un homologue de passerelle.</span><span class="sxs-lookup"><span data-stu-id="f0b11-148">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="f0b11-149">Pour modifier les ports d’écoute du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="f0b11-149">To Modify the Mediation Server Listening Ports</span></span>

1.  <span data-ttu-id="f0b11-150">Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f0b11-150">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="f0b11-151">Dans le générateur de topologie, dans l’arborescence de la console, développez le nœud Pools de **médiation** , puis cliquez avec le bouton droit sur le serveur de médiation précédemment créé.</span><span class="sxs-lookup"><span data-stu-id="f0b11-151">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>

3.  <span data-ttu-id="f0b11-152">Par défaut, les ports d’écoute SIP sur le serveur de médiation sont 5070 pour le trafic TLS provenant de Lync Server, 5067 pour le trafic TLS d’homologues (passerelles, PBXes ou SBCs).</span><span class="sxs-lookup"><span data-stu-id="f0b11-152">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Lync Server, 5067 for TLS traffic from peers (gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="f0b11-153">Le port TCP est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="f0b11-153">TCP port is disabled by default.</span></span> <span data-ttu-id="f0b11-154">Vous devez activer le port TCP si vous disposez de passerelles qui ne prennent pas en charge le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="f0b11-154">You must enable TCP port if you have gateways that do not support TLS.</span></span>

4.  <span data-ttu-id="f0b11-155">Spécifiez la plage de port d’écoute TCP ou TLS souhaitée le serveur de médiation acceptera les connexions entrantes des passerelles RTC.</span><span class="sxs-lookup"><span data-stu-id="f0b11-155">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f0b11-156">Vous n’êtes pas obligé d’entrer une plage de ports TCP si l’option <STRONG>Activer le port TCP</STRONG> n’est pas activée.</span><span class="sxs-lookup"><span data-stu-id="f0b11-156">Entering a TCP port range is not required if <STRONG>Enable TCP port</STRONG> is not checked.</span></span> <span data-ttu-id="f0b11-157">Ce paramètre est facultatif.</span><span class="sxs-lookup"><span data-stu-id="f0b11-157">This setting is optional.</span></span>

    
    </div>

<span data-ttu-id="f0b11-158">Ensuite, [définissez une passerelle dans le générateur de topologie de Lync server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) et installez les fichiers sur chaque serveur de médiation du pool en suivant les procédures décrites dans [installer le fichier pour le serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="f0b11-158">Next, [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) and install the files on each Mediation Server in the pool by following the procedures in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

