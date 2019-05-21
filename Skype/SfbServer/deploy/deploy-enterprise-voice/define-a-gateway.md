---
title: Définir une passerelle dans le générateur de topologies dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Résumé: Découvrez comment définir une passerelle RTC dans le générateur de topologie dans Skype entreprise Server.'
ms.openlocfilehash: 39e2bdf041055e392b88cc25594b45c2529161d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286168"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="1fc3f-103">Définir une passerelle dans le générateur de topologies dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1fc3f-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="1fc3f-104">**Résumé:** Découvrez comment définir une passerelle RTC dans le générateur de topologie de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="1fc3f-105">Suivez les étapes ci-dessous pour définir un homologue qui vous permet d’associer un serveur de médiation afin de fournir une connectivité au réseau téléphonique commuté (PSTN) pour les utilisateurs autorisés à utiliser voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="1fc3f-106">Un hôte du serveur de médiation peut être une passerelle RTC, un PBX IP ou un contrôleur de bordure de session (SBC) pour un fournisseur de services de téléphonie Internet (ITSP) auquel vous vous connectez en configurant un Trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="1fc3f-107">Pour définir un homologue pour le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="1fc3f-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="1fc3f-108">Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **Skype entreprise Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="1fc3f-109">Sous Skype entreprise Server, nom de votre site, composants partagés, cliquez avec le bouton droit sur le nœud **passerelles RTC** , puis cliquez sur **nouvelle passerelle PSTN**.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="1fc3f-110">Dans **Définir une nouvelle passerelle IP/RTC**, tapez le nom de domaine complet ou l’adresse IP de l’homologue, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1fc3f-111">Si vous spécifiez TLS (Transport Layer Security) comme type de transport, vous devez spécifier le nom de domaine complet (FQDN) au lieu de l’adresse IP de l’homologue du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="1fc3f-112">Définissez le mode d’écoute (IPv4 ou IPv6) de l’adresse IP de votre nouvelle passerelle RTC, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="1fc3f-113">Définissez une jonction racine pour la passerelle RTC.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="1fc3f-114">Un Trunk est une connexion logique entre un serveur de médiation et une passerelle identifiée de manière unique par le tuple.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="1fc3f-115">Le nom de domaine complet du serveur de médiation, port d’écoute du serveur de médiation (TLS ou TCP): adresse IP et nom de domaine complet de la passerelle</span><span class="sxs-lookup"><span data-stu-id="1fc3f-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="1fc3f-116">Lors de la définition d’une passerelle RTC dans le générateur de topologie, vous devez définir une Trunk racine pour ajouter correctement la passerelle RTC à votre topologie.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="1fc3f-117">Vous ne pouvez pas supprimer la jonction racine tant que la passerelle RTC associée n’est pas supprimée.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="1fc3f-118">Sous **port d’écoute pour la passerelle RTC/IP**, tapez le port d’écoute que la passerelle, le PBX ou la SBC utilisera pour les messages SIP du serveur de médiation qui sera associé au Trunk racine de la passerelle RTC.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="1fc3f-119">(Par défaut, les ports sont 5066 pour TCP [Transmission Control Protocol] et 5067 pour TLS [Transport Layer Security] sur une passerelle RTC, un autocommutateur privé [PBX] ou un contrôleur SBC.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="1fc3f-120">Sur une unité de branchement Survivable sur une succursale, les ports par défaut sont 5081 pour TCP et 5082 pour TLS.)</span><span class="sxs-lookup"><span data-stu-id="1fc3f-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="1fc3f-121">Sous **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1fc3f-122">Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation qui peut utiliser le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="1fc3f-123">Sous **serveur de médiation associé**, sélectionnez le pool de serveurs de médiation à associer au Trunk racine de cette passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="1fc3f-124">Sous **port du serveur de médiation associé**, tapez le port d’écoute que le serveur de médiation utilisera pour les messages SIP de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1fc3f-125">La prise en charge de plusieurs Trunks dans Skype entreprise Server vous permet de définir plusieurs ports de signalisation SIP sur le serveur de médiation pour la communication avec plusieurs passerelles RTC.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="1fc3f-126">Lors de la définition d’un Trunk, le **port du serveur de médiation associé** doit figurer dans la plage des ports d’écoute pour le protocole correspondant autorisé par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="1fc3f-127">Cette plage de ports est définie sous Skype entreprise Server et les pools de médiation.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="1fc3f-128">Cliquez avec le bouton droit sur le pool de serveurs de médiation qui vous intéresse, puis sélectionnez **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="1fc3f-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="1fc3f-130">Assurez-vous que l’homologue que vous avez défini s’exécute et utilise le nom de domaine complet ou l’adresse IP que vous avez spécifiée.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="1fc3f-131">Cliquez ensuite sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="1fc3f-132">Cliquez avec le bouton droit sur le nœud du **serveur Skype entreprise** , puis cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

