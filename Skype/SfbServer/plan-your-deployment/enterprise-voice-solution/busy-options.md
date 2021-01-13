---
title: Planifier les options Busy pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Découvrez la fonctionnalité Busy Options dans Skype Entreprise Server.
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813694"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="02b5c-103">Planifier les options Busy pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="02b5c-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="02b5c-104">Découvrez la fonctionnalité Busy Options dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="02b5c-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="02b5c-105">Busy Options est une nouvelle stratégie de voix introduite dans la mise à jour cumulative de juillet 2016 qui vous permet de configurer la façon dont les appels entrants sont gérés lorsqu’un utilisateur est déjà en cours d’appel ou de conférence, ou qu’un appel est mis en attente.</span><span class="sxs-lookup"><span data-stu-id="02b5c-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="02b5c-106">Les appels nouveaux ou entrants peuvent être rejetés avec une signal occupé ou transmis à la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="02b5c-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="02b5c-107">La stratégie Busy Options est prise en charge pour leover et la récupération d’urgence sur les pools frontaux couplés et les serveurs Survivable Branch Servers (SBS).</span><span class="sxs-lookup"><span data-stu-id="02b5c-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="02b5c-108">Cette rubrique décrit les fonctionnalités de Busy Options.</span><span class="sxs-lookup"><span data-stu-id="02b5c-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="02b5c-109">Pour plus d’informations sur l’installation et la configuration de Busy Options, voir [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="02b5c-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="02b5c-110">Options de configuration</span><span class="sxs-lookup"><span data-stu-id="02b5c-110">Configuration options</span></span>

