---
title: Définition de lignes supplémentaires dans le générateur de topologies de Skype entreprise Server
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Résumé: Découvrez comment définir un Trunk supplémentaire entre un serveur de médiation et un homologue de passerelle dans le générateur de topologies de Skype entreprise Server.'
ms.openlocfilehash: de6cfd45c9e5f8440fcbcf6b6098a82edda752f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303311"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="12083-103">Définition de lignes supplémentaires dans le générateur de topologies de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="12083-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="12083-104">**Résumé:** Découvrez comment définir un Trunk supplémentaire entre un serveur de médiation et un homologue de passerelle dans le générateur de topologies de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="12083-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="12083-105">Procédez comme suit pour définir un Trunk supplémentaire auquel vous pouvez associer un homologue à un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="12083-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="12083-106">Un homologue fournit aux utilisateurs une connectivité voix entreprise compatible avec le réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="12083-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="12083-107">L’homologue peut être une passerelle RTC, un système IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur ITSP (Internet Telephony Service Provider).</span><span class="sxs-lookup"><span data-stu-id="12083-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="12083-108">Un Trunk est une connexion logique entre un serveur de médiation et une passerelle.</span><span class="sxs-lookup"><span data-stu-id="12083-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="12083-109">Dans cette rubrique, nous partons du principe que vous avez configuré une passerelle RTC et une Trunk racine avec au moins un serveur ou un pool de médiation autonome ou autonome comme décrit dans la rubrique [définir une passerelle dans le générateur de topologie de Skype entreprise Server](define-a-gateway.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="12083-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="12083-110">Pour définir un Trunk supplémentaire entre un serveur de médiation et un homologue de passerelle</span><span class="sxs-lookup"><span data-stu-id="12083-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="12083-111">Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **Skype entreprise Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="12083-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="12083-112">Sous Skype entreprise Server, le nom de votre site, les **composants partagés**, cliquez avec \*\*\*\* le bouton droit sur le nœud Trunks, puis cliquez sur **nouveau Trunk**.</span><span class="sxs-lookup"><span data-stu-id="12083-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="12083-113">Dans **Définir un nouveau tronçon**, spécifiez un nom convivial pour identifier le tronçon de manière unique.</span><span class="sxs-lookup"><span data-stu-id="12083-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="12083-114">Deux tronçons ne peuvent pas porter le même nom.</span><span class="sxs-lookup"><span data-stu-id="12083-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="12083-115">Si vous spécifiez TLS (Transport Layer Security) comme type de transport, vous devez spécifier le nom de domaine complet (FQDN) au lieu de l’adresse IP de l’homologue du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="12083-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="12083-116">Sous **Passerelle RTC associée**, sélectionnez l’homologue de passerelle RTC à associer à ce tronçon.</span><span class="sxs-lookup"><span data-stu-id="12083-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="12083-117">Sous **port d’écoute pour la passerelle RTC**, tapez le port d’écoute que le pair (passerelle PSTN, IP-PBX ou SBC) reçoit les messages SIP du serveur de médiation qui sera associé à ce Trunk.</span><span class="sxs-lookup"><span data-stu-id="12083-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="12083-118">Les ports homologues par défaut sont 5066 pour TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="12083-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="12083-119">Les ports de l’appareil de branchement Survivable par défaut sont 5081 pour TCP et 5082 pour TLS.</span><span class="sxs-lookup"><span data-stu-id="12083-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="12083-120">Dans **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue.</span><span class="sxs-lookup"><span data-stu-id="12083-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="12083-121">Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation qui peut utiliser le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="12083-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="12083-122">Sous **serveur de médiation associé**, sélectionnez le pool de serveurs de médiation à associer au Trunk racine de cet homologue.</span><span class="sxs-lookup"><span data-stu-id="12083-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="12083-123">Sous **port du serveur de médiation associé**, tapez le port d’écoute sur lequel le serveur de médiation va recevoir des messages SIP de l’homologue.</span><span class="sxs-lookup"><span data-stu-id="12083-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="12083-124">Grâce à la prise en charge de Trunks multiples dans Skype entreprise Server, il est impossible de configurer deux Trunks avec différents noms de Trunk avec les mêmes **port de serveur de médiation** et **port d’écoute pour une passerelle IP/RTC**</span><span class="sxs-lookup"><span data-stu-id="12083-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="12083-125">La prise en charge de plusieurs Trunks dans Skype entreprise Server vous permet de définir plusieurs ports de signalisation SIP sur le serveur de médiation pour la communication avec des pairs multiples.</span><span class="sxs-lookup"><span data-stu-id="12083-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="12083-126">Lors de la définition d’un Trunk, le numéro de **port du serveur de médiation associé** doit figurer dans la plage des ports d’écoute pour le protocole correspondant autorisé par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="12083-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="12083-127">Cette plage de ports est définie sous Skype entreprise Server et pools de serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="12083-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="12083-128">Cliquez avec le bouton droit sur la liste de serveurs de médiation appropriée, puis sélectionnez **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="12083-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="12083-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="12083-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="12083-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="12083-130">Click **OK**.</span></span> 
    

