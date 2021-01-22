---
title: Étude de cas Teams voix Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Étude de cas Voix Teams pour une entreprise multinationale
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6ee08fa7bdeb1ded6bda384115a08048021cb67
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918730"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="0899e-103">Étude de cas Contoso : attendants automatiques et files d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="0899e-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="0899e-104">Contoso était familiarisé avec les attendants automatiques et les files d’attente d’appels à partir de leur déploiement Skype Entreprise local.</span><span class="sxs-lookup"><span data-stu-id="0899e-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="0899e-105">Pour comprendre comment configurer les attendants automatiques cloud et les files d’attente d’appels, ils ont examiné le plan des files d’attente et des files d’attente [automatiques de Teams.](plan-auto-attendant-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="0899e-105">To understand how to set up Cloud auto attendants and call queues, they reviewed [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md).</span></span>

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="0899e-106">Conditions requises en fonction du type de site</span><span class="sxs-lookup"><span data-stu-id="0899e-106">Requirements depending on site type</span></span>

<span data-ttu-id="0899e-107">Selon le type de site, Contoso avait les besoins suivants :</span><span class="sxs-lookup"><span data-stu-id="0899e-107">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="0899e-108">Type de site A : systèmes de téléphonie hérités traditionnels</span><span class="sxs-lookup"><span data-stu-id="0899e-108">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="0899e-109">Le type de site A est nécessaire pour conserver le même numéro de téléphone associé au numéro de téléphone que le numéro de téléphone de son personnel de réception.</span><span class="sxs-lookup"><span data-stu-id="0899e-109">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="0899e-110">Les départements clés pour chacun de ces sites ont leurs propres files d’attente d’appels qui sont acheminées vers les membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="0899e-110">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="0899e-111">Il y avait un mélange de sites qui utilisaient Phone System avec routage direct et Phone System avec des plans d’appels.</span><span class="sxs-lookup"><span data-stu-id="0899e-111">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="0899e-112">Type de site B : skype entreprise Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="0899e-112">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="0899e-113">Le type de site B avait des files d’attente et des files d’attente automatiques existantes qui devaient être migrées vers Teams.</span><span class="sxs-lookup"><span data-stu-id="0899e-113">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="0899e-114">Contoso devait conserver les numéros de téléphone associés aux travailleurs automatiques.</span><span class="sxs-lookup"><span data-stu-id="0899e-114">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="0899e-115">Contoso a déplacé la plupart de ces sites vers Phone System avec des forfaits d’appels.</span><span class="sxs-lookup"><span data-stu-id="0899e-115">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="0899e-116">Toutefois, aux emplacements où les plans d’appel n’étaient pas disponibles, Contoso a déplacé ces sites vers une configuration de routage direct.</span><span class="sxs-lookup"><span data-stu-id="0899e-116">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="0899e-117">Type de site C : Skype Voix Entreprise & système de téléphonie hérité traditionnel</span><span class="sxs-lookup"><span data-stu-id="0899e-117">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="0899e-118">Le type de site C existait des attendants automatiques résidant dans le système de téléphonie hérité traditionnel.</span><span class="sxs-lookup"><span data-stu-id="0899e-118">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="0899e-119">Les décisions et configurations de ce site étaient identiques au type de site A.</span><span class="sxs-lookup"><span data-stu-id="0899e-119">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="0899e-120">Pour tous les types de sites, Contoso a posé les questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="0899e-120">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="0899e-121">Q : Allons-nous utiliser des numéros nouveaux ou existants ?</span><span class="sxs-lookup"><span data-stu-id="0899e-121">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="0899e-122">R : Contoso a décidé d’utiliser des numéros de téléphone existants pour être affectés au compte de service du attendant automatique.</span><span class="sxs-lookup"><span data-stu-id="0899e-122">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="0899e-123">Q : Quand le attendant automatique sera-t-il disponible pour accepter les appels entrants ?</span><span class="sxs-lookup"><span data-stu-id="0899e-123">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="0899e-124">R : Contoso a décidé de définir les heures d’ouverture et de recevoir les appels reçus après les heures d’ouverture vers un attendant automatique « après les heures de travail ».</span><span class="sxs-lookup"><span data-stu-id="0899e-124">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="0899e-125">Q : Comment les appels sont-ils acheminés aux membres d’une file d’attente d’appels : employé de service, série ou round routage ?</span><span class="sxs-lookup"><span data-stu-id="0899e-125">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="0899e-126">R : Contoso a décidé d’utiliser le routage Attendant,</span><span class="sxs-lookup"><span data-stu-id="0899e-126">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="0899e-127">Q : Comment allons-nous déterminer quand un utilisateur doit ou non se faire appeler ?</span><span class="sxs-lookup"><span data-stu-id="0899e-127">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="0899e-128">R : Contoso a décidé d’utiliser les options de traitement des appels pour déterminer si l’agent est disponible : routage en fonction de la présence.</span><span class="sxs-lookup"><span data-stu-id="0899e-128">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="0899e-129">Configuration</span><span class="sxs-lookup"><span data-stu-id="0899e-129">Configuration</span></span>

