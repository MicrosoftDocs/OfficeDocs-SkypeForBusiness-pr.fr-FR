---
title: Ajouter serveur
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Pour ajouter un nouveau serveur à un pool de serveurs, où le pool est une des opérations suivantes :'
ms.openlocfilehash: 609fbb28900ac67e0a4e1e2a400f1eebb29b2ff2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-server"></a><span data-ttu-id="049f6-103">Ajouter serveur</span><span class="sxs-lookup"><span data-stu-id="049f6-103">Add Server</span></span>
 
<span data-ttu-id="049f6-104">Pour ajouter un nouveau serveur à un pool de serveurs, où le pool est une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="049f6-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="049f6-105">Enterprise Edition Server frontal</span><span class="sxs-lookup"><span data-stu-id="049f6-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="049f6-106">Serveur de directeur</span><span class="sxs-lookup"><span data-stu-id="049f6-106">Director server</span></span>
    
- <span data-ttu-id="049f6-107">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="049f6-107">Mediation Server</span></span>
    
- <span data-ttu-id="049f6-108">Serveur de conférence audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="049f6-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="049f6-109">Serveur d’applications de confiance</span><span class="sxs-lookup"><span data-stu-id="049f6-109">Trusted Application server</span></span>
    
<span data-ttu-id="049f6-110">Chacun des nouveaux serveurs de pool a des besoins différents.</span><span class="sxs-lookup"><span data-stu-id="049f6-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="049f6-111">Dans les sections suivantes, recherchez le type de serveur que vous ajoutez à la liste existante et fournir les renseignements demandés telle qu’elle est définie pour chaque type de serveur.</span><span class="sxs-lookup"><span data-stu-id="049f6-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="049f6-112">Vous fournissez les informations requises pour définir le nouveau serveur du pool.</span><span class="sxs-lookup"><span data-stu-id="049f6-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="049f6-113">**Enterprise Edition Server frontal**</span><span class="sxs-lookup"><span data-stu-id="049f6-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="049f6-114">Nom de domaine (FQDN) du nouveau serveur complet tel qu’il est défini dans le système DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="049f6-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="049f6-115">Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisé.</span><span class="sxs-lookup"><span data-stu-id="049f6-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="049f6-116">Sinon, vous pouvez sélectionnez **limiter l’utilisation de service aux adresses IP sélectionnées** et entrez une adresse spécifique sur le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="049f6-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="049f6-117">L’adresse IP saisie est la seule adresse IP qui répondra pour les services hébergés.</span><span class="sxs-lookup"><span data-stu-id="049f6-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="049f6-118">Définissez une **adresse IP de RTPC** lorsqu’un serveur de médiation se trouve sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="049f6-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="049f6-119">Sélectionnez **Activer l’IPv6** pour activer IPv6 pour ce serveur.</span><span class="sxs-lookup"><span data-stu-id="049f6-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
 <span data-ttu-id="049f6-120">**Serveur de directeur**</span><span class="sxs-lookup"><span data-stu-id="049f6-120">**Director server**</span></span>
  
- <span data-ttu-id="049f6-121">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans le système DNS.</span><span class="sxs-lookup"><span data-stu-id="049f6-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="049f6-122">Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur sera utilisé.</span><span class="sxs-lookup"><span data-stu-id="049f6-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="049f6-123">Vous pouvez également vous sélectionnez **limiter l’utilisation de service aux adresses IP sélectionnées** et entrez une adresse IP spécifique sur le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="049f6-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="049f6-124">L’adresse IP saisie est la seule adresse IP qui répondra pour les services hébergés.</span><span class="sxs-lookup"><span data-stu-id="049f6-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
 <span data-ttu-id="049f6-125">**Serveur de médiation**</span><span class="sxs-lookup"><span data-stu-id="049f6-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="049f6-126">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans le système DNS.</span><span class="sxs-lookup"><span data-stu-id="049f6-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="049f6-127">Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisé.</span><span class="sxs-lookup"><span data-stu-id="049f6-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="049f6-128">Vous pouvez également vous sélectionnez **limiter l’utilisation de service aux adresses IP sélectionnées** et entrer une adresse IP spécifique sur le nouveau serveur en tant que l’adresse IP principale et une entrée une adresse IP pour l’adresse IP du réseau téléphonique public commuté.</span><span class="sxs-lookup"><span data-stu-id="049f6-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="049f6-129">Les adresses IP entrées sont la seule adresse IP qui répondra pour les services désignés.</span><span class="sxs-lookup"><span data-stu-id="049f6-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="049f6-130">Le serveur de médiation, l’adresse IP entrée pour l’adresse IP principale et l’adresse IP de PSTN est celle par défaut.</span><span class="sxs-lookup"><span data-stu-id="049f6-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="049f6-131">Les adresses IP peuvent être définies séparément si vous utilisez les interfaces de réseau dédié ou adresses IP distinctes sur la même interface de réseau.</span><span class="sxs-lookup"><span data-stu-id="049f6-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="049f6-132">Si vous avez des interfaces réseau de deux, une pour la connexion au réseau local et l’autre pour la connexion TLS, vous devez affecter des adresses IP différentes.</span><span class="sxs-lookup"><span data-stu-id="049f6-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
 <span data-ttu-id="049f6-133">**Serveur de conférence audio/vidéo**</span><span class="sxs-lookup"><span data-stu-id="049f6-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="049f6-134">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans le système DNS.</span><span class="sxs-lookup"><span data-stu-id="049f6-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="049f6-135">Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisé.</span><span class="sxs-lookup"><span data-stu-id="049f6-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="049f6-136">Sinon, vous pouvez sélectionnez **limiter l’utilisation de service aux adresses IP sélectionnées** et entrez une adresse spécifique sur le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="049f6-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="049f6-137">L’adresse IP saisie est la seule adresse IP qui répondra pour les services hébergés.</span><span class="sxs-lookup"><span data-stu-id="049f6-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
 <span data-ttu-id="049f6-138">**Serveur d’applications de confiance**</span><span class="sxs-lookup"><span data-stu-id="049f6-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="049f6-139">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans le système DNS.</span><span class="sxs-lookup"><span data-stu-id="049f6-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

