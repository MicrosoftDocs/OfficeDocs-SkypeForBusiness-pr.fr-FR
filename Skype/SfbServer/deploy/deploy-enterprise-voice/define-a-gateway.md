---
title: Définir une passerelle dans le Générateur de topologie dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Résumé : Découvrez comment définir une passerelle PSTN dans le Générateur de topologie dans Skype pour Business Server.'
ms.openlocfilehash: c83951c26a125c568535bfba7d487324a9b725d0
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20998552"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="0cb9b-103">Définir une passerelle dans le Générateur de topologie dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="0cb9b-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="0cb9b-104">**Résumé :** Découvrez comment définir une passerelle PSTN dans le Générateur de topologie dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="0cb9b-105">Procédez comme suit pour utiliser le Générateur de topologie pour définir un homologue avec lequel vous pouvez associer un serveur de médiation pour fournir une connectivité au réseau téléphonique commuté (RTC) pour les utilisateurs activés pour Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="0cb9b-106">Un homologue pour le serveur de médiation peut être une passerelle PSTN, un IP-PBX ou un contrôleur de frontière Session (SBC) pour un Internet téléphonie Service fournisseur (ITSP) à laquelle vous vous connectez en configurant une jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="0cb9b-107">Pour définir un homologue pour le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="0cb9b-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="0cb9b-108">Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour le Générateur de 2015Topology Business Server**.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="0cb9b-109">Sous Skype pour Business Server, le nom de votre site, composants partagés, cliquez sur le nœud **Passerelles PSTN** , puis cliquez sur **Nouvelle passerelle PSTN**.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="0cb9b-110">Dans **Définir une nouvelle passerelle IP/RTC**, tapez le nom de domaine complet ou l’adresse IP de l’homologue, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0cb9b-111">Si vous spécifiez Transport Layer Security (TLS) comme type de transport, vous devez spécifier le nom de domaine complet au lieu de l’adresse IP de l’homologue du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="0cb9b-112">Définissez le mode d’écoute (IPv4 ou IPv6) de l’adresse IP de votre nouvelle passerelle RTC, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="0cb9b-113">Définissez une jonction racine pour la passerelle RTC.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="0cb9b-114">Une jonction est une connexion logique entre un serveur de médiation et une passerelle identifiée de manière unique par le tuple.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="0cb9b-115">{FQDN du serveur de médiation, port d’écoute de serveur de médiation (TLS ou TCP) : IP de la passerelle et le nom de domaine complet, port d’écoute de passerelle}</span><span class="sxs-lookup"><span data-stu-id="0cb9b-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="0cb9b-116">Lorsque vous définissez une passerelle PSTN dans le Générateur de topologie, vous devez définir une jonction racine pour ajouter correctement la passerelle PSTN à votre topologie.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="0cb9b-117">Vous ne pouvez pas supprimer la jonction racine tant que la passerelle RTC associée n’est pas supprimée.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="0cb9b-118">Sous **Port d’écoute pour passerelle IP/PSTN**, tapez le port d’écoute que la passerelle, PBX ou SBC utilisera pour les messages SIP à partir du serveur de médiation qui seront associés à la jonction racine de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="0cb9b-119">(Par défaut, les ports sont 5066 pour TCP [Transmission Control Protocol] et 5067 pour TLS [Transport Layer Security] sur une passerelle RTC, un autocommutateur privé [PBX] ou un contrôleur SBC.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="0cb9b-120">Sur un serveur Survivable Branch Appliance sur un site de succursale, les ports par défaut sont 5081 pour TCP et 5082 pour TLS.)</span><span class="sxs-lookup"><span data-stu-id="0cb9b-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="0cb9b-121">Sous **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0cb9b-122">Pour des raisons de sécurité, il est vivement recommandé de déployer un homologue pour le serveur de médiation pouvant utiliser TLS.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="0cb9b-123">Sous **Serveur de médiation associé**, sélectionnez le pool de serveur de médiation à associer à la jonction racine de cette passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="0cb9b-124">Sous **port du serveur de médiation associé**, tapez le port d’écoute du serveur de médiation utilisera pour les messages SIP provenant de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0cb9b-125">Plusieurs jonction prend en charge Skype pour Business Server, vous pouvez définir plusieurs SIP signalisation ports sur le serveur de médiation pour la communication avec plusieurs passerelles PSTN.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="0cb9b-126">Lorsque vous définissez une jonction, le **port du serveur de médiation associé** doit être dans la plage des ports d’écoute pour le protocole respectif autorisé par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="0cb9b-127">Cette plage de ports est définie sous Skype pour Business Server et les Pools de médiation.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="0cb9b-128">Cliquez sur le pool de serveur de médiation d’intérêt et sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="0cb9b-129">Spécifiez la plage de ports dans le champ **Ports d’écoute**.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="0cb9b-p105">Assurez-vous que l’homologue que vous avez défini est en cours d’exécution et qu’il utilise le nom de domaine complet ou l’adresse IP spécifié, puis cliquez sur **Terminer**</span><span class="sxs-lookup"><span data-stu-id="0cb9b-p105">Be sure that the peer you defined is running and using the FQDN or IP address that you specified. Then click **Finish**.</span></span>
    
11. <span data-ttu-id="0cb9b-132">Cliquez avec le bouton droit sur le nœud **Skype Entreprise Server**, puis cliquez sur **Publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="0cb9b-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

