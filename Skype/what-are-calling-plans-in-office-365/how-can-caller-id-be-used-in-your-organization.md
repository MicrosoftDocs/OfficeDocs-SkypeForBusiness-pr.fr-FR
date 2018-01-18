---
title: "ID de l’appelant utilisation dans votre organisation"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "ID de l’appelant peut être contrôlée pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l’aide d’une stratégie nommée CallingLineIdentity."
ms.openlocfilehash: b9e889ae9d87277939e844eeb911834f466942c5
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="60e02-103">ID de l’appelant utilisation dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="60e02-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="60e02-104">ID de l’appelant peut être contrôlée pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l’aide d’une stratégie nommée CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="60e02-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="60e02-105">La fonctionnalité d’ID de l’appelant est disponible pour tous les utilisateurs du système téléphonique que connectivité RTPC :</span><span class="sxs-lookup"><span data-stu-id="60e02-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="60e02-106">Connectivité RTPC en ligne</span><span class="sxs-lookup"><span data-stu-id="60e02-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="60e02-107">La connectivité RTPC local avec Skype pour connecteur de nuage Professionnel (requiert le nuage connecteur Edition 1.4.2 et au-delà)</span><span class="sxs-lookup"><span data-stu-id="60e02-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="60e02-108">Connectivité RTPC local avec Skype pour Business Server (nécessite Skype pour Business Server 2015 CU5 et au-delà)</span><span class="sxs-lookup"><span data-stu-id="60e02-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="60e02-109">Cette stratégie n’est pas disponible dans Skype pour Business Server de 2015.</span><span class="sxs-lookup"><span data-stu-id="60e02-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="60e02-110">ID de l’appelant sortant</span><span class="sxs-lookup"><span data-stu-id="60e02-110">Outbound caller ID</span></span>

<span data-ttu-id="60e02-111">Trois options sont disponibles pour l’ID de l’appelant RTPC sortant :</span><span class="sxs-lookup"><span data-stu-id="60e02-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="60e02-112">Le numéro de téléphone attribué à l’utilisateur, qui est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="60e02-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="60e02-113">Numéro de stock un numéro de téléphone qui est considéré comme un *service* et un numéro *d’appel gratuit* dans vos Plans de l’appel dans téléphone d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="60e02-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="60e02-114">Il est généralement affecté à une file d’attente surveillance du ou des appels d’organisation automatique.</span><span class="sxs-lookup"><span data-stu-id="60e02-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="60e02-115">La valeur anonyme.</span><span class="sxs-lookup"><span data-stu-id="60e02-115">Set to anonymous.</span></span>
    
