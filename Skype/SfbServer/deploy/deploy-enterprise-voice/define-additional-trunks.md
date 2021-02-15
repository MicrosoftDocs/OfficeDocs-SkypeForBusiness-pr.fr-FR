---
title: Définir des branches supplémentaires dans le Générateur de topologies dans Skype Entreprise Server
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Résumé : Découvrez comment définir une branche supplémentaire entre un serveur de médiation et un homologue de passerelle dans le Générateur de topologies dans Skype Entreprise Server.'
ms.openlocfilehash: 3aab744761420ab631f17e6b56391f1fab120ccf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836994"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="646a4-103">Définir des branches supplémentaires dans le Générateur de topologies dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="646a4-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="646a4-104">**Résumé :** Découvrez comment définir une branche supplémentaire entre un serveur de médiation et un homologue de passerelle dans le Générateur de topologies dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="646a4-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="646a4-105">Suivez ces étapes pour définir une ligne supplémentaire à laquelle vous pouvez associer un homologue à un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="646a4-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="646a4-106">Un homologue fournit aux utilisateurs activés pour Voix Entreprise la connectivité au réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="646a4-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="646a4-107">Un homologue peut être une passerelle PSTN, un SYSTÈME IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="646a4-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="646a4-108">Une connexion est une connexion logique entre un serveur de médiation et une passerelle.</span><span class="sxs-lookup"><span data-stu-id="646a4-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="646a4-109">Cette rubrique suppose que vous avez configuré une passerelle PSTN et une trunk racine avec au moins un serveur de médiation ou pool cum ou autonome, comme décrit dans Définir une passerelle dans le Générateur de topologies dans [Skype Entreprise Server](define-a-gateway.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="646a4-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="646a4-110">Pour définir une ligne supplémentaire entre un serveur de médiation et un homologue de passerelle</span><span class="sxs-lookup"><span data-stu-id="646a4-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="646a4-111">Démarrez le Générateur de topologie : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **Server 2015,** puis sur Générateur skype entreprise **Server 2015Topology.**</span><span class="sxs-lookup"><span data-stu-id="646a4-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="646a4-112">Sous Skype Entreprise Server, nom de votre site, **Composants partagés,** cliquez avec le bouton droit sur le nœud **Trunks,** puis cliquez sur **New Trunk**.</span><span class="sxs-lookup"><span data-stu-id="646a4-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="646a4-113">Dans **Définir une nouvelle trunk**, spécifiez un nom convivial pour identifier la trunk de manière unique.</span><span class="sxs-lookup"><span data-stu-id="646a4-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="646a4-114">Vous ne pouvez pas avoir deux branches du même nom.</span><span class="sxs-lookup"><span data-stu-id="646a4-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="646a4-115">Si vous spécifiez le type de transport TLS (Transport Layer Security), vous devez spécifier le nom de groupe au lieu de l’adresse IP de l’homologue du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="646a4-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="646a4-116">Sous **Passerelle PSTN associée,** sélectionnez l’homologue de passerelle PSTN à associer à cette passerelle.</span><span class="sxs-lookup"><span data-stu-id="646a4-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="646a4-117">Sous Le port d’écoute pour la passerelle **PSTN,** tapez le port d’écoute que l’homologue (passerelle PSTN, IP-PBX ou SBC) recevra des messages SIP du serveur de médiation qui doit être associé à cette passerelle.</span><span class="sxs-lookup"><span data-stu-id="646a4-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="646a4-118">Les ports homologues par défaut sont 5066 pour le protocole TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="646a4-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="646a4-119">Les ports survivable Branch Appliance par défaut sont 5081 pour TCP et 5082 pour TLS.</span><span class="sxs-lookup"><span data-stu-id="646a4-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="646a4-120">Sous **Protocole de transport SIP,** cliquez sur le type de transport utilisé par l’homologue.</span><span class="sxs-lookup"><span data-stu-id="646a4-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="646a4-121">Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation qui peut utiliser TLS.</span><span class="sxs-lookup"><span data-stu-id="646a4-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="646a4-122">Sous **Serveur de médiation associé,** sélectionnez le pool de serveurs de médiation à associer à la branche racine de cet homologue</span><span class="sxs-lookup"><span data-stu-id="646a4-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="646a4-123">Sous **le port du serveur de médiation associé,** tapez le port d’écoute que le serveur de médiation recevra des messages SIP de l’homologue.</span><span class="sxs-lookup"><span data-stu-id="646a4-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="646a4-124">Avec la prise en charge de plusieurs trunks dans Skype Entreprise Server, deux trunks avec des noms de trunks différents ne peuvent pas être configurés avec le même port de serveur de médiation associé et le même **port** d’écoute pour la passerelle **IP/PSTN**</span><span class="sxs-lookup"><span data-stu-id="646a4-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="646a4-125">Avec la prise en charge de plusieurs branches dans Skype Entreprise Server, plusieurs ports de signalisation SIP peuvent être définis sur le serveur de médiation pour la communication avec plusieurs homologues.</span><span class="sxs-lookup"><span data-stu-id="646a4-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="646a4-126">Lors de la définition d’une trunk, le numéro de **port** du serveur de médiation associé doit se trouver dans la plage des ports d’écoute pour le protocole respectif autorisé par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="646a4-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="646a4-127">Cette plage de ports est définie sous les pools de serveurs skype entreprise et de médiation.</span><span class="sxs-lookup"><span data-stu-id="646a4-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="646a4-128">Cliquez avec le bouton droit sur le pool de serveurs de médiation approprié, puis sélectionnez **Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="646a4-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="646a4-129">Spécifiez la plage de ports dans le champ **Ports d’écoute**.</span><span class="sxs-lookup"><span data-stu-id="646a4-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="646a4-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="646a4-130">Click **OK**.</span></span> 
    

