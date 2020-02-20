---
title: 'Lync Server 2013 : définir des jonctions supplémentaires dans le générateur de topologies'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f4c31dc9b3e23f591e1084ba649bf00a4c8a0f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="bcdf4-102">Définir d’autres jonctions dans le générateur de topologies dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcdf4-102">Define additional trunks in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcdf4-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="bcdf4-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="bcdf4-104">Procédez comme suit pour utiliser le générateur de topologie afin de définir une jonction supplémentaire à laquelle vous pouvez associer un *homologue* à un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-104">Follow these steps to use Topology Builder to define an additional trunk to which you can associate a *peer* with a Mediation Server.</span></span> <span data-ttu-id="bcdf4-105">Un homologue fournit aux utilisateurs activés pour voix entreprise la connectivité au réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="bcdf4-105">A peer provides users enabled for Enterprise Voice with connectivity to the public switched telephone network (PSTN).</span></span> <span data-ttu-id="bcdf4-106">Un homologue peut être une passerelle RTC, un système IP-PBX ou un contrôleur SBC (session Border Controller) pour un fournisseur de services de téléphonie Internet (téléphonie Internet).</span><span class="sxs-lookup"><span data-stu-id="bcdf4-106">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span> <span data-ttu-id="bcdf4-107">La jonction définit cette connexion entre le serveur de médiation et l’homologue.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-107">The trunk defines this connection between the Mediation Server and peer.</span></span> <span data-ttu-id="bcdf4-108">Plusieurs jonctions peuvent être définies par serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-108">Multiple trunks can be defined per Mediation Server.</span></span> <span data-ttu-id="bcdf4-109">Un serveur de médiation peut être associé à plusieurs homologues.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-109">A Mediation Server can be associated with multiple peers.</span></span>

<span data-ttu-id="bcdf4-110">Une jonction est une connexion logique entre un serveur de médiation et une passerelle identifiée de manière unique par le tuple :</span><span class="sxs-lookup"><span data-stu-id="bcdf4-110">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple:</span></span>

<span data-ttu-id="bcdf4-111">{Nom de domaine complet du serveur de médiation, port d’écoute du serveur de médiation (TLS ou TCP) : IP de passerelle et nom de domaine complet, port d’écoute de passerelle}</span><span class="sxs-lookup"><span data-stu-id="bcdf4-111">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bcdf4-112">Cette rubrique suppose que vous avez configuré une passerelle PSTN et une jonction racine avec au moins un serveur ou pool de médiation colocalisé ou autonome, comme décrit dans <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">define a Gateway in Topology Builder in Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-112">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="bcdf4-113">Cette rubrique suppose que vous ayez configuré au moins un pool frontal ou un serveur Standard Edition dans au moins un site central, comme décrit dans <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and Configure a front end pool or Standard Edition Server in Lync server 2013</A> et <A href="lync-server-2013-publish-the-topology.md">publish the Topology in Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-113">This topic assumes that you have set up at least one Front End pool or Standard Edition server in at least one central site, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="bcdf4-114">Pour définir une jonction supplémentaire entre un serveur de médiation et un homologue de passerelle</span><span class="sxs-lookup"><span data-stu-id="bcdf4-114">To Define an additional Trunk between a Mediation Server and a Gateway Peer</span></span>

1.  <span data-ttu-id="bcdf4-115">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="bcdf4-116">Sous Lync Server 2013, le nom de votre site, **composants partagés**, cliquez avec le bouton droit sur le nœud **jonctions** , puis cliquez sur **nouvelle jonction**.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-116">Under Lync Server 2013, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    
    <span data-ttu-id="bcdf4-117">![Écran structure des fichiers du générateur de topologie Lync Server](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Écran structure des fichiers du générateur de topologie Lync Server")</span><span class="sxs-lookup"><span data-stu-id="bcdf4-117">![Lync Server Topology Builder file structure screen](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server Topology Builder file structure screen")</span></span>

