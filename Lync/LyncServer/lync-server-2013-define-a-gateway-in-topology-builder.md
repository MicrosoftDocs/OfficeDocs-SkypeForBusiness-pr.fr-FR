---
title: 'Lync Server 2013 : définition d’une passerelle dans le générateur de topologies'
description: 'Lync Server 2013 : définition d’une passerelle dans le générateur de topologies.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f8bf09f06f54d8988c8c9a9e385ef251a960bd6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567800"
---
# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="fe98e-103">Définition d’une passerelle dans le générateur de topologies dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe98e-103">Define a gateway in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe98e-104">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="fe98e-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="fe98e-105">Procédez comme suit pour utiliser le générateur de topologie afin de définir un *homologue* avec lequel vous pouvez associer un serveur de médiation pour fournir la connectivité au réseau téléphonique commuté (PSTN) pour les utilisateurs activés pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="fe98e-105">Follow these steps to use Topology Builder to define a *peer* with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="fe98e-106">Un homologue du serveur de médiation peut être une passerelle RTC, un système IP-PBX ou un contrôleur SBC (session Border Controller) pour un fournisseur de services de téléphonie Internet (téléphonie Internet) auquel vous vous connectez en configurant une jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="fe98e-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe98e-107">Cette rubrique suppose que vous ayez configuré au moins un pool frontal interne ou un serveur Standard Edition dans au moins un site central avec un serveur de médiation colocalisé ou autonome, comme décrit dans <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and Configure a front end pool or Standard Edition Server in Lync server 2013</A> et <A href="lync-server-2013-publish-the-topology.md">publish the Topology in Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="fe98e-107">This topic assumes that you have set up at least one internal Front End pool or Standard Edition server in at least one central site with a collocated or stand-alone Mediation Server, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="fe98e-108">Cette rubrique suppose également que vous ayez vérifié que votre infrastructure répond aux exigences décrites dans <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software Prerequisites for Enterprise Voice in Lync server 2013</A> et <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration Prerequisites for Enterprise Voice in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fe98e-108">This topic also assumes that you have verified that your infrastructure meets the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="fe98e-109">Pour définir un homologue pour le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="fe98e-109">To Define a Peer for the Mediation Server</span></span>

1.  <span data-ttu-id="fe98e-110">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="fe98e-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="fe98e-111">Sous Lync Server 2013, le nom de votre site, composants partagés, cliquez avec le bouton droit sur le nœud **passerelles RTC** , puis cliquez sur **nouvelle passerelle PSTN**.</span><span class="sxs-lookup"><span data-stu-id="fe98e-111">Under Lync Server 2013, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
    
    <span data-ttu-id="fe98e-112">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span><span class="sxs-lookup"><span data-stu-id="fe98e-112">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span></span>

3.  <span data-ttu-id="fe98e-113">Dans **Définir une nouvelle passerelle IP/PSTN**, tapez le nom de domaine complet ou l’adresse IP de l’homologue, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="fe98e-113">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    <span data-ttu-id="fe98e-114">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span><span class="sxs-lookup"><span data-stu-id="fe98e-114">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe98e-115">Si vous spécifiez le protocole TLS (Transport Layer Security) comme type de transport, vous devez spécifier le nom de domaine complet au lieu de l’adresse IP de l’homologue du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="fe98e-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="fe98e-116">Définissez le mode d’écoute (IPv4 ou IPv6) de l’adresse IP de votre nouvelle passerelle PSTN, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="fe98e-116">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>
    
    <span data-ttu-id="fe98e-117">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span><span class="sxs-lookup"><span data-stu-id="fe98e-117">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span></span>

5.  <span data-ttu-id="fe98e-118">Définissez une *jonction racine* pour la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="fe98e-118">Define a *root trunk* for the PSTN gateway.</span></span> <span data-ttu-id="fe98e-119">Une jonction est une connexion logique entre un serveur de médiation et une passerelle identifiée de manière unique par le tuple.</span><span class="sxs-lookup"><span data-stu-id="fe98e-119">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="fe98e-120">{Nom de domaine complet du serveur de médiation, port d’écoute du serveur de médiation (TLS ou TCP) : IP de passerelle et nom de domaine complet, port d’écoute de passerelle}</span><span class="sxs-lookup"><span data-stu-id="fe98e-120">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
      - <span data-ttu-id="fe98e-121">Lors de la définition d’une passerelle PSTN dans le générateur de topologie, vous devez définir une jonction racine pour pouvoir ajouter la passerelle PSTN à votre topologie.</span><span class="sxs-lookup"><span data-stu-id="fe98e-121">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
      - <span data-ttu-id="fe98e-122">Vous ne pouvez pas supprimer la jonction racine tant que la passerelle PSTN associée n’est pas supprimée.</span><span class="sxs-lookup"><span data-stu-id="fe98e-122">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
    <span data-ttu-id="fe98e-123">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span><span class="sxs-lookup"><span data-stu-id="fe98e-123">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span></span>

