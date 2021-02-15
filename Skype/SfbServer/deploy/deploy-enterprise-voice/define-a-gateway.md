---
title: Définir une passerelle dans le Générateur de topologies dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Résumé : Découvrez comment définir une passerelle PSTN dans le Générateur de topologie dans Skype Entreprise Server.'
ms.openlocfilehash: be68c853cdcd530b05ad4b0949f722788e77d0df
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837024"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="a6bb6-103">Définir une passerelle dans le Générateur de topologies dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a6bb6-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="a6bb6-104">**Résumé :** Découvrez comment définir une passerelle PSTN dans le Générateur de topologies dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="a6bb6-105">Suivez ces étapes pour utiliser le Générateur de topologie afin de définir un homologue avec lequel vous pouvez associer un serveur de médiation afin de fournir une connectivité au réseau téléphonique commuté (PSTN) pour les utilisateurs activés pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="a6bb6-106">Un homologue au serveur de médiation peut être une passerelle PSTN, un SYSTÈME IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet (ITSP) auquel vous vous connectez en configurant une connexion SIP.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="a6bb6-107">Pour définir un homologue pour le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="a6bb6-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="a6bb6-108">Démarrez le Générateur de topologie : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **Server 2015,** puis sur Générateur skype entreprise **Server 2015Topology.**</span><span class="sxs-lookup"><span data-stu-id="a6bb6-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="a6bb6-109">Sous Skype Entreprise Server, nom de votre site, Composants partagés, cliquez avec le bouton droit sur le nœud **Passerelles PSTN,** puis cliquez sur Nouvelle passerelle **PSTN.**</span><span class="sxs-lookup"><span data-stu-id="a6bb6-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="a6bb6-110">Dans **Définir une nouvelle passerelle IP/PSTN**, tapez le nom de domaine complet ou l’adresse IP de l’homologue, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a6bb6-111">Si vous spécifiez le type de transport TLS (Transport Layer Security), vous devez spécifier le nom de groupe au lieu de l’adresse IP de l’homologue du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="a6bb6-112">Définissez le mode d’écoute (IPv4 ou IPv6) de l’adresse IP de votre nouvelle passerelle PSTN, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="a6bb6-113">Définissez une jonction racine pour la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="a6bb6-114">Une connexion est une connexion logique entre un serveur de médiation et une passerelle identifiée de manière unique par le tuple.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="a6bb6-115">{FQDN du serveur de médiation, port d’écoute du serveur de médiation (TLS ou TCP) : IP et FQDN de passerelle, port d’écoute de passerelle}</span><span class="sxs-lookup"><span data-stu-id="a6bb6-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="a6bb6-116">Lorsque vous définissez une passerelle PSTN dans le Générateur de topologie, vous devez définir une trunk racine pour ajouter correctement la passerelle PSTN à votre topologie.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="a6bb6-117">Vous ne pouvez pas supprimer la jonction racine tant que la passerelle PSTN associée n’est pas supprimée.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="a6bb6-118">Sous Port d’écoute pour la passerelle **IP/PSTN,** tapez le port d’écoute que la passerelle, le PBX ou le SBC utilisera pour les messages SIP du serveur de médiation qui seront associés à la branche racine de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="a6bb6-119">(Par défaut, les ports sont 5066 pour TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security) sur une passerelle PSTN, un autocommutateur privé (PBX) ou un contrôleur SBC.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="a6bb6-120">Sur un Survivable Branch Appliance sur un site de succursale, les ports par défaut sont 5081 pour TCP et 5082 pour TLS.)</span><span class="sxs-lookup"><span data-stu-id="a6bb6-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="a6bb6-121">Sous **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a6bb6-122">Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation qui peut utiliser TLS.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="a6bb6-123">Sous **Serveur de médiation associé,** sélectionnez le pool de serveurs de médiation à associer à la branche racine de cette passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="a6bb6-124">Sous **le port du serveur de** médiation associé, tapez le port d’écoute que le serveur de médiation utilisera pour les messages SIP de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a6bb6-125">Avec la prise en charge de plusieurs branches dans Skype Entreprise Server, vous pouvez définir plusieurs ports de signalisation SIP sur le serveur de médiation pour la communication avec plusieurs passerelles PSTN.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="a6bb6-126">Lors de la définition d’une trunk, le **port** du serveur de médiation associé doit se trouver dans la plage des ports d’écoute pour le protocole respectif autorisé par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="a6bb6-127">Cette plage de ports est définie sous Skype Entreprise Server et les pools de médiation.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="a6bb6-128">Cliquez avec le bouton droit sur le pool de serveurs de médiation qui vous intéresse, puis sélectionnez **Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="a6bb6-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="a6bb6-129">Spécifiez la plage de ports dans le champ **Ports d’écoute**.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="a6bb6-130">Assurez-vous que l’homologue que vous avez défini est en cours d’exécution et qu’il utilise le FQDN ou l’adresse IP que vous avez spécifié.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="a6bb6-131">Cliquez ensuite sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="a6bb6-132">Cliquez avec le bouton droit sur le nœud **Skype Entreprise Server,** puis cliquez sur **Publier la topologie.**</span><span class="sxs-lookup"><span data-stu-id="a6bb6-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

