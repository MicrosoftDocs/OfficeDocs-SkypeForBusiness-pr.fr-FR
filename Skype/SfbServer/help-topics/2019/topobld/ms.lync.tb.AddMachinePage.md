---
title: Ajouter un serveur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour ajouter un nouveau serveur à un pool existant de serveurs, où le pool est une des opérations suivantes :'
ms.openlocfilehash: 562dbc44641c5af72224dbcbb0df494b7c0346d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888913"
---
# <a name="add-server"></a><span data-ttu-id="9d80b-103">Ajouter un serveur</span><span class="sxs-lookup"><span data-stu-id="9d80b-103">Add Server</span></span>
 
<span data-ttu-id="9d80b-104">Pour ajouter un nouveau serveur à un pool existant de serveurs, où le pool est une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d80b-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="9d80b-105">Enterprise Edition Server frontal</span><span class="sxs-lookup"><span data-stu-id="9d80b-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="9d80b-106">Serveur directeur</span><span class="sxs-lookup"><span data-stu-id="9d80b-106">Director server</span></span>
    
- <span data-ttu-id="9d80b-107">serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="9d80b-107">Mediation Server</span></span>
    
- <span data-ttu-id="9d80b-108">Serveur de conférence audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="9d80b-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="9d80b-109">Serveur d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="9d80b-109">Trusted Application server</span></span>
    
<span data-ttu-id="9d80b-110">Chacun des nouveaux serveurs de pool a des exigences différentes.</span><span class="sxs-lookup"><span data-stu-id="9d80b-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="9d80b-111">Dans les sections suivantes, recherchez le type de serveur que vous ajoutez au pool existant et fournit les informations demandées telle qu’elle est définie pour chaque type de serveur.</span><span class="sxs-lookup"><span data-stu-id="9d80b-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="9d80b-112">Vous fournir les informations demandées pour définir le nouveau serveur du pool.</span><span class="sxs-lookup"><span data-stu-id="9d80b-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="9d80b-113">**Enterprise Edition Server frontal**</span><span class="sxs-lookup"><span data-stu-id="9d80b-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="9d80b-114">Domaine nom complet (FQDN) du nouveau serveur tel qu’il est défini dans le système DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="9d80b-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="9d80b-115">Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisée.</span><span class="sxs-lookup"><span data-stu-id="9d80b-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="9d80b-116">Sinon, vous pouvez sélectionner **limiter l’utilisation de service pour les adresses IP sélectionnées** et entrez une adresse spécifique sur le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="9d80b-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="9d80b-117">L’adresse IP saisie est la seule adresse IP qui répondra pour les services hébergés.</span><span class="sxs-lookup"><span data-stu-id="9d80b-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="9d80b-118">Définir une **adresse IP PSTN** lorsqu’un serveur de médiation est colocalisé sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="9d80b-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="9d80b-119">Sélectionnez **Activer IPv6** pour activer IPv6 pour ce serveur.</span><span class="sxs-lookup"><span data-stu-id="9d80b-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="9d80b-120">**Serveur directeur**</span><span class="sxs-lookup"><span data-stu-id="9d80b-120">**Director server**</span></span>
  
- <span data-ttu-id="9d80b-121">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="9d80b-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="9d80b-122">Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur est utilisé.</span><span class="sxs-lookup"><span data-stu-id="9d80b-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="9d80b-123">Vous pouvez également vous sélectionnez **limiter l’utilisation de service pour les adresses IP sélectionnées** et entrez une adresse IP spécifique sur le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="9d80b-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="9d80b-124">L’adresse IP saisie est la seule adresse IP qui répondra pour les services hébergés.</span><span class="sxs-lookup"><span data-stu-id="9d80b-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="9d80b-125">**Serveur de médiation**</span><span class="sxs-lookup"><span data-stu-id="9d80b-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="9d80b-126">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="9d80b-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="9d80b-127">Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisée.</span><span class="sxs-lookup"><span data-stu-id="9d80b-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="9d80b-128">Vous pouvez également vous sélectionnez **limiter l’utilisation de service pour les adresses IP sélectionnées** et entrez une adresse IP spécifique sur le nouveau serveur en tant que l’adresse IP principale et une adresse IP pour l’adresse IP du réseau téléphonique commuté public entrée.</span><span class="sxs-lookup"><span data-stu-id="9d80b-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="9d80b-129">Les adresses IP entrées sont la seule adresse IP qui répondra pour les services désignés.</span><span class="sxs-lookup"><span data-stu-id="9d80b-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9d80b-130">Le serveur de médiation, l’adresse IP entrée pour l’adresse IP principale et l’adresse IP PSTN est le même par défaut.</span><span class="sxs-lookup"><span data-stu-id="9d80b-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="9d80b-131">Les adresses IP peuvent être définies séparément si vous utilisez les interfaces réseau dédié ou des adresses IP séparées sur la même interface réseau.</span><span class="sxs-lookup"><span data-stu-id="9d80b-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="9d80b-132">Si vous avez des interfaces réseau deux, l’autre pour la connexion au réseau local et l’autre pour la connexion PSTN, vous devez assigner des adresses IP différentes.</span><span class="sxs-lookup"><span data-stu-id="9d80b-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="9d80b-133">**Serveur de conférence audio/vidéo**</span><span class="sxs-lookup"><span data-stu-id="9d80b-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="9d80b-134">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="9d80b-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="9d80b-135">Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisée.</span><span class="sxs-lookup"><span data-stu-id="9d80b-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="9d80b-136">Sinon, vous pouvez sélectionner **limiter l’utilisation de service pour les adresses IP sélectionnées** et entrez une adresse spécifique sur le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="9d80b-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="9d80b-137">L’adresse IP saisie est la seule adresse IP qui répondra pour les services hébergés.</span><span class="sxs-lookup"><span data-stu-id="9d80b-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="9d80b-138">**Serveur d’applications approuvées**</span><span class="sxs-lookup"><span data-stu-id="9d80b-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="9d80b-139">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="9d80b-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