<span data-ttu-id="02b5c-111">Si Busy Options est activée pour l’organisation, tous les utilisateurs de votre organisation, les utilisateurs Voix Entreprise et non Voix Entreprise, peuvent utiliser les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="02b5c-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="02b5c-112">Occupé (occupé) : les nouveaux appels entrants sont rejetés avec une signal occupé si l’utilisateur est occupé.</span><span class="sxs-lookup"><span data-stu-id="02b5c-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="02b5c-113">Messagerie vocale sur Busy : dans laquelle les nouveaux appels entrants sont transmis à la messagerie vocale si l’utilisateur est occupé.</span><span class="sxs-lookup"><span data-stu-id="02b5c-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="02b5c-114">La fonctionnalité Busy Options offre une fonctionnalité deover.</span><span class="sxs-lookup"><span data-stu-id="02b5c-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="02b5c-115">Si un problème se produit et que les utilisateurs reviennent vers un autre serveur frontal ou vers un autre pool dans Skype Entreprise Server, leurs paramètres Busy Options sont conservés.</span><span class="sxs-lookup"><span data-stu-id="02b5c-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="02b5c-116">Quelle que soit la façon dont les options de occupé(s) sont configurées, les utilisateurs d’un appel ou d’une conférence, ou ceux qui ont un appel en attente, ne sont pas empêchés de lancer de nouveaux appels ou conférences.</span><span class="sxs-lookup"><span data-stu-id="02b5c-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="02b5c-117">Après la configuration, le paramètre Busy Options est en vigueur pour tous les clients et périphériques d’appel Skype Entreprise de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="02b5c-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="02b5c-118">En fonction des paramètres Busy Options de l’utilisateur, l’appel rejeté ou envoyé à la messagerie vocale ne sonne pas sur les périphériques d’appel de l’utilisateur (y compris Macintosh, Windows Desktop, clients mobiles ou téléphones IP) sur lesquels l’utilisateur est connecté.</span><span class="sxs-lookup"><span data-stu-id="02b5c-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="02b5c-119">Les utilisateurs voient les notifications d’appels manqués sur leurs clients et appareils Skype Entreprise, et ils sont également avertis par courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="02b5c-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="02b5c-120">Les appelants dont l’appel a été rejeté en raison de Busy on Busy voient une notification dans leur client Skype Entreprise indiquant que l’utilisateur qu’ils ont tenté de joindre est occupé sur un autre appel.</span><span class="sxs-lookup"><span data-stu-id="02b5c-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="02b5c-121">Vous pouvez configurer la fonctionnalité Busy Options à l’aide des cmdlets PowerShell Skype Entreprise pour :</span><span class="sxs-lookup"><span data-stu-id="02b5c-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="02b5c-122">Activez ou désactivez la stratégie Busy Options Voice pour l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="02b5c-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="02b5c-123">Administrer Busy on Busy ou Voicemail on Busy pour tous les utilisateurs de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="02b5c-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="02b5c-124">Administrer Busy on Busy ou Voicemail on Busy pour tous les utilisateurs d’un pool frontal particulier.</span><span class="sxs-lookup"><span data-stu-id="02b5c-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="02b5c-125">Administrer Busy on Busy ou Voicemail on Busy pour obtenir la liste des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="02b5c-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="02b5c-126">Administrer Busy on Busy ou Voicemail on Busy pour un seul utilisateur.</span><span class="sxs-lookup"><span data-stu-id="02b5c-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="02b5c-127">Interopérabilité avec les applications vocales</span><span class="sxs-lookup"><span data-stu-id="02b5c-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="02b5c-128">Busy Options offre une interopérabilité avec les applications vocales suivantes dans Skype Entreprise :</span><span class="sxs-lookup"><span data-stu-id="02b5c-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="02b5c-129">Response Groups (RGS)</span><span class="sxs-lookup"><span data-stu-id="02b5c-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="02b5c-130">Les options Busy définies sur les numéros Response Group seront ignorées par le système . plusieurs appels simultanés seront autorisés.</span><span class="sxs-lookup"><span data-stu-id="02b5c-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="02b5c-131">L’expérience actuelle de routage attendant dans Response Groups reste inchangée pour les agents avec les paramètres Busy Options.</span><span class="sxs-lookup"><span data-stu-id="02b5c-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="02b5c-132">Les appels provenant de Response Groups vers les utilisateurs qui sont des agents Response Groups ne seront pas limitées par les paramètres Busy Options et l’expérience RGS actuelle sera conservée.</span><span class="sxs-lookup"><span data-stu-id="02b5c-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="02b5c-133">Les appels non liés à RGS aux agents seront honorés par leurs paramètres Busy Options.</span><span class="sxs-lookup"><span data-stu-id="02b5c-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="02b5c-134">Appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="02b5c-134">Team Call</span></span>
    
  - <span data-ttu-id="02b5c-135">Les appels entrants aux utilisateurs qui sont configurer pour un appel d’équipe seront classés par ordre de priorité pour ignorer les paramètres Busy on Busy et Voicemail on Busy.</span><span class="sxs-lookup"><span data-stu-id="02b5c-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="02b5c-136">L’expérience actuelle de l’appel d’équipe reste inchangée avec busy options définies pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="02b5c-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="02b5c-137">Les appels non liés à l’appel d’équipe à ces utilisateurs seront honorés par leurs paramètres Busy Options.</span><span class="sxs-lookup"><span data-stu-id="02b5c-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="02b5c-138">Délégation de chef/administrateur</span><span class="sxs-lookup"><span data-stu-id="02b5c-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="02b5c-139">Les appels entrants aux utilisateurs qui sont configurer pour une délégation de responsable/d’administration en tant que responsable ou administrateur seront hiérarchisés pour ignorer les paramètres Busy on Busy et Voicemail on Busy.</span><span class="sxs-lookup"><span data-stu-id="02b5c-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="02b5c-140">L’expérience actuelle de délégation de responsable/administrateur reste inchangée avec busy options définies pour les administrateurs ou les responsables.</span><span class="sxs-lookup"><span data-stu-id="02b5c-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="02b5c-141">Les appels non associés à la délégation d’administrateur/non-chef aux administrateurs seront honorés par leurs paramètres Busy Options.</span><span class="sxs-lookup"><span data-stu-id="02b5c-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="02b5c-142">Mode partage de lignes</span><span class="sxs-lookup"><span data-stu-id="02b5c-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="02b5c-143">Les paramètres Busy Options sur les comptes d’utilisateurs qui sont configurer pour l’apparence de ligne partagée sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="02b5c-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="02b5c-144">Les options Busy on Busy et Voicemail on Busy natives de l’apparence de ligne partagée seront honorées à la place.</span><span class="sxs-lookup"><span data-stu-id="02b5c-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="02b5c-145">Service de parc public d’appel</span><span class="sxs-lookup"><span data-stu-id="02b5c-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="02b5c-146">Les appels par parcés qui n’ont pas été récupérés et qui sonnent en raison du délai d’arrêt seront autorisés à sonner pour l’utilisateur qui a par parcé l’appel par busy options.</span><span class="sxs-lookup"><span data-stu-id="02b5c-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="02b5c-147">Conférence téléphonique</span><span class="sxs-lookup"><span data-stu-id="02b5c-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="02b5c-148">Les utilisateurs des appels de conférence sont considérés comme occupés et les nouveaux appels entrants sont rejetés avec une signal occupé ou transmis à la messagerie vocale en fonction de leurs paramètres Busy Options.</span><span class="sxs-lookup"><span data-stu-id="02b5c-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="02b5c-149">Les utilisateurs des conférences ne sont pas empêchés de lancer de nouveaux appels ou conférences par Busy Options.</span><span class="sxs-lookup"><span data-stu-id="02b5c-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="02b5c-150">Les utilisateurs des conférences peuvent toujours recevoir de nouvelles invitations aux conférences, mais les nouveaux appels d’égal à égal seront rejetés en fonction de leurs paramètres Busy Options.</span><span class="sxs-lookup"><span data-stu-id="02b5c-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="02b5c-151">Sonnerie simultanée et forwarding d’appel</span><span class="sxs-lookup"><span data-stu-id="02b5c-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="02b5c-152">La fonctionnalité Busy on Busy n’est pas conçue pour fonctionner avec la sonnerie simultanée et le forwarding d’appel.</span><span class="sxs-lookup"><span data-stu-id="02b5c-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