6.  <span data-ttu-id="fe98e-124">Sous **port d’écoute pour la passerelle IP/PSTN**, tapez le port d’écoute que la passerelle, PBX ou SBC utilisera pour les messages SIP provenant du serveur de médiation qui sera associé à la jonction racine de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="fe98e-124">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="fe98e-125">(Par défaut, les ports sont 5066 pour TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security) sur une passerelle PSTN, un autocommutateur privé (PBX) ou un contrôleur SBC.</span><span class="sxs-lookup"><span data-stu-id="fe98e-125">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="fe98e-126">Sur un Survivable Branch appliance sur un site de succursale, les ports par défaut sont 5081 pour TCP et 5082 pour TLS.)</span><span class="sxs-lookup"><span data-stu-id="fe98e-126">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>

7.  <span data-ttu-id="fe98e-127">Sous **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe98e-127">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe98e-128">Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation pouvant utiliser le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="fe98e-128">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

8.  <span data-ttu-id="fe98e-129">Sous **serveur de médiation associé**, sélectionnez le pool de serveurs de médiation à associer à la jonction racine de cette passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="fe98e-129">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>

9.  <span data-ttu-id="fe98e-130">Sous **port du serveur de médiation associé**, tapez le port d’écoute que le serveur de médiation utilisera pour les messages SIP à partir de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="fe98e-130">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe98e-131">Avec la prise en charge de plusieurs tronçons dans Lync Server 2013, plusieurs ports de signalisation SIP peuvent être définis sur le serveur de médiation afin d’être utilisés pour la communication avec plusieurs passerelles RTC.</span><span class="sxs-lookup"><span data-stu-id="fe98e-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server to be used for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="fe98e-132">Lors de la définition d’une jonction, le <STRONG>port du serveur de médiation associé</STRONG> doit se situer dans la plage des ports d’écoute pour le protocole respectif autorisé par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="fe98e-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="fe98e-133">Cette plage de ports est définie sous Lync Server 2013 et pools de médiation.</span><span class="sxs-lookup"><span data-stu-id="fe98e-133">This port range is defined under Lync Server 2013 and Mediation Pools.</span></span> <span data-ttu-id="fe98e-134">Cliquez avec le bouton droit sur le pool de serveurs de médiation qui vous intéresse, puis sélectionnez <STRONG>modifier les propriétés</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fe98e-134">Right-click the Mediation Server pool of interest, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="fe98e-135">Spécifiez la plage de ports dans le champ <STRONG>Ports d’écoute</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fe98e-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

10. <span data-ttu-id="fe98e-136">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="fe98e-136">Click **Finish**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fe98e-137">Avant de terminer cette étape, assurez-vous que l’homologue que vous avez défini est en cours d’exécution et qu’il utilise le nom de domaine complet ou l’adresse IP que vous avez spécifié(e).</span><span class="sxs-lookup"><span data-stu-id="fe98e-137">Before you finish this step, be sure that the peer that you defined is running and using the FQDN or IP address that you specified.</span></span>



</div>

<span data-ttu-id="fe98e-138">Ensuite, pour ajouter l’homologue à la topologie, suivez les procédures de la [publication de la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="fe98e-138">Next, to add the peer to the topology, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span> <span data-ttu-id="fe98e-139">Vous devez publier votre topologie chaque fois que vous utilisez le générateur de topologie pour créer ou modifier votre topologie, afin que les données puissent être utilisées pour installer les fichiers pour les serveurs qui exécutent Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe98e-139">You must publish your topology each time that you use Topology Builder to build or modify your topology, so that the data can be used to install the files for servers that are running Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe98e-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fe98e-140">See Also</span></span>


[<span data-ttu-id="fe98e-141">Modifier une jonction dans le générateur de topologies dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe98e-141">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

