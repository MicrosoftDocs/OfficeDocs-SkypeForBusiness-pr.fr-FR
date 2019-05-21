---
title: Ajouter un serveur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Pour ajouter un nouveau serveur à un pool de serveurs existant, où le pool est l’un des éléments suivants:'
ms.openlocfilehash: 32033d7d758528fc925c5c228971c040828bd654
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290505"
---
# <a name="add-server"></a><span data-ttu-id="1abb2-103">Ajouter un serveur</span><span class="sxs-lookup"><span data-stu-id="1abb2-103">Add Server</span></span>
 
<span data-ttu-id="1abb2-104">Pour ajouter un nouveau serveur à un pool de serveurs existant, où le pool est l’un des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="1abb2-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="1abb2-105">Serveur frontal d’Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="1abb2-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="1abb2-106">Serveur Director</span><span class="sxs-lookup"><span data-stu-id="1abb2-106">Director server</span></span>
    
- <span data-ttu-id="1abb2-107">serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="1abb2-107">Mediation Server</span></span>
    
- <span data-ttu-id="1abb2-108">Serveur de visioconférence audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="1abb2-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="1abb2-109">Serveur d’applications de confiance</span><span class="sxs-lookup"><span data-stu-id="1abb2-109">Trusted Application server</span></span>
    
<span data-ttu-id="1abb2-110">Chacun des nouveaux serveurs de pools a des exigences différentes.</span><span class="sxs-lookup"><span data-stu-id="1abb2-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="1abb2-111">Dans les sections suivantes, recherchez le type de serveur que vous ajoutez au pool existant, puis fournissez les informations demandées comme il est défini pour chaque type de serveur.</span><span class="sxs-lookup"><span data-stu-id="1abb2-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="1abb2-112">Vous fournissez les informations demandées pour définir le nouveau serveur du pool.</span><span class="sxs-lookup"><span data-stu-id="1abb2-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="1abb2-113">**Serveur frontal d’Enterprise Edition**</span><span class="sxs-lookup"><span data-stu-id="1abb2-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="1abb2-114">Nom de domaine complet (FQDN) du nouveau serveur, tel qu’il est défini dans DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="1abb2-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="1abb2-115">Sélectionnez **utiliser toutes les adresses IP configurées**, ce qui signifie que toute adresse IP définie sur l’ordinateur peut être utilisée.</span><span class="sxs-lookup"><span data-stu-id="1abb2-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="1abb2-116">Vous pouvez également sélectionner **limiter l’utilisation du service aux adresses IP sélectionnées** et entrer une adresse particulière sur le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="1abb2-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="1abb2-117">L’adresse IP entrée est la seule adresse IP qui répond aux services hébergés.</span><span class="sxs-lookup"><span data-stu-id="1abb2-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="1abb2-118">Définissez une **adresse IP RTC** quand un serveur de médiation est colocalisé sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="1abb2-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="1abb2-119">Sélectionnez **activer IPv6** pour activer le protocole IPv6 pour ce serveur.</span><span class="sxs-lookup"><span data-stu-id="1abb2-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="1abb2-120">**Serveur Director**</span><span class="sxs-lookup"><span data-stu-id="1abb2-120">**Director server**</span></span>
  
- <span data-ttu-id="1abb2-121">Nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="1abb2-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="1abb2-122">Activez l’option **utiliser toutes les adresses IP configurées**, ce qui signifie que toute adresse IP définie sur l’ordinateur sera utilisée.</span><span class="sxs-lookup"><span data-stu-id="1abb2-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="1abb2-123">Vous pouvez également sélectionner **limiter l’utilisation du service aux adresses IP sélectionnées** et entrer une adresse IP particulière sur le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="1abb2-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="1abb2-124">L’adresse IP entrée est la seule adresse IP qui répond aux services hébergés.</span><span class="sxs-lookup"><span data-stu-id="1abb2-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="1abb2-125">**Serveur de médiation**</span><span class="sxs-lookup"><span data-stu-id="1abb2-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="1abb2-126">Nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="1abb2-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="1abb2-127">Sélectionnez **utiliser toutes les adresses IP configurées**, ce qui signifie que toute adresse IP définie sur l’ordinateur peut être utilisée.</span><span class="sxs-lookup"><span data-stu-id="1abb2-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="1abb2-128">Vous pouvez également sélectionner **limiter l’utilisation du service aux adresses IP sélectionnées** et entrer une adresse IP particulière sur le nouveau serveur en tant qu’adresse IP principale et entrer une adresse IP pour l’adresse IP du réseau téléphonique public commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="1abb2-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="1abb2-129">Les adresses IP entrées sont la seule adresse IP qui répond aux services désignés.</span><span class="sxs-lookup"><span data-stu-id="1abb2-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1abb2-130">Pour le serveur de médiation, l’adresse IP entrée pour l’adresse IP principale et l’adresse IP RTC est identique par défaut.</span><span class="sxs-lookup"><span data-stu-id="1abb2-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="1abb2-131">Les adresses IP peuvent être définies séparément si vous utilisez des interfaces réseau dédiées ou des adresses IP distinctes sur la même interface réseau.</span><span class="sxs-lookup"><span data-stu-id="1abb2-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="1abb2-132">Si vous avez deux interfaces réseau, une pour la connexion réseau locale et une pour la connexion RTC, vous devez attribuer des adresses IP différentes.</span><span class="sxs-lookup"><span data-stu-id="1abb2-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="1abb2-133">**Serveur de visioconférence audio/vidéo**</span><span class="sxs-lookup"><span data-stu-id="1abb2-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="1abb2-134">Nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="1abb2-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="1abb2-135">Sélectionnez **utiliser toutes les adresses IP configurées**, ce qui signifie que toute adresse IP définie sur l’ordinateur peut être utilisée.</span><span class="sxs-lookup"><span data-stu-id="1abb2-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="1abb2-136">Vous pouvez également sélectionner **limiter l’utilisation du service aux adresses IP sélectionnées** et entrer une adresse particulière sur le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="1abb2-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="1abb2-137">L’adresse IP entrée est la seule adresse IP qui répond aux services hébergés.</span><span class="sxs-lookup"><span data-stu-id="1abb2-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="1abb2-138">**Serveur d’applications de confiance**</span><span class="sxs-lookup"><span data-stu-id="1abb2-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="1abb2-139">Nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="1abb2-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

