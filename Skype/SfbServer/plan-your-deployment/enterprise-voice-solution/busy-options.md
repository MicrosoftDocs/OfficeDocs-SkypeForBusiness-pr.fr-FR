---
title: Planifier les options Occupé pour Skype Entreprise Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: En savoir plus sur la fonctionnalité de disponibilité dans Skype pour Business Server.
ms.openlocfilehash: 41e34dbb4eaf4a264ba1cec3756cc53c78992611
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897976"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="f2ef9-103">Planifier les options Occupé pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f2ef9-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="f2ef9-104">En savoir plus sur la fonctionnalité de disponibilité dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="f2ef9-105">Busy Options est une nouvelle stratégie de voix de la mise à jour cumulative de juillet 2016, qui vous permet de configurer la manière dont les appels entrants sont gérés lorsqu'un utilisateur participe déjà à un appel ou à une conférence, ou lorsqu'il a mis un appel en attente.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="f2ef9-106">Les nouveaux appels ou les appels entrants peuvent être rejetés avec une tonalité d’occupation ou sont transférés vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="f2ef9-107">La stratégie Busy Options est prise en charge pour le basculement et la récupération d’urgence sur les pools frontaux associés et les serveurs Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="f2ef9-108">Cette rubrique décrit la fonctionnalité Busy Options.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="f2ef9-109">Pour savoir comment installer et configurer la fonctionnalité Busy Options, reportez-vous à [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="f2ef9-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="f2ef9-110">Options de configuration</span><span class="sxs-lookup"><span data-stu-id="f2ef9-110">Configuration options</span></span>

