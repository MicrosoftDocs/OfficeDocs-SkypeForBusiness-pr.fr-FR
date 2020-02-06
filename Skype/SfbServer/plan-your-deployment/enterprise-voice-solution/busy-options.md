---
title: Planifier les options Occupé pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: En savoir plus sur la fonctionnalité options occupées dans Skype entreprise Server.
ms.openlocfilehash: cf9ee9dbb3785804b1bb63f4118a29d29cf7715c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803244"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="60fdf-103">Planifier les options Occupé pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="60fdf-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="60fdf-104">En savoir plus sur la fonctionnalité options occupées dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="60fdf-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="60fdf-105">Busy Options est une nouvelle stratégie de voix de la mise à jour cumulative de juillet 2016, qui vous permet de configurer la manière dont les appels entrants sont gérés lorsqu'un utilisateur participe déjà à un appel ou à une conférence, ou lorsqu'il a mis un appel en attente.</span><span class="sxs-lookup"><span data-stu-id="60fdf-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="60fdf-106">Les nouveaux appels ou les appels entrants peuvent être rejetés avec une tonalité d’occupation ou sont transférés vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="60fdf-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="60fdf-107">La stratégie Busy Options est prise en charge pour le basculement et la récupération d’urgence sur les pools frontaux associés et les serveurs Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="60fdf-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="60fdf-108">Cette rubrique décrit la fonctionnalité Busy Options.</span><span class="sxs-lookup"><span data-stu-id="60fdf-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="60fdf-109">Pour savoir comment installer et configurer la fonctionnalité Busy Options, reportez-vous à [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="60fdf-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="60fdf-110">Options de configuration</span><span class="sxs-lookup"><span data-stu-id="60fdf-110">Configuration options</span></span>

