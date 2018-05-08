---
title: Définition d’autres jonctions dans le générateur de topologie dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Résumé : Découvrez comment définir un tronçon supplémentaire entre un serveur de médiation et un homologue de passerelle dans le Générateur de topologie dans Skype pour Business Server 2015.'
ms.openlocfilehash: e76555d0f03b884ad3f3c91c5ca4ad5d687711a2
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server-2015"></a><span data-ttu-id="11e8a-103">Définition d’autres jonctions dans le générateur de topologie dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="11e8a-103">Define additional trunks in Topology Builder in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="11e8a-104">**Résumé :** Découvrez comment définir un tronçon supplémentaire entre un serveur de médiation et un homologue de passerelle dans le Générateur de topologie dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="11e8a-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="11e8a-105">Suivez ces étapes pour définir un tronçon supplémentaire auquel vous pouvez associer un homologue à un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="11e8a-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="11e8a-106">Un homologue fournit aux utilisateurs activés pour Enterprise Voice avec une connectivité pour les publics téléphone réseau commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="11e8a-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="11e8a-107">L’homologue peut être une passerelle RTC, un système IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur ITSP (Internet Telephony Service Provider).</span><span class="sxs-lookup"><span data-stu-id="11e8a-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="11e8a-108">Une jonction est une connexion logique entre un serveur de médiation et une passerelle.</span><span class="sxs-lookup"><span data-stu-id="11e8a-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="11e8a-109">Cette rubrique suppose que vous disposez du programme d’installation une passerelle PSTN et jonction racine au moins un colocalisé ou autonome serveur de médiation ou pool comme décrit dans [définir une passerelle dans le Générateur de topologie dans Skype pour Business Server 2015](define-a-gateway.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="11e8a-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server 2015](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="11e8a-110">Pour définir un tronçon supplémentaire entre un serveur de médiation et un homologue de passerelle</span><span class="sxs-lookup"><span data-stu-id="11e8a-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="11e8a-111">Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour le Générateur de 2015Topology Business Server**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="11e8a-112">Sous Skype pour Business Server, le nom de votre site, **Composants partagés**, cliquez sur le nœud **tronçons** , puis cliquez sur **Nouvelle jonction**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    3. <span data-ttu-id="11e8a-p102">Dans **Définir un nouveau tronçon**, spécifiez un nom convivial pour identifier le tronçon de manière unique. Deux tronçons ne peuvent pas porter le même nom.</span><span class="sxs-lookup"><span data-stu-id="11e8a-p102">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk. You cannot have two trunks with the same name.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="11e8a-115">Si vous spécifiez Transport Layer Security (TLS) comme type de transport, vous devez spécifier le nom de domaine complet au lieu de l’adresse IP de l’homologue du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="11e8a-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="11e8a-116">Sous **Passerelle RTC associée**, sélectionnez l’homologue de passerelle RTC à associer à ce tronçon.</span><span class="sxs-lookup"><span data-stu-id="11e8a-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="11e8a-117">Sous **Port d’écoute pour passerelle PSTN**, tapez le port d’écoute que l’homologue (passerelle PSTN, IP-PBX ou SBC) recevoir des messages SIP à partir du serveur de médiation doit être associé à ce tronçon.</span><span class="sxs-lookup"><span data-stu-id="11e8a-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="11e8a-118">Les ports homologues par défaut sont 5066 pour TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="11e8a-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="11e8a-119">Les ports de Survivable Branch Appliance par défaut sont 5081 pour TCP et 5082 pour TLS.</span><span class="sxs-lookup"><span data-stu-id="11e8a-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
6. <span data-ttu-id="11e8a-120">Dans **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue.</span><span class="sxs-lookup"><span data-stu-id="11e8a-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="11e8a-121">Pour des raisons de sécurité, il est vivement recommandé de déployer un homologue pour le serveur de médiation pouvant utiliser TLS.</span><span class="sxs-lookup"><span data-stu-id="11e8a-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
7. <span data-ttu-id="11e8a-122">Sous **Serveur de médiation associé**, sélectionnez le pool de serveur de médiation à associer à la jonction racine de cet homologue</span><span class="sxs-lookup"><span data-stu-id="11e8a-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
8. <span data-ttu-id="11e8a-123">Sous **port du serveur de médiation associé**, tapez le port d’écoute que le serveur de médiation recevoir des messages SIP de l’homologue.</span><span class="sxs-lookup"><span data-stu-id="11e8a-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="11e8a-124">Plusieurs jonction prend en charge Skype pour Business Server, deux tronçons ayant des noms différents ne peuvent pas être configurés avec le même **port du serveur de médiation associé** et le **Port d’écoute pour passerelle IP/RTC**</span><span class="sxs-lookup"><span data-stu-id="11e8a-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="11e8a-125">Plusieurs jonction prend en charge Skype pour Business Server, SIP plusieurs voies de signalisation peut être définie sur le serveur de médiation pour la communication avec plusieurs homologues.</span><span class="sxs-lookup"><span data-stu-id="11e8a-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="11e8a-126">Lors de la définition d’une jonction, le numéro de **port du serveur de médiation associé** doit se trouver dans la plage de ports d’écoute pour le protocole respectif autorisé par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="11e8a-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="11e8a-127">Cette plage de ports est définie sous Skype pour les pools Business Server et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="11e8a-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="11e8a-128">Le pool de serveur de médiation pertinent d’avec le bouton droit et sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="11e8a-129">Spécifiez la plage de ports dans le champ **Ports d’écoute**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-129">Specify the port range in the **Listening ports** field.</span></span>
  
9. <span data-ttu-id="11e8a-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-130">Click **OK**.</span></span> 
    