3.  <span data-ttu-id="bcdf4-118">Dans **define New jonction**, spécifiez un nom convivial pour identifier le tronçon de manière unique.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-118">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="bcdf4-119">Vous ne pouvez pas avoir deux jonctions de même nom.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-119">You cannot have two trunks with the same name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bcdf4-120">Si vous spécifiez le protocole TLS (Transport Layer Security) comme type de transport, vous devez spécifier le nom de domaine complet au lieu de l’adresse IP de l’homologue du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-120">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="bcdf4-121">Sous **passerelle RTC associée**, sélectionnez l’homologue de passerelle PSTN à associer à cette jonction.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-121">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    
    <span data-ttu-id="bcdf4-122">![Paramètres de propriété pour l’homologue de passerelle PSTN pour jonction](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Paramètres de propriété pour l’homologue de passerelle PSTN pour jonction")</span><span class="sxs-lookup"><span data-stu-id="bcdf4-122">![Property settings for PSTN gateway peer for trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Property settings for PSTN gateway peer for trunk")</span></span>

5.  <span data-ttu-id="bcdf4-123">Sous **port d’écoute pour la passerelle PSTN**, tapez le port d’écoute que l’homologue (passerelle PSTN, IP-PBX ou SBC) reçoit les messages SIP du serveur de médiation qui doit être associé à cette jonction.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-123">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="bcdf4-124">Les ports d’homologue par défaut sont 5066 pour le protocole TCP (Transmission Control Protocol) et 5067 pour le protocole TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="bcdf4-124">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="bcdf4-125">Les ports Survivable Branch Appliance par défaut sont 5081 pour TCP et 5082 pour TLS.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-125">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>

6.  <span data-ttu-id="bcdf4-126">Sous **protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-126">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bcdf4-127">Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation pouvant utiliser le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

7.  <span data-ttu-id="bcdf4-128">Sous **serveur de médiation associé**, sélectionnez le pool de serveurs de médiation à associer à la jonction racine de cet homologue.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>

8.  <span data-ttu-id="bcdf4-129">Sous **port du serveur de médiation associé**, tapez le port d’écoute que le serveur de médiation recevra les messages SIP de l’homologue.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bcdf4-130">Avec la prise en charge de plusieurs tronçons dans Lync Server 2013, deux jonctions avec différents noms de jonctions ne peuvent pas être configurées avec le même <STRONG>port de serveur de médiation</STRONG> et le même <STRONG>port d’écoute pour la passerelle IP/PSTN</STRONG></span><span class="sxs-lookup"><span data-stu-id="bcdf4-130">With multiple trunk support in Lync Server 2013, two trunks with different trunk names cannot be configured with the same <STRONG>Associated Mediation Server port</STRONG> and <STRONG>Listening Port for IP/PSTN gateway</STRONG></span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bcdf4-131">Avec la prise en charge de plusieurs tronçons dans Lync Server 2013, plusieurs ports de signalisation SIP peuvent être définis sur le serveur de médiation pour la communication avec plusieurs homologues.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="bcdf4-132">Lors de la définition d’une jonction, le numéro de <STRONG>port du serveur de médiation associé</STRONG> doit être compris dans la plage des ports d’écoute pour le protocole respectif autorisé par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="bcdf4-133">Cette plage de ports est définie sous Lync Server 2013 et pools de serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-133">This port range is defined under Lync Server 2013 and Mediation Server pools.</span></span> <span data-ttu-id="bcdf4-134">Cliquez avec le bouton droit sur le pool de serveurs de médiation approprié, puis sélectionnez <STRONG>modifier les propriétés</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-134">Right-click the relevant Mediation Server pool, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="bcdf4-135">Spécifiez la plage de ports dans le champ <STRONG>Ports d’écoute</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

9.  <span data-ttu-id="bcdf4-136">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcdf4-136">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bcdf4-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bcdf4-137">See Also</span></span>


[<span data-ttu-id="bcdf4-138">Modifier une jonction dans le générateur de topologies dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcdf4-138">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

