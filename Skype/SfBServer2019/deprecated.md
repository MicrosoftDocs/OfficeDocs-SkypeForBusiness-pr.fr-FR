---
title: Ce qui est déconseillé dans Skype entreprise Server 2019
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé: les fonctionnalités suivantes ont été supprimées de Skype entreprise Server 2019.'
ms.openlocfilehash: 9fd6ddc28a3b75b8d4c411aa7909516d4b5c0ab8
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418360"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="d336d-103">Ce qui est déconseillé dans Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="d336d-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="d336d-104">Découvrez les fonctionnalités déconseillées dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d336d-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="d336d-105">Pour plus d’informations sur les nouvelles fonctionnalités de Skype entreprise Server 2019, voir [qu’est-ce que Skype entreprise server 2019](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="d336d-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="d336d-106">Certaines fonctions inversées sont incluses dans Skype entreprise Server 2019 à des fins de compatibilité avec les versions antérieures du produit.</span><span class="sxs-lookup"><span data-stu-id="d336d-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="d336d-107">Fonctionnalités déconseillées dans Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="d336d-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="d336d-108">Passerelles XMPP pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d336d-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="d336d-109">Skype entreprise Server 2015 et ses prédécesseurs vous permettaient de configurer un proxy de messagerie électronique et de présence sur le serveur Edge et une passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="d336d-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="d336d-110">Cette fonctionnalité n’est plus disponible dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d336d-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="d336d-111">Conversation permanente pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d336d-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="d336d-112">Le serveur Chat permanent est un rôle facultatif qui permet à plusieurs utilisateurs de votre organisation de participer à des conversations de salles de conversation qui persistent dans le temps.</span><span class="sxs-lookup"><span data-stu-id="d336d-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="d336d-113">La conversation permanente ne peut pas être déployée avec Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d336d-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="d336d-114">Ce rôle de serveur est supprimé du générateur de topologie, ainsi que du code.</span><span class="sxs-lookup"><span data-stu-id="d336d-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="d336d-115">La même fonctionnalité est disponible dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d336d-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="d336d-116">Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="d336d-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="d336d-117">Mise en miroir SQL pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d336d-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="d336d-118">La mise en miroir SQL ne peut pas être déployée avec Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d336d-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="d336d-119">D’autres options de fourniture d’une haute disponibilité et de récupération d’urgence sont toujours prises en charge, et vous devez choisir entre elles.</span><span class="sxs-lookup"><span data-stu-id="d336d-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="d336d-120">Pour plus d’informations, consultez l’offre [pour une haute disponibilité et une reprise après sinistre dans Skype entreprise Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) .</span><span class="sxs-lookup"><span data-stu-id="d336d-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="d336d-121">Mises à niveau sur place</span><span class="sxs-lookup"><span data-stu-id="d336d-121">In-place upgrades</span></span> 

<span data-ttu-id="d336d-122">Les mises à niveau sur place étaient disponibles dans Skype entreprise Server 2015, mais ne sont plus prises en charge dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d336d-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d336d-123">La mise à niveau et la coexistence côte à côte sont prises en charge pour plus d’informations, reportez-vous à la rubrique [migration vers Skype entreprise Server 2019](migration/migration-to-skype-for-business-server-2019.md) .</span><span class="sxs-lookup"><span data-stu-id="d336d-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="d336d-124">Service de mobilité (MCX)</span><span class="sxs-lookup"><span data-stu-id="d336d-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="d336d-125">La prise en charge des services de mobilité par les anciens clients mobiles n’est plus disponible dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d336d-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="d336d-126">Il s’est déjà annoncé dans Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d336d-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="d336d-127">Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts.</span><span class="sxs-lookup"><span data-stu-id="d336d-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="d336d-128">Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="d336d-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="d336d-129">Pour plus d’informations, reportez-vous à la rubrique [planification de la mobilité pour Skype entreprise Server](../SfbServer/plan-your-deployment/mobility.md) et [comparaison des fonctionnalités du client mobile pour Skype entreprise](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span><span class="sxs-lookup"><span data-stu-id="d336d-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="d336d-130">Utilitaires</span><span class="sxs-lookup"><span data-stu-id="d336d-130">Tools</span></span>

<span data-ttu-id="d336d-131">Les outils suivants ne seront pas disponibles lors de la publication initiale de Skype entreprise Server 2019:</span><span class="sxs-lookup"><span data-stu-id="d336d-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="d336d-132">Calculateur de planification de la capacité Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d336d-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="d336d-133">Outils de débogage de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d336d-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="d336d-134">Outils du kit de ressources Skype entreprise Server (certains outils seront supprimés)</span><span class="sxs-lookup"><span data-stu-id="d336d-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="d336d-135">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="d336d-135">Call Parkometer</span></span>
    - <span data-ttu-id="d336d-136">Console utilisateur de recherche</span><span class="sxs-lookup"><span data-stu-id="d336d-136">Lookup user console</span></span>
    - <span data-ttu-id="d336d-137">Migration d’annonce de numéro non affectée</span><span class="sxs-lookup"><span data-stu-id="d336d-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="d336d-138">Les outils suivants ne sont pas pris en charge avec Skype entreprise Server 2019:</span><span class="sxs-lookup"><span data-stu-id="d336d-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="d336d-139">Méthodologie de qualité d’appel (mais pas de tableau de bord de qualité d’appel)</span><span class="sxs-lookup"><span data-stu-id="d336d-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="d336d-140">Carte de performance de méthodologie de qualité d’appel Microsoft, v 1.5</span><span class="sxs-lookup"><span data-stu-id="d336d-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="d336d-141">Outil de planification de Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="d336d-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="d336d-142">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="d336d-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="d336d-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d336d-143">See also</span></span>

[<span data-ttu-id="d336d-144">Nouveautés de Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="d336d-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="d336d-145">Migration de la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="d336d-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