<span data-ttu-id="60e02-116">Toutefois, vous ne pouvez pas affecter ces types de numéros de téléphone pour l’ID d’appelant sortant :</span><span class="sxs-lookup"><span data-stu-id="60e02-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="60e02-117">Les numéros de téléphone qui sont classés en tant qu' *utilisateur* de votre téléphone appel Plans numéro de stock</span><span class="sxs-lookup"><span data-stu-id="60e02-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="60e02-118">Un Skype pour le numéro de téléphone local Business Server</span><span class="sxs-lookup"><span data-stu-id="60e02-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="60e02-119">Pour définir l’ID d’appelant sortants, consultez [la valeur de l’ID d’appelant pour un utilisateur](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="60e02-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="60e02-120">Contrôle de l’utilisateur final de l’ID de l’appelant sortant</span><span class="sxs-lookup"><span data-stu-id="60e02-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="60e02-121">L’attribut EnableUserOverride permet à un ou plusieurs utilisateurs à modifier leurs paramètres d’ID de l’appelant **anonyme**.</span><span class="sxs-lookup"><span data-stu-id="60e02-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="60e02-122">Cela s’applique uniquement lorsqu’une stratégie de CallingLineIdentity est configurée avec un paramètre de CallingIDSubstitute de LineURI ou de substitution.</span><span class="sxs-lookup"><span data-stu-id="60e02-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="60e02-123">La valeur par défaut de EnableUserOverride a la valeur False.</span><span class="sxs-lookup"><span data-stu-id="60e02-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="60e02-124">Vos utilisateurs finaux peuvent définir leur ID de l’appelant **anonyme** à l’aide de l’onglet **Paramètres d’appeler vers l’avant** dans le Skype pour client ordinateur de bureau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="60e02-124">Your end users can set their caller ID to **Anonymous** by using the **Call Forward Settings** tab in the Skype for Business desktop client.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="60e02-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="60e02-125">**Windows**</span></span> <br/> |<span data-ttu-id="60e02-126">**Version**</span><span class="sxs-lookup"><span data-stu-id="60e02-126">**Version**</span></span> <br/> |<span data-ttu-id="60e02-127">**Prise en charge**</span><span class="sxs-lookup"><span data-stu-id="60e02-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="60e02-128">Démarrer en un clic</span><span class="sxs-lookup"><span data-stu-id="60e02-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="60e02-129">Canal de cours publié le 6 décembre 2016 - version 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="60e02-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="60e02-130">Oui</span><span class="sxs-lookup"><span data-stu-id="60e02-130">Yes</span></span>  <br/> |
|<span data-ttu-id="60e02-131">Démarrer en un clic</span><span class="sxs-lookup"><span data-stu-id="60e02-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="60e02-132">Première version différé canal publié le 22 février 2017 - Version 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="60e02-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="60e02-133">Oui</span><span class="sxs-lookup"><span data-stu-id="60e02-133">Yes</span></span>  <br/> |
|<span data-ttu-id="60e02-134">Démarrer en un clic</span><span class="sxs-lookup"><span data-stu-id="60e02-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="60e02-135">Différé de canal publié le 13 juin 2017 - Version 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="60e02-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="60e02-136">Oui</span><span class="sxs-lookup"><span data-stu-id="60e02-136">Yes</span></span>  <br/> |
|<span data-ttu-id="60e02-137">MSI</span><span class="sxs-lookup"><span data-stu-id="60e02-137">MSI</span></span>  <br/> |<span data-ttu-id="60e02-138">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="60e02-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="60e02-139">Non</span><span class="sxs-lookup"><span data-stu-id="60e02-139">No</span></span>  <br/> |
|<span data-ttu-id="60e02-140">Mac</span><span class="sxs-lookup"><span data-stu-id="60e02-140">Mac</span></span>  <br/> |<span data-ttu-id="60e02-141">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="60e02-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="60e02-142">Non</span><span class="sxs-lookup"><span data-stu-id="60e02-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="60e02-143">ID de l’appelant entrant</span><span class="sxs-lookup"><span data-stu-id="60e02-143">Inbound Caller ID</span></span>

<span data-ttu-id="60e02-144">L’attribut BlockIncomingCallerID permet de blocage de l’ID d’appelant pour les appels entrants RTPC.</span><span class="sxs-lookup"><span data-stu-id="60e02-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="60e02-145">Vous pouvez définir cet attribut, mais il n’est pas disponible pour les utilisateurs finaux sur la page Paramètres de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="60e02-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="60e02-146">Et elle n’est disponible qu’avec connectivité RTPC en ligne.</span><span class="sxs-lookup"><span data-stu-id="60e02-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="60e02-147">Pour définir l’ID d’appelant sortants, consultez [la valeur de l’ID d’appelant pour un utilisateur](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="60e02-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="60e02-148">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="60e02-148">Related topics</span></span>
[<span data-ttu-id="60e02-149">Transfert de questions courantes des numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="60e02-149">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="60e02-150">Différents types de numéros de téléphone utilisés pour les Plans d’appel</span><span class="sxs-lookup"><span data-stu-id="60e02-150">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="60e02-151">Gérer les numéros de téléphone pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="60e02-151">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="60e02-152">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="60e02-152">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="60e02-153">Skype pour Business Online : étiquette de décharge de responsabilité d’appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="60e02-153">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)