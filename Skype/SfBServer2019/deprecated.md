---
title: Fonctionnalités déconseillées de Skype entreprise Server 2019
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : ces fonctionnalités ont été supprimées de Skype entreprise Server 2019.'
ms.openlocfilehash: 40a202f802ec8ac1a0f880f92ad9cf59ce68a627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42125217"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="bc209-103">Fonctionnalités déconseillées de Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="bc209-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="bc209-104">Découvrez les fonctionnalités qui sont déconseillées dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bc209-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="bc209-105">Pour plus d’informations sur les nouvelles fonctionnalités de Skype entreprise Server 2019, consultez [la rubrique what’s in Skype for Business server 2019](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="bc209-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="bc209-106">Certaines fonctionnalités de mise en évidence sont incluses dans Skype entreprise Server 2019 pour la compatibilité avec les versions antérieures du produit.</span><span class="sxs-lookup"><span data-stu-id="bc209-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="bc209-107">Fonctionnalités déconseillées dans Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="bc209-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="bc209-108">Passerelles XMPP pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bc209-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="bc209-109">Skype entreprise Server 2015 et ses prédécesseurs vous permettaient de configurer un proxy XMPP (extensible Messaging and Presence Protocol) sur le serveur Edge et une passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="bc209-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="bc209-110">Cette fonctionnalité n’est plus disponible dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bc209-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="bc209-111">Conversation permanente pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bc209-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="bc209-112">Le serveur de conversation permanente est un rôle facultatif qui permet à plusieurs utilisateurs de votre organisation de participer à des conversations de salle de conversation qui persistent dans le temps.</span><span class="sxs-lookup"><span data-stu-id="bc209-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="bc209-113">La conversation permanente ne peut pas être déployée avec Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bc209-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="bc209-114">Ce rôle serveur est supprimé du générateur de topologies, ainsi que du code.</span><span class="sxs-lookup"><span data-stu-id="bc209-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="bc209-115">Les mêmes fonctionnalités sont disponibles dans Teams.</span><span class="sxs-lookup"><span data-stu-id="bc209-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="bc209-116">Pour plus d’informations, consultez [la rubrique prise en main de la mise à niveau de Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="bc209-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="bc209-117">Mise en miroir SQL pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bc209-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="bc209-118">La mise en miroir SQL ne peut pas être déployée avec Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bc209-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="bc209-119">D’autres options de fourniture de haute disponibilité et de récupération d’urgence sont toujours prises en charge et vous devez choisir parmi celles-ci.</span><span class="sxs-lookup"><span data-stu-id="bc209-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="bc209-120">Reportez-vous à la rubrique [plan for High Availability and Disaster Recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) pour consulter les options.</span><span class="sxs-lookup"><span data-stu-id="bc209-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="bc209-121">Mises à niveau sur place</span><span class="sxs-lookup"><span data-stu-id="bc209-121">In-place upgrades</span></span> 

<span data-ttu-id="bc209-122">Les mises à niveau sur place étaient disponibles dans Skype entreprise Server 2015, mais ne sont plus prises en charge dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bc209-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="bc209-123">La mise à niveau et la coexistence côte à côte sont prises en charge, reportez-vous [à migration vers Skype entreprise Server 2019](migration/migration-to-skype-for-business-server-2019.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="bc209-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="bc209-124">Service de mobilité (MCX)</span><span class="sxs-lookup"><span data-stu-id="bc209-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="bc209-125">La prise en charge du service de mobilité utilisée par les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bc209-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="bc209-126">Il a été précédemment annoncé dans Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bc209-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="bc209-127">Tous les clients mobiles Skype entreprise actuels utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="bc209-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="bc209-128">Les utilisateurs avec des clients hérités qui utilisent MCX devront effectuer une mise à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="bc209-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="bc209-129">Pour plus d’informations, reportez-vous à la rubrique [plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) et [mobile client Feature Comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span><span class="sxs-lookup"><span data-stu-id="bc209-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="bc209-130">Outils</span><span class="sxs-lookup"><span data-stu-id="bc209-130">Tools</span></span>

<span data-ttu-id="bc209-131">Les outils suivants ne peuvent pas être utilisés lors de la publication initiale de Skype entreprise Server 2019 :</span><span class="sxs-lookup"><span data-stu-id="bc209-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="bc209-132">Calculatrice de planification de la capacité de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bc209-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="bc209-133">Outils de débogage Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bc209-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="bc209-134">Outils du kit de ressources Skype entreprise Server (certains outils seront supprimés)</span><span class="sxs-lookup"><span data-stu-id="bc209-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="bc209-135">Appeler Parkometer</span><span class="sxs-lookup"><span data-stu-id="bc209-135">Call Parkometer</span></span>
    - <span data-ttu-id="bc209-136">Console utilisateur de recherche</span><span class="sxs-lookup"><span data-stu-id="bc209-136">Lookup user console</span></span>
    - <span data-ttu-id="bc209-137">Migration des annonces de numéros non attribués</span><span class="sxs-lookup"><span data-stu-id="bc209-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="bc209-138">Les outils suivants ne sont pas pris en charge avec Skype entreprise Server 2019 :</span><span class="sxs-lookup"><span data-stu-id="bc209-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="bc209-139">Méthodologie de qualité des appels (mais pas tableau de bord de qualité des appels)</span><span class="sxs-lookup"><span data-stu-id="bc209-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="bc209-140">Carte de performance de méthodologie de qualité des appels Microsoft, v 1.5</span><span class="sxs-lookup"><span data-stu-id="bc209-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="bc209-141">Outil de planification de Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="bc209-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="bc209-142">Outil de contrainte et de performances de Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="bc209-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="bc209-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bc209-143">See also</span></span>

[<span data-ttu-id="bc209-144">Nouveautés de Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="bc209-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="bc209-145">Migration de la Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="bc209-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
