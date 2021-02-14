---
title: What’s deprecated from Skype for Business Server 2019
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : Ces fonctionnalités ont été supprimées de Skype Entreprise Server 2019.'
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808724"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="e5a76-103">What’s deprecated from Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e5a76-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="e5a76-104">Découvrez les fonctionnalités qui sont dépréciées dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e5a76-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="e5a76-105">Pour plus d’informations sur les nouvelles fonctionnalités de Skype Entreprise Server 2019, voir [What’s in Skype for Business Server 2019](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="e5a76-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="e5a76-106">Certaines fonctionnalités de mise en avant sont incluses dans Skype Entreprise Server 2019 pour des raisons de compatibilité avec les versions précédentes du produit.</span><span class="sxs-lookup"><span data-stu-id="e5a76-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="e5a76-107">Fonctionnalités dépréciées dans Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="e5a76-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="e5a76-108">Passerelles XMPP pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e5a76-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="e5a76-109">Skype Entreprise Server 2015 et ses prédécesseurs vous ont permis de configurer un proxy XMPP (Extensible Messaging and Presence Protocol) sur le serveur Edge et une passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="e5a76-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="e5a76-110">Cette fonctionnalité n’est plus disponible dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e5a76-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="e5a76-111">Conversation permanente pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e5a76-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="e5a76-112">Le serveur de conversation permanente est un rôle facultatif qui permet à plusieurs utilisateurs de votre organisation de participer à des conversations de salle de conversation persistantes au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="e5a76-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="e5a76-113">La conversation permanente ne peut pas être déployée avec Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e5a76-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="e5a76-114">Ce rôle serveur est supprimé du Générateur de topologie, ainsi que du code.</span><span class="sxs-lookup"><span data-stu-id="e5a76-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="e5a76-115">La même fonctionnalité est disponible dans Teams.</span><span class="sxs-lookup"><span data-stu-id="e5a76-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="e5a76-116">Pour plus d’informations, voir [La mise à niveau de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="e5a76-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="e5a76-117">SQL miroir pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e5a76-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="e5a76-118">SQL la mise en miroir ne peut pas être déployée avec Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e5a76-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="e5a76-119">D’autres options de haute disponibilité et de récupération d’urgence sont toujours pris en charge et vous devez choisir parmi celles-ci.</span><span class="sxs-lookup"><span data-stu-id="e5a76-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="e5a76-120">Pour consulter les options, voir [Planifier la haute disponibilité et la récupération d’urgence](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e5a76-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="e5a76-121">Mises à niveau sur place</span><span class="sxs-lookup"><span data-stu-id="e5a76-121">In-place upgrades</span></span> 

<span data-ttu-id="e5a76-122">Les mises à niveau sur place étaient disponibles dans Skype Entreprise Server 2015, mais ne sont plus pris en charge dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e5a76-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e5a76-123">La mise à niveau et la coexistence côte à côte sont pris en charge. Pour plus d’informations, voir Migration vers Skype Entreprise [Server 2019.](migration/migration-to-skype-for-business-server-2019.md)</span><span class="sxs-lookup"><span data-stu-id="e5a76-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="e5a76-124">Mobility Service (Mcx)</span><span class="sxs-lookup"><span data-stu-id="e5a76-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="e5a76-125">La prise en charge du service de mobilité utilisée par les clients mobiles hérités n’est plus disponible dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e5a76-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e5a76-126">Cela a été annoncé précédemment dans Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e5a76-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="e5a76-127">Tous les clients mobiles Skype Entreprise actuels utilisent déjà l’API web de communications unifiées (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="e5a76-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e5a76-128">Les utilisateurs ayant des clients hérités utilisant Mcx devront mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="e5a76-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="e5a76-129">Pour plus d’informations, consultez la comparaison des fonctionnalités de client mobile et de plan de mobilité pour Skype [Entreprise](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) [Server.](../SfbServer/plan-your-deployment/mobility.md)</span><span class="sxs-lookup"><span data-stu-id="e5a76-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="e5a76-130">Outils</span><span class="sxs-lookup"><span data-stu-id="e5a76-130">Tools</span></span>

<span data-ttu-id="e5a76-131">Les outils suivants ne pourront pas être utilisés lors de la version initiale de Skype Entreprise Server 2019 :</span><span class="sxs-lookup"><span data-stu-id="e5a76-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="e5a76-132">Calculateur de planification de la capacité Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e5a76-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="e5a76-133">Outils de débogage Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e5a76-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="e5a76-134">Outils du Kit de ressources Skype Entreprise Server (certains outils seront supprimés)</span><span class="sxs-lookup"><span data-stu-id="e5a76-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="e5a76-135">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="e5a76-135">Call Parkometer</span></span>
    - <span data-ttu-id="e5a76-136">Console utilisateur de recherche</span><span class="sxs-lookup"><span data-stu-id="e5a76-136">Lookup user console</span></span>
    - <span data-ttu-id="e5a76-137">Migration d’annonces de numéro non signé</span><span class="sxs-lookup"><span data-stu-id="e5a76-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="e5a76-138">Les outils suivants ne sont pas pris en charge avec Skype Entreprise Server 2019 :</span><span class="sxs-lookup"><span data-stu-id="e5a76-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="e5a76-139">Méthodologie de qualité des appels (mais pas tableau de bord de qualité des appels)</span><span class="sxs-lookup"><span data-stu-id="e5a76-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="e5a76-140">Carte de performance de méthodologie de qualité des appels Microsoft, v1.5</span><span class="sxs-lookup"><span data-stu-id="e5a76-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="e5a76-141">Outil de planification Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="e5a76-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="e5a76-142">Outil Stress and Performance de Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="e5a76-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="e5a76-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e5a76-143">See also</span></span>

[<span data-ttu-id="e5a76-144">Nouveautés de Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="e5a76-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="e5a76-145">Migration de la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="e5a76-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
