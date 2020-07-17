---
title: Étude de cas de voix contoso teams
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
description: Étude de cas de voix dans teams pour les entreprises à plusieurs nationaux
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786021"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="8ca30-103">Étude de cas contoso : standards automatiques et files d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="8ca30-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="8ca30-104">Contoso s’est familier des standards automatiques et des files d’attente de son déploiement Skype entreprise local.</span><span class="sxs-lookup"><span data-stu-id="8ca30-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="8ca30-105">Pour savoir comment configurer les standards automatiques Cloud, ils ont examiné [ce que sont les standards automatiques Cloud ?](what-are-phone-system-auto-attendants.md) et [exemples petite entreprise-définir le didacticiel du standard automatique](tutorial-org-aa.yml).</span><span class="sxs-lookup"><span data-stu-id="8ca30-105">To understand how to set up Cloud auto attendants, they reviewed [What are Cloud auto attendants?](what-are-phone-system-auto-attendants.md) and [Small business  example - Set up auto attendant tutorial](tutorial-org-aa.yml).</span></span> <span data-ttu-id="8ca30-106">Pour en savoir plus sur les options disponibles pour la configuration de files d’attente d’appels, le réviseur de Contoso [a examiné une file d’attente d’appels Cloud](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="8ca30-106">To learn about the options available to set up call queues, Contoso reviewed [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="8ca30-107">Conditions requises en fonction du type de site</span><span class="sxs-lookup"><span data-stu-id="8ca30-107">Requirements depending on site type</span></span>

<span data-ttu-id="8ca30-108">En fonction du type de site, Contoso a-il besoin des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="8ca30-108">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="8ca30-109">Type de site A : systèmes de téléphonie traditionnels traditionnels</span><span class="sxs-lookup"><span data-stu-id="8ca30-109">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="8ca30-110">Site tapez A requis pour conserver le même numéro de téléphone associé à la réceptionniste en tant que numéro de ses standards automatiques.</span><span class="sxs-lookup"><span data-stu-id="8ca30-110">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="8ca30-111">Les services clés de chacun de ces sites disposeront de leurs propres files d’attente d’appels routables aux membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="8ca30-111">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="8ca30-112">Un mélange de sites utilisait un système téléphonique avec un routage direct et un système téléphonique avec des plans d’appels.</span><span class="sxs-lookup"><span data-stu-id="8ca30-112">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="8ca30-113">Type de site B : Skype entreprise voix entreprise</span><span class="sxs-lookup"><span data-stu-id="8ca30-113">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="8ca30-114">Le type de site B avait déjà des standards automatiques et des files d’attente d’appels pour migrer vers Teams.</span><span class="sxs-lookup"><span data-stu-id="8ca30-114">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="8ca30-115">Contoso a besoin de conserver les numéros de téléphone associés aux standards automatiques.</span><span class="sxs-lookup"><span data-stu-id="8ca30-115">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="8ca30-116">Contoso a déplacé la majorité de ces sites vers un système téléphonique avec des plans d’appels.</span><span class="sxs-lookup"><span data-stu-id="8ca30-116">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="8ca30-117">Néanmoins, dans les rares emplacements où les plans d’appel ne sont pas disponibles, Contoso a déplacé ces sites vers une configuration de routage directe.</span><span class="sxs-lookup"><span data-stu-id="8ca30-117">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="8ca30-118">Type de site C : voix entreprise Skype entreprise & système de téléphonie traditionnel traditionnel</span><span class="sxs-lookup"><span data-stu-id="8ca30-118">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="8ca30-119">Le type de site C avait déjà des standards automatiques qui résident dans le système de téléphonie classique.</span><span class="sxs-lookup"><span data-stu-id="8ca30-119">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="8ca30-120">Les décisions et configurations pour ce site étaient les mêmes que le type de site A.</span><span class="sxs-lookup"><span data-stu-id="8ca30-120">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="8ca30-121">Pour tous les types de sites, Contoso a posé les questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="8ca30-121">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="8ca30-122">Q : utiliserez-vous des numéros nouveaux ou existants ?</span><span class="sxs-lookup"><span data-stu-id="8ca30-122">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="8ca30-123">A : contoso a décidé d’utiliser des numéros de téléphone existants à attribuer au compte de service pour le standard automatique.</span><span class="sxs-lookup"><span data-stu-id="8ca30-123">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="8ca30-124">Q : quand le standard automatique sera-t-il disponible pour accepter les appels entrants ?</span><span class="sxs-lookup"><span data-stu-id="8ca30-124">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="8ca30-125">A : contoso a décidé de définir les heures d’activité et d’avoir reçu des appels lorsque les heures d’activité sont redirigées vers un standard automatique « après heures ».</span><span class="sxs-lookup"><span data-stu-id="8ca30-125">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="8ca30-126">Q : comment les appels sont-ils acheminés vers les membres d’une file d’attente d’appels : le standard, le routage de série ou le routage par répétition alternée ?</span><span class="sxs-lookup"><span data-stu-id="8ca30-126">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="8ca30-127">A : contoso a décidé d’utiliser le service de routage de l’assistance.</span><span class="sxs-lookup"><span data-stu-id="8ca30-127">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="8ca30-128">Q : Comment puis-je déterminer à quel moment un utilisateur doit ou ne doit pas être appelé ?</span><span class="sxs-lookup"><span data-stu-id="8ca30-128">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="8ca30-129">A : contoso a décidé d’utiliser les options de traitement des appels pour déterminer si l’agent est disponible : routage basé sur la présence.</span><span class="sxs-lookup"><span data-stu-id="8ca30-129">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="8ca30-130">Configuration</span><span class="sxs-lookup"><span data-stu-id="8ca30-130">Configuration</span></span>