<span data-ttu-id="f2ef9-111">Si Busy Options est activée pour l'organisation, l'ensemble des utilisateurs de votre organisation, qu'il s'agisse des utilisateurs de Voix Entreprise ou non, peuvent utiliser les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="f2ef9-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="f2ef9-112">Busy on Busy : les nouveaux appels entrants seront rejetés avec une tonalité d’occupation si l'utilisateur est occupé.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="f2ef9-113">Voicemail on Busy : les nouveaux appels entrants seront transférés vers la messagerie si l'utilisateur est occupé.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="f2ef9-114">La fonctionnalité Busy Option fournit une capacité de basculement.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="f2ef9-115">Si un problème se produit et les utilisateurs basculement vers un autre serveur frontal ou vers un autre pool dans Skype pour Business Server, leurs paramètres Options occupé (e) seront préservées.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="f2ef9-116">Quelle que soit la manière dont ils ont configuré Busy Option, les utilisateurs participant à un appel ou une conférence, ou ceux ayant mis un appel en absence, peuvent toujours lancer de nouveaux appels ou de nouvelles conférences.  </span><span class="sxs-lookup"><span data-stu-id="f2ef9-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="f2ef9-117">Après la configuration, le paramètre Options occupé (e) est en vigueur pour Skype de tous les utilisateurs pour les clients et périphériques d’appel Business.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="f2ef9-118">En fonction des paramètres de la fonctionnalité Busy Option des utilisateurs, la sonnerie de l'appel qui est rejeté ou transféré vers la messagerie vocale ne retentira pas sur le dispositif d'appel de l'utilisateur (que ce soit Macintosh, Bureau Windows, clients mobiles ou téléphones IP) sur lequel il est connecté.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="f2ef9-119">Les utilisateurs verront les notifications d’appels manqués sur leur Skype pour les clients professionnels et les appareils, et ils seront avertis par courrier électronique ainsi que.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="f2ef9-120">Une notification s'affichera sur le client Skype Entreprise des appelants dont l'appel a été rejeté en raison du statut Busy on Busy, les informant que l'utilisateur qu'ils ont tenté de joindre est déjà en communication.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="f2ef9-121">Vous pouvez configurer la fonctionnalité de disponibilité à l’aide de Skype pour les applets de commande PowerShell de l’entreprise :</span><span class="sxs-lookup"><span data-stu-id="f2ef9-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="f2ef9-122">Activer ou désactiver la stratégie de voix Busy Options pour l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="f2ef9-123">Administrer le statut Busy on Busy ou Voicemail on Busy pour l'ensemble des utilisateurs de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="f2ef9-124">Administrer le statut Busy on Busy ou Voicemail on Busy pour l'ensemble des utilisateurs hébergés sur un pool frontal spécifique.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="f2ef9-125">Administrer le statut Busy on Busy ou Voicemail on Busy pour une liste d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="f2ef9-126">Administrer le statut Busy on Busy ou Voicemail on Busy pour un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="f2ef9-127">Interopérabilité avec les applications Voix</span><span class="sxs-lookup"><span data-stu-id="f2ef9-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="f2ef9-128">Options de disponibilité fournit une interopérabilité avec les applications vocales suivantes dans Skype pour les entreprises :</span><span class="sxs-lookup"><span data-stu-id="f2ef9-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="f2ef9-129">Response Groups (RGS)</span><span class="sxs-lookup"><span data-stu-id="f2ef9-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="f2ef9-130">La fonctionnalité Busy Options définie sur les chiffres Response Group sera ignorée par le système ; plusieurs appels simultanés seront autorisés. </span><span class="sxs-lookup"><span data-stu-id="f2ef9-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="f2ef9-131">L'expérience actuelle de routage des participants dans Response Groups restera inchangée pour les agents avec les paramètres Busy Options.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="f2ef9-132">Les appels provenant de Response Groups à destination des utilisateurs qui sont des agents Response Groups ne seront pas limités par les paramètres Busy Options et l'expérience RGS actuelle sera maintenue.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="f2ef9-133">Les appels non associés à RGS vers les agents seront honorés par leurs paramètres Busy Options.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="f2ef9-134">Appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="f2ef9-134">Team Call</span></span>
    
  - <span data-ttu-id="f2ef9-135">Les appels entrants vers les utilisateurs qui sont définies pour un appel d’équipe seront prioritaires pour ignorer occupé (e) sur occupé (e) et la messagerie vocale sur les paramètres occupé (e).</span><span class="sxs-lookup"><span data-stu-id="f2ef9-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="f2ef9-136">L'expérience actuelle de l'appel d'équipe restera inchangée avec la fonctionnalité Busy Options définie pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="f2ef9-137">Les appels non associés à l'appel d'équipe vers les agents seront honorés par leurs paramètres Busy Options.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="f2ef9-138">Délégation patron/administrateur </span><span class="sxs-lookup"><span data-stu-id="f2ef9-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="f2ef9-139">Les appels entrants vers les utilisateurs qui sont configurés pour une délégation/administration du responsable soit en tant que directeur ou un administrateur qui seront prioritaires pour ignorer occupé (e) sur occupé (e) et la messagerie vocale sur les paramètres occupé (e).</span><span class="sxs-lookup"><span data-stu-id="f2ef9-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="f2ef9-140">L'expérience actuelle de délégation patron/administrateur restera inchangée avec la fonctionnalité Busy Options définie pour les administrateurs ou les patrons.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="f2ef9-141">Les appels non associés à la délégation patron/administrateur vers les administrateurs seront honorés par leurs paramètres Busy Options.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="f2ef9-142">Mode partage de lignes   </span><span class="sxs-lookup"><span data-stu-id="f2ef9-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="f2ef9-143">Les paramètres Busy Options sur les comptes d'utilisateur configurés pour le mode partage de ligne seront ignorés. </span><span class="sxs-lookup"><span data-stu-id="f2ef9-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="f2ef9-144">Informations de disponibilité native de partagé apparence de la ligne sur occupé (e) et la messagerie vocale sur les options de disponibilité sont honorées à la place.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="f2ef9-145">Service de parcage des appels </span><span class="sxs-lookup"><span data-stu-id="f2ef9-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="f2ef9-146">Les appels parqués qui n'ont pas été extraits et qui sont émis de nouveau en raison de l'expiration du délai d'attente seront émis systématiquement vers l'utilisateur qui a parqué l'appel via la fonctionnalité Busy Options. </span><span class="sxs-lookup"><span data-stu-id="f2ef9-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="f2ef9-147">Conférence téléphonique</span><span class="sxs-lookup"><span data-stu-id="f2ef9-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="f2ef9-148">Les utilisateurs qui participent à une conférence téléphonique sont considérés comme occupés et les nouveaux appels entrants sont rejetés avec une tonalité d’occupation ou transférés vers la messagerie vocale en fonction des paramètres définis pour Busy Options.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="f2ef9-149">Les utilisateurs qui participent à une conférence peuvent toujours démarrer de nouveaux appels ou de nouvelles conférences via la fonctionnalité Busy Options.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="f2ef9-150">Les utilisateurs qui participent à une conférence peuvent toujours recevoir des invitations pour participer à de nouvelles conférences, mais les nouveaux appels d’égal à égal seront rejetés en fonction des paramètres définis pour Busy Options.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="f2ef9-151">Sonnerie simultanée et transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="f2ef9-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="f2ef9-152">La fonctionnalité Busy on Busy n’est pas conçue pour fonctionner avec la sonnerie simultanée et le transfert d’appel.</span><span class="sxs-lookup"><span data-stu-id="f2ef9-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

