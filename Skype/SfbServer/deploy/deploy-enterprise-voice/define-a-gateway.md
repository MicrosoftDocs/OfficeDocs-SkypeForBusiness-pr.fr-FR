---
title: Définition d’une passerelle dans le générateur de topologie dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Résumé : Apprenez à définir une passerelle PSTN dans le Générateur de topologie dans Skype pour Business Server 2015.'
ms.openlocfilehash: 7fa7f95fd04cf491dad32b0ab6cc050c5ebb0b0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server-2015"></a><span data-ttu-id="275a2-103">Définition d’une passerelle dans le générateur de topologie dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="275a2-103">Define a gateway in Topology Builder in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="275a2-104">**Résumé :** Découvrez comment définir une passerelle PSTN dans le Générateur de topologie dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="275a2-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="275a2-105">Procédez comme suit pour utiliser le Générateur de topologies pour définir un homologue avec lequel vous pouvez associer un serveur de médiation pour assurer la connectivité au réseau téléphonique public commuté (RTPC) pour les utilisateurs activés pour la Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="275a2-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="275a2-106">Un homologue sur le serveur de médiation peut être une passerelle PSTN, un IP-PBX ou un contrôleur de Session bordure (SBC) pour un Internet téléphonie Service fournisseur (ITSP) auquel vous vous connectez en configurant un SIP trunk.</span><span class="sxs-lookup"><span data-stu-id="275a2-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="275a2-107">Pour définir un homologue pour le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="275a2-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="275a2-108">Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="275a2-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="275a2-109">Sous Skype pour Business Server, le nom de votre site, les composants partagés, cliquez sur le nœud de **Passerelles RTPC** , puis cliquez sur **Nouvelle passerelle RTPC**.</span><span class="sxs-lookup"><span data-stu-id="275a2-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="275a2-110">Dans **Définir une nouvelle passerelle IP/RTC**, tapez le nom de domaine complet ou l’adresse IP de l’homologue, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="275a2-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="275a2-111">Si vous spécifiez la sécurité TLS (Transport Layer) comme type de transport, vous devez spécifier le nom de domaine complet au lieu de l’adresse IP de l’hôte du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="275a2-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="275a2-112">Définissez le mode d’écoute (IPv4 ou IPv6) de l’adresse IP de votre nouvelle passerelle RTC, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="275a2-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="275a2-113">Définir un tronc racine de la passerelle RTPC.</span><span class="sxs-lookup"><span data-stu-id="275a2-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="275a2-114">Une ligne est une connexion logique entre un serveur de médiation et la passerelle identifié de manière unique par le tuple.</span><span class="sxs-lookup"><span data-stu-id="275a2-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="275a2-115">{FQDN de serveur de médiation, port d’écoute de serveur de médiation (TLS ou TCP) : passerelle IP et nom de domaine complet, port d’écoute passerelle}</span><span class="sxs-lookup"><span data-stu-id="275a2-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="275a2-116">Lorsque vous définissez une passerelle PSTN dans le Générateur de topologie, vous devez définir un tronc racine pour ajouter correctement de la passerelle PSTN de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="275a2-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="275a2-117">Vous ne pouvez pas supprimer la jonction racine tant que la passerelle RTC associée n’est pas supprimée.</span><span class="sxs-lookup"><span data-stu-id="275a2-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="275a2-118">Sous **Ports d’écoute pour la passerelle IP/RTPC**, tapez le port d’écoute par la passerelle, un PBX ou un SBC pour messages SIP à partir du serveur de médiation sera associé le tronc racine de la passerelle RTPC.</span><span class="sxs-lookup"><span data-stu-id="275a2-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="275a2-119">(Par défaut, les ports sont 5066 pour TCP [Transmission Control Protocol] et 5067 pour TLS [Transport Layer Security] sur une passerelle RTC, un autocommutateur privé [PBX] ou un contrôleur SBC.</span><span class="sxs-lookup"><span data-stu-id="275a2-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="275a2-120">Survivable Branch Appliance à un site de la succursale, les ports par défaut sont 5081 pour TCP et 5082 pour TLS.)</span><span class="sxs-lookup"><span data-stu-id="275a2-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="275a2-121">Sous **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="275a2-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="275a2-122">Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation qui peuvent utiliser TLS.</span><span class="sxs-lookup"><span data-stu-id="275a2-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="275a2-123">Sous **Serveur de médiation associé**, sélectionnez le pool de serveur de médiation à associer le tronc racine de cette passerelle RTPC.</span><span class="sxs-lookup"><span data-stu-id="275a2-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="275a2-124">Sous **port de serveur de médiation associée**, tapez le port d’écoute utilisé par le serveur de médiation pour messages SIP de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="275a2-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="275a2-125">Plusieurs trunk prend en charge Skype pour Business Server, vous pouvez définir plusieurs SIP signalisation des ports sur le serveur de médiation pour la communication avec plusieurs passerelles RTPC.</span><span class="sxs-lookup"><span data-stu-id="275a2-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="275a2-126">Lorsque vous définissez un tronc, le **port du serveur de médiation associé** doit être comprise entre les ports d’écoute pour le protocole respectif autorisée par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="275a2-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="275a2-127">Cette plage de ports est définie sous Skype pour Business Server et les Pools de médiation.</span><span class="sxs-lookup"><span data-stu-id="275a2-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="275a2-128">Cliquez sur le pool de serveur de médiation d’intérêt et sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="275a2-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="275a2-129">Spécifiez la plage de ports dans le champ **Ports d’écoute**.</span><span class="sxs-lookup"><span data-stu-id="275a2-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="275a2-p105">Assurez-vous que l’homologue que vous avez défini est en cours d’exécution et qu’il utilise le nom de domaine complet ou l’adresse IP spécifié, puis cliquez sur **Terminer**</span><span class="sxs-lookup"><span data-stu-id="275a2-p105">Be sure that the peer you defined is running and using the FQDN or IP address that you specified. Then click **Finish**.</span></span>
    
11. <span data-ttu-id="275a2-132">Cliquez avec le bouton droit sur le nœud **Skype Entreprise Server**, puis cliquez sur **Publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="275a2-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