<span data-ttu-id="8ca30-131">Pour configurer un standard automatique et une file d’attente d’appels, vous pouvez suivre les étapes décrites dans [gérer les comptes de ressources](manage-resource-accounts.md):</span><span class="sxs-lookup"><span data-stu-id="8ca30-131">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="8ca30-132">Obtenez un numéro de service.</span><span class="sxs-lookup"><span data-stu-id="8ca30-132">Obtain a service number.</span></span> 

2. <span data-ttu-id="8ca30-133">Procurez-vous un système téléphonique gratuit ou une licence de système téléphonique payant à utiliser avec le compte de ressources ou une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="8ca30-133">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="8ca30-134">Créez le compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="8ca30-134">Create the resource account.</span></span> <span data-ttu-id="8ca30-135">Un standard automatique ou une file d’attente d’appels doivent être associés à un compte de ressources associé.</span><span class="sxs-lookup"><span data-stu-id="8ca30-135">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="8ca30-136">Attribuez le système téléphonique ou un système téléphonique-licence utilisateur virtuel au compte de ressources.</span><span class="sxs-lookup"><span data-stu-id="8ca30-136">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="8ca30-137">Pour plus d’informations, reportez-vous à [la rubrique système téléphonique Microsoft 365-licence utilisateur virtuel](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span><span class="sxs-lookup"><span data-stu-id="8ca30-137">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="8ca30-138">Affectez un numéro de téléphone de service au compte de ressources auquel vous avez attribué des licences.</span><span class="sxs-lookup"><span data-stu-id="8ca30-138">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="8ca30-139">Créer une file d’attente des appels du système téléphonique ou un standard automatique</span><span class="sxs-lookup"><span data-stu-id="8ca30-139">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="8ca30-140">Liez le compte de ressource avec une file d’attente d’appels ou un standard automatique.</span><span class="sxs-lookup"><span data-stu-id="8ca30-140">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="8ca30-141">Sites avec système téléphonique avec routage direct</span><span class="sxs-lookup"><span data-stu-id="8ca30-141">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="8ca30-142">Contoso a créé le numéro de téléphone fourni par l’opérateur local en tant que numéro de service dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="8ca30-142">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="8ca30-143">Pour configurer un numéro de téléphone disponible via le routage direct, Contoso a suivi les instructions situées dans [gérer les comptes de ressources](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="8ca30-143">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="8ca30-144">Comme Office 365 ne connaît pas les numéros de téléphone locaux, Contoso a utilisé PowerShell pour terminer la configuration.</span><span class="sxs-lookup"><span data-stu-id="8ca30-144">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="8ca30-145">Pour configurer le standard automatique du Cloud, Contoso a suivi les étapes décrites dans l’article [configurer un standard automatique Cloud](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="8ca30-145">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="8ca30-146">Pour configurer une file d’attente d’appels Cloud, Contoso a suivi les étapes décrites dans la rubrique [créer une file d’attente d’appels Cloud](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="8ca30-146">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="8ca30-147">Sites avec système téléphonique avec un plan d’appels</span><span class="sxs-lookup"><span data-stu-id="8ca30-147">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="8ca30-148">Contoso a dû porter le numéro de téléphone utilisé pour les standards automatiques vocaux Skype entreprise vers un système téléphonique Office 365.</span><span class="sxs-lookup"><span data-stu-id="8ca30-148">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="8ca30-149">Le même numéro a été attribué en tant que numéro de service à utiliser comme standard automatique.</span><span class="sxs-lookup"><span data-stu-id="8ca30-149">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="8ca30-150">Pour porter le numéro de téléphone, Contoso a suivi les instructions contenues dans les sections [transférer les numéros de téléphone aux équipes](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) et obtenu des conseils supplémentaires sur [la gestion des numéros de téléphone pour votre organisation](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="8ca30-150">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="8ca30-151">Pour configurer un standard automatique Cloud, Contoso a suivi les étapes décrites dans l’article [configurer un standard automatique Cloud](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="8ca30-151">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="8ca30-152">Pour configurer une file d’attente d’appels Cloud, Contoso a suivi les étapes décrites dans la rubrique [créer une file d’attente d’appels Cloud](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="8ca30-152">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 