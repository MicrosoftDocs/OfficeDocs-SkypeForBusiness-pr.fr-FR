---
title: Définition d’autres jonctions dans le générateur de topologie dans Skype Entreprise Server 2015
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Résumé : Découvrez comment définir un trunk supplémentaire entre un serveur de médiation et un homologue de passerelle dans le Générateur de topologie dans Skype pour Business Server 2015.'
ms.openlocfilehash: 67d378a794ed6a80b5721f9eb2e9e988ee4db048
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server-2015"></a><span data-ttu-id="5e740-103">Définition d’autres jonctions dans le générateur de topologie dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5e740-103">Define additional trunks in Topology Builder in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5e740-104">**Résumé :** Découvrez comment définir un trunk supplémentaire entre un serveur de médiation et un homologue de passerelle dans le Générateur de topologie dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5e740-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5e740-105">Suivez ces étapes pour définir un trunk supplémentaire auxquels vous pouvez associer un homologue avec un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="5e740-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="5e740-106">Un homologue fournit aux utilisateurs activés pour la Voix Entreprise grâce à la connectivité pour la commutation de téléphone RTPC (réseau Public).</span><span class="sxs-lookup"><span data-stu-id="5e740-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="5e740-107">L’homologue peut être une passerelle RTC, un système IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur ITSP (Internet Telephony Service Provider).</span><span class="sxs-lookup"><span data-stu-id="5e740-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="5e740-108">Une ligne est une connexion logique entre un serveur de médiation et la passerelle.</span><span class="sxs-lookup"><span data-stu-id="5e740-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5e740-109">Cette rubrique suppose que si vous avez le programme d’installation une passerelle PSTN et le tronc racine au moins un colocalisé autonome médiation serveur ou pool comme décrit dans [définition de passerelle dans le Générateur de topologie dans Skype pour Business Server 2015](define-a-gateway.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="5e740-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server 2015](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="5e740-110">Pour définir un trunk supplémentaire entre un serveur de médiation et un homologue de passerelle</span><span class="sxs-lookup"><span data-stu-id="5e740-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="5e740-111">Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="5e740-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="5e740-112">Sous Skype pour Business Server, le nom de votre site, les **Composants partagés**, cliquez sur le nœud de **puits** et puis cliquez sur **Nouveau Trunk**.</span><span class="sxs-lookup"><span data-stu-id="5e740-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    3. <span data-ttu-id="5e740-p102">Dans **Définir un nouveau tronçon**, spécifiez un nom convivial pour identifier le tronçon de manière unique. Deux tronçons ne peuvent pas porter le même nom.</span><span class="sxs-lookup"><span data-stu-id="5e740-p102">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk. You cannot have two trunks with the same name.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5e740-115">Si vous spécifiez la sécurité TLS (Transport Layer) comme type de transport, vous devez spécifier le nom de domaine complet au lieu de l’adresse IP de l’hôte du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="5e740-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="5e740-116">Sous **Passerelle RTC associée**, sélectionnez l’homologue de passerelle RTC à associer à ce tronçon.</span><span class="sxs-lookup"><span data-stu-id="5e740-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="5e740-117">Sous **Ports d’écoute pour passerelle PSTN**, tapez le port d’écoute que l’homologue (passerelle RTPC, IP-PBX ou SBC) recevra les messages SIP à partir du serveur de médiation qui doit être associée à cette ligne.</span><span class="sxs-lookup"><span data-stu-id="5e740-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="5e740-118">Les ports homologues par défaut sont 5066 pour TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="5e740-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="5e740-119">Les ports de Survivable Branch Appliance par défaut sont 5081 pour TCP et 5082 pour TLS.</span><span class="sxs-lookup"><span data-stu-id="5e740-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
6. <span data-ttu-id="5e740-120">Dans **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue.</span><span class="sxs-lookup"><span data-stu-id="5e740-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5e740-121">Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation qui peuvent utiliser TLS.</span><span class="sxs-lookup"><span data-stu-id="5e740-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
7. <span data-ttu-id="5e740-122">Sous **Serveur de médiation associé**, sélectionnez le pool de serveur de médiation à associer le tronc racine de cet homologue</span><span class="sxs-lookup"><span data-stu-id="5e740-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
8. <span data-ttu-id="5e740-123">Sous **port de serveur de médiation associée**, tapez le port d’écoute que le serveur de médiation recevoir des messages SIP de l’homologue.</span><span class="sxs-lookup"><span data-stu-id="5e740-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5e740-124">Plusieurs trunk prend en charge Skype pour Business Server, deux trunks avec des noms différents trunk ne peut pas être configurés avec le même **port de serveur de médiation associé** et le **Port d’écoute pour la passerelle IP/RTPC**</span><span class="sxs-lookup"><span data-stu-id="5e740-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="5e740-125">Plusieurs trunk prend en charge Skype pour Business Server, SIP plusieurs voies de signalisation peut être défini sur le serveur de médiation pour la communication avec plusieurs homologues.</span><span class="sxs-lookup"><span data-stu-id="5e740-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="5e740-126">Lorsque vous définissez un tronc, le numéro de **port du serveur de médiation associé** doit être comprise entre les ports d’écoute pour le protocole respectif autorisée par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="5e740-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="5e740-127">Cette plage de ports est définie sous Skype pour les pools Business Server et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="5e740-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="5e740-128">Droit sur le pool de serveur de médiation approprié et sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5e740-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="5e740-129">Spécifiez la plage de ports dans le champ **Ports d’écoute**.</span><span class="sxs-lookup"><span data-stu-id="5e740-129">Specify the port range in the **Listening ports** field.</span></span>
  
9. <span data-ttu-id="5e740-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e740-130">Click **OK**.</span></span> 
    

