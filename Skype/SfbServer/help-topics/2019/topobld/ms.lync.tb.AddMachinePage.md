---
title: Ajouter un serveur
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 5db99c8cdd2a08722a27a9da437911dcf573d5bf
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220926"
---
# <a name="add-server"></a><span data-ttu-id="0150d-103">Ajouter un serveur</span><span class="sxs-lookup"><span data-stu-id="0150d-103">Add Server</span></span>
 
<span data-ttu-id="0150d-104">Pour ajouter un nouveau serveur à un pool existant de serveurs, où le pool est une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0150d-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="0150d-105">Enterprise Edition Server frontal</span><span class="sxs-lookup"><span data-stu-id="0150d-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="0150d-106">Serveur directeur</span><span class="sxs-lookup"><span data-stu-id="0150d-106">Director server</span></span>
    
- <span data-ttu-id="0150d-107">serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="0150d-107">Mediation Server</span></span>
    
- <span data-ttu-id="0150d-108">Serveur de conférence audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="0150d-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="0150d-109">Serveur d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="0150d-109">Trusted Application server</span></span>
    
<span data-ttu-id="0150d-110">Chacun des nouveaux serveurs de pool a des exigences différentes.</span><span class="sxs-lookup"><span data-stu-id="0150d-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="0150d-111">Dans les sections suivantes, recherchez le type de serveur que vous ajoutez au pool existant et fournit les informations demandées telle qu’elle est définie pour chaque type de serveur.</span><span class="sxs-lookup"><span data-stu-id="0150d-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="0150d-112">Vous fournir les informations demandées pour définir le nouveau serveur du pool.</span><span class="sxs-lookup"><span data-stu-id="0150d-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="0150d-113">**Enterprise Edition Server frontal**</span><span class="sxs-lookup"><span data-stu-id="0150d-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="0150d-114">Domaine nom complet (FQDN) du nouveau serveur tel qu’il est défini dans le système DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="0150d-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="0150d-115">Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisée.</span><span class="sxs-lookup"><span data-stu-id="0150d-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="0150d-116">Sinon, vous pouvez sélectionner **limiter l’utilisation de service pour les adresses IP sélectionnées** et entrez une adresse spécifique sur le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="0150d-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="0150d-117">L’adresse IP saisie est la seule adresse IP qui répondra pour les services hébergés.</span><span class="sxs-lookup"><span data-stu-id="0150d-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="0150d-118">Définir une **adresse IP PSTN** lorsqu’un serveur de médiation est colocalisé sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="0150d-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="0150d-119">Sélectionnez **Activer IPv6** pour activer IPv6 pour ce serveur.</span><span class="sxs-lookup"><span data-stu-id="0150d-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="0150d-120">**Serveur directeur**</span><span class="sxs-lookup"><span data-stu-id="0150d-120">**Director server**</span></span>
  
- <span data-ttu-id="0150d-121">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="0150d-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="0150d-122">Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur est utilisé.</span><span class="sxs-lookup"><span data-stu-id="0150d-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="0150d-123">Vous pouvez également vous sélectionnez **limiter l’utilisation de service pour les adresses IP sélectionnées** et entrez une adresse IP spécifique sur le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="0150d-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="0150d-124">L’adresse IP saisie est la seule adresse IP qui répondra pour les services hébergés.</span><span class="sxs-lookup"><span data-stu-id="0150d-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="0150d-125">**Serveur de médiation**</span><span class="sxs-lookup"><span data-stu-id="0150d-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="0150d-126">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="0150d-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="0150d-127">Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisée.</span><span class="sxs-lookup"><span data-stu-id="0150d-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="0150d-128">Vous pouvez également vous sélectionnez **limiter l’utilisation de service pour les adresses IP sélectionnées** et entrez une adresse IP spécifique sur le nouveau serveur en tant que l’adresse IP principale et une adresse IP pour l’adresse IP du réseau téléphonique commuté public entrée.</span><span class="sxs-lookup"><span data-stu-id="0150d-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="0150d-129">Les adresses IP entrées sont la seule adresse IP qui répondra pour les services désignés.</span><span class="sxs-lookup"><span data-stu-id="0150d-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0150d-130">Le serveur de médiation, l’adresse IP entrée pour l’adresse IP principale et l’adresse IP PSTN est le même par défaut.</span><span class="sxs-lookup"><span data-stu-id="0150d-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="0150d-131">Les adresses IP peuvent être définies séparément si vous utilisez les interfaces réseau dédié ou des adresses IP séparées sur la même interface réseau.</span><span class="sxs-lookup"><span data-stu-id="0150d-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="0150d-132">Si vous avez des interfaces réseau deux, l’autre pour la connexion au réseau local et l’autre pour la connexion PSTN, vous devez assigner des adresses IP différentes.</span><span class="sxs-lookup"><span data-stu-id="0150d-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="0150d-133">**Serveur de conférence audio/vidéo**</span><span class="sxs-lookup"><span data-stu-id="0150d-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="0150d-134">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="0150d-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="0150d-135">Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisée.</span><span class="sxs-lookup"><span data-stu-id="0150d-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="0150d-136">Sinon, vous pouvez sélectionner **limiter l’utilisation de service pour les adresses IP sélectionnées** et entrez une adresse spécifique sur le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="0150d-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="0150d-137">L’adresse IP saisie est la seule adresse IP qui répondra pour les services hébergés.</span><span class="sxs-lookup"><span data-stu-id="0150d-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="0150d-138">**Serveur d’applications approuvées**</span><span class="sxs-lookup"><span data-stu-id="0150d-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="0150d-139">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="0150d-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