<span data-ttu-id="0899e-130">Les étapes à suivre pour configurer un attendant automatique et une file d’attente d’appels incluent les étapes [suivantes décrites](manage-resource-accounts.md)dans la liste Gérer les comptes de ressources :</span><span class="sxs-lookup"><span data-stu-id="0899e-130">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="0899e-131">Obtenez un numéro de service.</span><span class="sxs-lookup"><span data-stu-id="0899e-131">Obtain a service number.</span></span> 

2. <span data-ttu-id="0899e-132">Obtenez un système téléphonique gratuit - licence Utilisateur virtuel ou licence Système téléphonique payant à utiliser avec le compte de ressource ou une licence Système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="0899e-132">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="0899e-133">Créez le compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="0899e-133">Create the resource account.</span></span> <span data-ttu-id="0899e-134">Un responsable automatique ou une file d’attente d’appels est requis pour avoir un compte de ressource associé.</span><span class="sxs-lookup"><span data-stu-id="0899e-134">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="0899e-135">Affecter le système téléphonique ou un système téléphonique - Licence utilisateur virtuel au compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="0899e-135">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="0899e-136">Pour plus d’informations, [voir Microsoft 365 Phone System – Licence utilisateur virtuel.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)</span><span class="sxs-lookup"><span data-stu-id="0899e-136">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="0899e-137">Affectez un numéro de téléphone de service au compte de ressource que vous avez affecté aux licences.</span><span class="sxs-lookup"><span data-stu-id="0899e-137">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="0899e-138">Créer une file d’attente ou un attendant automatique du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="0899e-138">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="0899e-139">Lier le compte de ressource à une file d’attente d’appels ou un attendant automatique.</span><span class="sxs-lookup"><span data-stu-id="0899e-139">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="0899e-140">Sites avec système téléphonique avec routage direct</span><span class="sxs-lookup"><span data-stu-id="0899e-140">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="0899e-141">Contoso a dû configurer le numéro de téléphone fourni par l’opérateur local comme numéro de service dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="0899e-141">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="0899e-142">Pour configurer un numéro de téléphone disponible via le routage direct, Contoso a suivi les instructions situées dans Gérer les [comptes de ressources.](manage-resource-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="0899e-142">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="0899e-143">Étant donné qu’Office 365 n’a pas connaissance des numéros de téléphone locaux, Contoso a utilisé PowerShell pour terminer l’installation.</span><span class="sxs-lookup"><span data-stu-id="0899e-143">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="0899e-144">Pour configurer le attendant automatique cloud, Contoso a suivi les étapes décrites dans [La configuration d’un attendant automatique cloud.](create-a-phone-system-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="0899e-144">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="0899e-145">Pour configurer une file d’attente d’appels cloud, Contoso a suivi les étapes décrites dans créer une file d’attente [d’appels cloud.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="0899e-145">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="0899e-146">Sites avec système téléphonique avec forfait d’appels</span><span class="sxs-lookup"><span data-stu-id="0899e-146">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="0899e-147">Contoso a dû porter le numéro de téléphone utilisé pour les Voix Entreprise automatiques Skype Entreprise vers Office 365 Phone System.</span><span class="sxs-lookup"><span data-stu-id="0899e-147">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="0899e-148">Cela permettait d’attribuer le même numéro en tant que numéro de service à un employé de service automatique.</span><span class="sxs-lookup"><span data-stu-id="0899e-148">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="0899e-149">Pour transférer le numéro de téléphone, Contoso a suivi les instructions de transfert des numéros de téléphone vers [Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) et a obtenu des instructions supplémentaires sur la gestion des numéros de téléphone [pour votre organisation.](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="0899e-149">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="0899e-150">Pour configurer un attendant automatique cloud, Contoso a suivi les étapes décrites dans [La configuration d’un attendant automatique cloud.](create-a-phone-system-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="0899e-150">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="0899e-151">Pour configurer une file d’attente d’appels cloud, Contoso a suivi les étapes décrites dans créer une file d’attente [d’appels cloud.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="0899e-151">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 