<span data-ttu-id="60fdf-111">Si Busy Options est activée pour l'organisation, l'ensemble des utilisateurs de votre organisation, qu'il s'agisse des utilisateurs de Voix Entreprise ou non, peuvent utiliser les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="60fdf-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="60fdf-112">Busy on Busy : les nouveaux appels entrants seront rejetés avec une tonalité d’occupation si l'utilisateur est occupé.</span><span class="sxs-lookup"><span data-stu-id="60fdf-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="60fdf-113">Voicemail on Busy : les nouveaux appels entrants seront transférés vers la messagerie si l'utilisateur est occupé.</span><span class="sxs-lookup"><span data-stu-id="60fdf-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="60fdf-114">La fonctionnalité Busy Option fournit une capacité de basculement.</span><span class="sxs-lookup"><span data-stu-id="60fdf-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="60fdf-115">Dans le cas où un problème se produit et que les utilisateurs basculent vers un autre serveur frontal ou vers un autre pool dans Skype entreprise Server, leurs paramètres d’options occupés seront conservés.</span><span class="sxs-lookup"><span data-stu-id="60fdf-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="60fdf-116">Quelle que soit la manière dont ils ont configuré Busy Option, les utilisateurs participant à un appel ou une conférence, ou ceux ayant mis un appel en absence, peuvent toujours lancer de nouveaux appels ou de nouvelles conférences.  </span><span class="sxs-lookup"><span data-stu-id="60fdf-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="60fdf-117">Après la configuration, le paramètre options de disponibilité est activé pour tous les appareils et clients de l’utilisateur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="60fdf-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="60fdf-118">En fonction des paramètres de la fonctionnalité Busy Option des utilisateurs, la sonnerie de l'appel qui est rejeté ou transféré vers la messagerie vocale ne retentira pas sur le dispositif d'appel de l'utilisateur (que ce soit Macintosh, Bureau Windows, clients mobiles ou téléphones IP) sur lequel il est connecté.</span><span class="sxs-lookup"><span data-stu-id="60fdf-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="60fdf-119">Les utilisateurs verront les notifications d’appel manqué sur leurs clients et appareils Skype entreprise et ils seront également avertis par e-mail.</span><span class="sxs-lookup"><span data-stu-id="60fdf-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="60fdf-120">Une notification s'affichera sur le client Skype Entreprise des appelants dont l'appel a été rejeté en raison du statut Busy on Busy, les informant que l'utilisateur qu'ils ont tenté de joindre est déjà en communication.</span><span class="sxs-lookup"><span data-stu-id="60fdf-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="60fdf-121">Vous pouvez configurer la fonctionnalité d’options occupées en utilisant les cmdlets PowerShell Skype entreprise pour :</span><span class="sxs-lookup"><span data-stu-id="60fdf-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="60fdf-122">Activer ou désactiver la stratégie de voix Busy Options pour l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="60fdf-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="60fdf-123">Administrer le statut Busy on Busy ou Voicemail on Busy pour l'ensemble des utilisateurs de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="60fdf-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="60fdf-124">Administrer le statut Busy on Busy ou Voicemail on Busy pour l'ensemble des utilisateurs hébergés sur un pool frontal spécifique.</span><span class="sxs-lookup"><span data-stu-id="60fdf-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="60fdf-125">Administrer le statut Busy on Busy ou Voicemail on Busy pour une liste d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="60fdf-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="60fdf-126">Administrer le statut Busy on Busy ou Voicemail on Busy pour un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="60fdf-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="60fdf-127">Interopérabilité avec les applications Voix</span><span class="sxs-lookup"><span data-stu-id="60fdf-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="60fdf-128">Les options occupées permettent l’interopérabilité avec les applications vocales suivantes dans Skype entreprise :</span><span class="sxs-lookup"><span data-stu-id="60fdf-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="60fdf-129">Response Groups (RGS)</span><span class="sxs-lookup"><span data-stu-id="60fdf-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="60fdf-130">La fonctionnalité Busy Options définie sur les chiffres Response Group sera ignorée par le système ; plusieurs appels simultanés seront autorisés. </span><span class="sxs-lookup"><span data-stu-id="60fdf-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="60fdf-131">L'expérience actuelle de routage des participants dans Response Groups restera inchangée pour les agents avec les paramètres Busy Options.</span><span class="sxs-lookup"><span data-stu-id="60fdf-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="60fdf-132">Les appels provenant de Response Groups à destination des utilisateurs qui sont des agents Response Groups ne seront pas limités par les paramètres Busy Options et l'expérience RGS actuelle sera maintenue.</span><span class="sxs-lookup"><span data-stu-id="60fdf-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="60fdf-133">Les appels non associés à RGS vers les agents seront honorés par leurs paramètres Busy Options.</span><span class="sxs-lookup"><span data-stu-id="60fdf-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="60fdf-134">Appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="60fdf-134">Team Call</span></span>
    
  - <span data-ttu-id="60fdf-135">Les appels entrants vers des utilisateurs qui sont configurés pour un appel d’équipe sont classés par ordre de priorité pour ignorer les valeurs occupées et les messages vocaux sur les paramètres occupés.</span><span class="sxs-lookup"><span data-stu-id="60fdf-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="60fdf-136">L'expérience actuelle de l'appel d'équipe restera inchangée avec la fonctionnalité Busy Options définie pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="60fdf-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="60fdf-137">Les appels non associés à l'appel d'équipe vers les agents seront honorés par leurs paramètres Busy Options.</span><span class="sxs-lookup"><span data-stu-id="60fdf-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="60fdf-138">Délégation patron/administrateur </span><span class="sxs-lookup"><span data-stu-id="60fdf-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="60fdf-139">Les appels entrants vers des utilisateurs qui sont configurés pour un responsable/une délégation d’administration, en tant que patron ou administrateur, sont classés par ordre de priorité pour ignorer les disponibilités et les messages vocaux sur les paramètres occupés.</span><span class="sxs-lookup"><span data-stu-id="60fdf-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="60fdf-140">L'expérience actuelle de délégation patron/administrateur restera inchangée avec la fonctionnalité Busy Options définie pour les administrateurs ou les patrons.</span><span class="sxs-lookup"><span data-stu-id="60fdf-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="60fdf-141">Les appels non associés à la délégation patron/administrateur vers les administrateurs seront honorés par leurs paramètres Busy Options.</span><span class="sxs-lookup"><span data-stu-id="60fdf-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="60fdf-142">Mode partage de lignes   </span><span class="sxs-lookup"><span data-stu-id="60fdf-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="60fdf-143">Les paramètres Busy Options sur les comptes d'utilisateur configurés pour le mode partage de ligne seront ignorés. </span><span class="sxs-lookup"><span data-stu-id="60fdf-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="60fdf-144">Le champ natif occupé de la ligne en fonction de la disponibilité et de la boîte vocale est accepté à la place.</span><span class="sxs-lookup"><span data-stu-id="60fdf-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="60fdf-145">Service de parcage des appels </span><span class="sxs-lookup"><span data-stu-id="60fdf-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="60fdf-146">Les appels parqués qui n'ont pas été extraits et qui sont émis de nouveau en raison de l'expiration du délai d'attente seront émis systématiquement vers l'utilisateur qui a parqué l'appel via la fonctionnalité Busy Options. </span><span class="sxs-lookup"><span data-stu-id="60fdf-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="60fdf-147">Conférence téléphonique</span><span class="sxs-lookup"><span data-stu-id="60fdf-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="60fdf-148">Les utilisateurs qui participent à une conférence téléphonique sont considérés comme occupés et les nouveaux appels entrants sont rejetés avec une tonalité d’occupation ou transférés vers la messagerie vocale en fonction des paramètres définis pour Busy Options.</span><span class="sxs-lookup"><span data-stu-id="60fdf-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="60fdf-149">Les utilisateurs qui participent à une conférence peuvent toujours démarrer de nouveaux appels ou de nouvelles conférences via la fonctionnalité Busy Options.</span><span class="sxs-lookup"><span data-stu-id="60fdf-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="60fdf-150">Les utilisateurs qui participent à une conférence peuvent toujours recevoir des invitations pour participer à de nouvelles conférences, mais les nouveaux appels d’égal à égal seront rejetés en fonction des paramètres définis pour Busy Options.</span><span class="sxs-lookup"><span data-stu-id="60fdf-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="60fdf-151">Sonnerie simultanée et transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="60fdf-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="60fdf-152">La fonctionnalité Busy on Busy n’est pas conçue pour fonctionner avec la sonnerie simultanée et le transfert d’appel.</span><span class="sxs-lookup"><span data-stu-id="60fdf-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

