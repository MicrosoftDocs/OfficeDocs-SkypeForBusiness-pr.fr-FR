---
title: Ajouter un serveur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Pour ajouter un nouveau serveur à un pool de serveurs existant, où le pool est l’un des suivants :'
ms.openlocfilehash: 5e6d1772b1cb18fe8c392e3ad9fa4f131415e522
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216405"
---
# <a name="add-server"></a><span data-ttu-id="de1e6-103">Ajouter un serveur</span><span class="sxs-lookup"><span data-stu-id="de1e6-103">Add Server</span></span>
 
<span data-ttu-id="de1e6-104">Pour ajouter un nouveau serveur à un pool de serveurs existant, où le pool est l’un des suivants :</span><span class="sxs-lookup"><span data-stu-id="de1e6-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="de1e6-105">Serveur frontal Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="de1e6-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="de1e6-106">Serveur directeur</span><span class="sxs-lookup"><span data-stu-id="de1e6-106">Director server</span></span>
    
- <span data-ttu-id="de1e6-107">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="de1e6-107">Mediation Server</span></span>
    
- <span data-ttu-id="de1e6-108">Serveur de conférence audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="de1e6-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="de1e6-109">Serveur d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="de1e6-109">Trusted Application server</span></span>
    
<span data-ttu-id="de1e6-p101">Chaque nouveau serveur de pool a des exigences différentes. Dans les sections suivantes, recherchez le type de serveur que vous ajoutez à un pool existant et fournissez les informations requises tel que définit pour chaque type de serveur. Fournissez les informations demandées pour définir le nouveau pool de serveurs.</span><span class="sxs-lookup"><span data-stu-id="de1e6-p101">Each of the new pool servers has different requirements. In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type. You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="de1e6-113">**Serveur frontal Enterprise Edition**</span><span class="sxs-lookup"><span data-stu-id="de1e6-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="de1e6-114">Le nom de domaine complet (FQDN) du nouveau serveur tel qu’il est défini dans DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="de1e6-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="de1e6-p102">Sélectionnez **Utiliser toutes les adresses IP configurées**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisée. Vous pouvez également sélectionner **Limiter l’utilisation des services aux adresses spécifiées** et entrer une adresse spécifique sur le nouveau serveur. L’adresse IP entrée est la seule adresse IP qui répondra aux services hébergés.</span><span class="sxs-lookup"><span data-stu-id="de1e6-p102">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="de1e6-118">Définissez une **Adresse IP PSTN** lorsqu’un serveur de médiation est colocalisé sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="de1e6-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="de1e6-119">Sélectionnez **Activer IPv6** pour activer IPv6 pour ce serveur.</span><span class="sxs-lookup"><span data-stu-id="de1e6-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="de1e6-120">**Serveur directeur**</span><span class="sxs-lookup"><span data-stu-id="de1e6-120">**Director server**</span></span>
  
- <span data-ttu-id="de1e6-121">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="de1e6-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="de1e6-p103">Sélectionnez **Utiliser toutes les adresses IP configurées**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur sera utilisée. Vous pouvez aussi sélectionner **Limiter l’utilisation des services aux adresses IP sélectionnées** et entrer une adresse IP spécifique sur le nouveau serveur. L’adresse IP entrée est la seule adresse IP qui répondra aux services hébergés.</span><span class="sxs-lookup"><span data-stu-id="de1e6-p103">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="de1e6-125">**Serveur de médiation**</span><span class="sxs-lookup"><span data-stu-id="de1e6-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="de1e6-126">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="de1e6-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="de1e6-p104">Sélectionnez **Utiliser toutes les adresses IP configurées**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisée. Vous pouvez également sélectionner **Limiter l’utilisation des services aux adresses IP sélectionnées** et entrer une adresse IP spécifique sur le nouveau serveur en tant qu’adresse IP primaire, et une adresse IP pour l'adresse IP du réseau téléphonique commuté (PSTN). Les adresses IP entrées sont les seules adresses IP qui répondront aux services désignés.</span><span class="sxs-lookup"><span data-stu-id="de1e6-p104">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address. The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="de1e6-p105">Pour le serveur de médiation, l’adresse IP entrée pour l’adresse IP principale et l’adresse IP PSTN est identique par défaut. Les adresses IP peuvent être définies séparément si vous utilisez des interfaces réseau dédiées ou des adresses IP distinctes sur la même interface réseau. Si vous avez deux interfaces réseau, une pour la connexion au réseau local et une pour la connexion PSTN, vous devez assigner des adresses IP différentes.</span><span class="sxs-lookup"><span data-stu-id="de1e6-p105">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default. The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface. If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="de1e6-133">**Serveur de conférence audio/vidéo**</span><span class="sxs-lookup"><span data-stu-id="de1e6-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="de1e6-134">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="de1e6-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="de1e6-p106">Sélectionnez **Utiliser toutes les adresses IP configurées**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisée. Vous pouvez également sélectionner **Limiter l’utilisation des services aux adresses spécifiées** et entrer une adresse spécifique sur le nouveau serveur. L’adresse IP entrée est la seule adresse IP qui répondra aux services hébergés.</span><span class="sxs-lookup"><span data-stu-id="de1e6-p106">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="de1e6-138">**Serveur d’applications approuvées**</span><span class="sxs-lookup"><span data-stu-id="de1e6-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="de1e6-139">Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.</span><span class="sxs-lookup"><span data-stu-id="de1e6-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

