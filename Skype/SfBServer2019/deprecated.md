---
title: Ce qui est déconseillé de Skype pour Business Server 2019
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/10/2018
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : Ces fonctionnalités ont été supprimées de Skype pour Business Server 2019.'
ms.openlocfilehash: 66366c2272db8d6f605fde6dc066f730543883b6
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530541"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="e895d-103">Ce qui est déconseillé de Skype pour Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e895d-103">What's deprecated from Skype for Business Server 2019</span></span> 

<span data-ttu-id="e895d-104">Découvrez les fonctionnalités qui sont déconseillées dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e895d-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="e895d-105">Pour plus d’informations sur les nouvelles fonctionnalités dans Skype pour Business Server 2019, voir [Nouveautés de Skype pour Business Server 2019](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="e895d-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="e895d-106">Certaines fonctionnalités de retrait emphasised sont incluses dans Skype pour Business Server 2019 pour la compatibilité avec les versions antérieures du produit.</span><span class="sxs-lookup"><span data-stu-id="e895d-106">Some de-emphasised features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span> 

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="e895d-107">Fonctionnalités déconseillées dans Skype pour Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e895d-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="e895d-108">Passerelles XMPP pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="e895d-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="e895d-109">Skype pour Business Server 2015 et ses prédécesseurs autorisés vous permet de configurer un proxy XMPP et de présence Protocol (XMPP) sur le serveur de périphérie et une passerelle XMPP sur le pool frontal ou serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="e895d-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="e895d-110">Cette fonctionnalité n’est plus disponible dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e895d-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>


### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="e895d-111">Conversation permanente pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="e895d-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="e895d-112">Serveur de conversation permanente est un rôle facultatif qui permet à plusieurs utilisateurs dans votre organisation participer à des conversations de salle de conversation persistant.</span><span class="sxs-lookup"><span data-stu-id="e895d-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="e895d-113">Conversation permanente ne peuvent pas être déployée avec Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e895d-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="e895d-114">Ce rôle de serveur est supprimé du Générateur de topologie, ainsi que du code.</span><span class="sxs-lookup"><span data-stu-id="e895d-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="e895d-115">La même fonctionnalité est disponible dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="e895d-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="e895d-116">Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="e895d-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span>   

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="e895d-117">Mise en miroir de SQL pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="e895d-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="e895d-118">La mise en miroir SQL ne peut pas être déployé avec Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e895d-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="e895d-119">Autres options pour fournir une haute disponibilité et récupération d’urgence sont toujours supportées et vous devez choisir parmi les.</span><span class="sxs-lookup"><span data-stu-id="e895d-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="e895d-120">Voir [planifier la haute disponibilité et de récupération d’urgence dans Skype pour Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) pour passer en revue les options.</span><span class="sxs-lookup"><span data-stu-id="e895d-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="e895d-121">Mises à niveau sur place</span><span class="sxs-lookup"><span data-stu-id="e895d-121">In-place upgrades</span></span> 

<span data-ttu-id="e895d-122">Mises à niveau sur place étaient disponibles dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e895d-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e895d-123">Côte à côte mise à niveau et la coexistence, consultez [Migration vers Skype pour Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="e895d-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

###  <a name="mobility-service-mcx"></a><span data-ttu-id="e895d-124">Service de mobilité (Mcx)</span><span class="sxs-lookup"><span data-stu-id="e895d-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="e895d-125">Prise en charge du Service Mobility utilisé par les clients hérités mobiles n’est plus disponible dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e895d-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e895d-126">Il a été précédemment annoncé dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e895d-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="e895d-127">Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="e895d-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e895d-128">Les utilisateurs avec les clients hérités Mcx doivent mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="e895d-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="e895d-129">Pour plus d’informations, voir [planifier la mobilité Skype pour Business Server](../SfbServer/plan-your-deployment/mobility.md) et [comparaison des fonctionnalités de client Mobile pour Skype pour les entreprises](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span><span class="sxs-lookup"><span data-stu-id="e895d-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="e895d-130">Outils</span><span class="sxs-lookup"><span data-stu-id="e895d-130">Tools</span></span>

<span data-ttu-id="e895d-131">Les outils suivants ne sera pas disponibles pour la version initiale de Skype pour Business Server 2019 :</span><span class="sxs-lookup"><span data-stu-id="e895d-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="e895d-132">Skype pour calculateur de planification de la capacité de serveur Business</span><span class="sxs-lookup"><span data-stu-id="e895d-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="e895d-133">Skype pour Business Server Outils de débogage</span><span class="sxs-lookup"><span data-stu-id="e895d-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="e895d-134">Skype pour les outils du Kit de ressources Business Server (certains outils seront supprimés)</span><span class="sxs-lookup"><span data-stu-id="e895d-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="e895d-135">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="e895d-135">Call Parkometer</span></span>
    - <span data-ttu-id="e895d-136">Console utilisateur de recherche</span><span class="sxs-lookup"><span data-stu-id="e895d-136">Lookup user console</span></span>
    - <span data-ttu-id="e895d-137">Numéro non attribué Migration annonce</span><span class="sxs-lookup"><span data-stu-id="e895d-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="e895d-138">Les outils suivants ne sont pas pris en charge avec Skype pour Business Server 2019 :</span><span class="sxs-lookup"><span data-stu-id="e895d-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="e895d-139">Méthodologie de la qualité des appels (mais pas appeler de tableau de bord qualité)</span><span class="sxs-lookup"><span data-stu-id="e895d-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="e895d-140">Carte de performance Microsoft appel qualité méthodologie, v1.5</span><span class="sxs-lookup"><span data-stu-id="e895d-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="e895d-141">Skype for Business Server 2015 Planning Tool</span><span class="sxs-lookup"><span data-stu-id="e895d-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="e895d-142">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="e895d-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="e895d-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e895d-143">See also</span></span>

[<span data-ttu-id="e895d-144">Quelles sont les nouveautés dans Skype pour Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e895d-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="e895d-145">Migration de la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="e895d-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)