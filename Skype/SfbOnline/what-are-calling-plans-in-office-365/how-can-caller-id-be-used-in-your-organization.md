---
title: Comment utiliser un ID d'appelant dans votre organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: ID de l’appelant peut être contrôlé pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l’aide d’une stratégie appelée CallingLineIdentity.
ms.openlocfilehash: a1a809805b96152e4b205c8f38b3c8409014eb55
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="04069-103">Comment utiliser un ID d'appelant dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="04069-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="04069-104">ID de l’appelant peut être contrôlé pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l’aide d’une stratégie appelée CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="04069-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="04069-105">La fonctionnalité d’ID de l’appelant est disponible pour tous les utilisateurs du système téléphonique quelle que soit la connectivité PSTN :</span><span class="sxs-lookup"><span data-stu-id="04069-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="04069-106">Connectivité RTC en ligne</span><span class="sxs-lookup"><span data-stu-id="04069-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="04069-107">Connectivité RTC locale avec Skype Entreprise, Édition Cloud Connector (requiert Cloud Connector Édition 1.4.2 et version ultérieure)</span><span class="sxs-lookup"><span data-stu-id="04069-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="04069-108">Connectivité RTC locale avec Skype Entreprise Server (requiert Skype Entreprise Server 2015 CU5 et version ultérieure)</span><span class="sxs-lookup"><span data-stu-id="04069-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="04069-109">Cette stratégie n'est pas disponible pour Skype Entreprise 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="04069-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="04069-110">ID d'appelant sortant</span><span class="sxs-lookup"><span data-stu-id="04069-110">Outbound caller ID</span></span>

<span data-ttu-id="04069-111">Trois options sont disponibles pour l'ID d'appelant RTC sortant :</span><span class="sxs-lookup"><span data-stu-id="04069-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="04069-112">Le numéro de téléphone attribué à l’utilisateur, qui est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="04069-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="04069-113">Un numéro de téléphone qui est considéré comme un *service* et un *numéro gratuit* nombre dans vos Plans de l’appel dans Office 365 téléphone numéro inventaire.</span><span class="sxs-lookup"><span data-stu-id="04069-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="04069-114">Il est généralement attribué à une file d’attente d’organisation automatique standard ou un appel.</span><span class="sxs-lookup"><span data-stu-id="04069-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="04069-115">Défini sur Anonyme.</span><span class="sxs-lookup"><span data-stu-id="04069-115">Set to anonymous.</span></span>
    
<span data-ttu-id="04069-116">Toutefois, vous ne pouvez pas affecter les types de numéros de téléphone suivants à l'ID d'appelant entrant :</span><span class="sxs-lookup"><span data-stu-id="04069-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="04069-117">Les numéros de téléphone qui sont classés en tant qu' *utilisateur* de votre téléphone de l’appel des Plans de numéro d’inventaire</span><span class="sxs-lookup"><span data-stu-id="04069-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="04069-118">Un numéro de téléphone Skype Entreprise Server local</span><span class="sxs-lookup"><span data-stu-id="04069-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="04069-119">Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="04069-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="04069-120">Contrôle de l'ID d'appelant sortant par l'utilisateur final</span><span class="sxs-lookup"><span data-stu-id="04069-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="04069-121">L’attribut EnableUserOverride permet à un ou plusieurs utilisateurs à modifier leurs paramètres d’ID de l’appelant **anonyme**.</span><span class="sxs-lookup"><span data-stu-id="04069-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="04069-122">Cela s’applique uniquement lorsqu’une stratégie CallingLineIdentity est configurée avec un paramètre CallingIDSubstitute de LineURI ou de remplacement.</span><span class="sxs-lookup"><span data-stu-id="04069-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="04069-123">La valeur par défaut de EnableUserOverride a la valeur False.</span><span class="sxs-lookup"><span data-stu-id="04069-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="04069-124">Vos utilisateurs finaux peuvent définir leur ID d’appelant **anonyme** à l’aide de l’onglet **Paramètres d’appel vers l’avant** dans le Skype pour le client de bureau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="04069-124">Your end users can set their caller ID to **Anonymous** by using the **Call Forward Settings** tab in the Skype for Business desktop client.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="04069-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="04069-125">**Windows**</span></span> <br/> |<span data-ttu-id="04069-126">**Version**</span><span class="sxs-lookup"><span data-stu-id="04069-126">**Version**</span></span> <br/> |<span data-ttu-id="04069-127">**Prise en charge**</span><span class="sxs-lookup"><span data-stu-id="04069-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="04069-128">Démarrer en un clic</span><span class="sxs-lookup"><span data-stu-id="04069-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="04069-129">Canal actuel publié le 6 décembre 2016 - version 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="04069-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="04069-130">Oui</span><span class="sxs-lookup"><span data-stu-id="04069-130">Yes</span></span>  <br/> |
|<span data-ttu-id="04069-131">Démarrer en un clic</span><span class="sxs-lookup"><span data-stu-id="04069-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="04069-132">Première version du canal différé publiée le 22 février 2017 - version 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="04069-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="04069-133">Oui</span><span class="sxs-lookup"><span data-stu-id="04069-133">Yes</span></span>  <br/> |
|<span data-ttu-id="04069-134">Démarrer en un clic</span><span class="sxs-lookup"><span data-stu-id="04069-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="04069-135">Différé canal publié le 13 juin 2017 - Version 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="04069-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="04069-136">Oui</span><span class="sxs-lookup"><span data-stu-id="04069-136">Yes</span></span>  <br/> |
|<span data-ttu-id="04069-137">MSI</span><span class="sxs-lookup"><span data-stu-id="04069-137">MSI</span></span>  <br/> |<span data-ttu-id="04069-138">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="04069-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="04069-139">Non</span><span class="sxs-lookup"><span data-stu-id="04069-139">No</span></span>  <br/> |
|<span data-ttu-id="04069-140">Mac</span><span class="sxs-lookup"><span data-stu-id="04069-140">Mac</span></span>  <br/> |<span data-ttu-id="04069-141">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="04069-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="04069-142">Non</span><span class="sxs-lookup"><span data-stu-id="04069-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="04069-143">ID d'appelant entrant</span><span class="sxs-lookup"><span data-stu-id="04069-143">Inbound Caller ID</span></span>

<span data-ttu-id="04069-144">L’attribut BlockIncomingCallerID permet de blocage de l’ID d’appelant pour les appels PSTN entrants.</span><span class="sxs-lookup"><span data-stu-id="04069-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="04069-145">Vous pouvez définir cet attribut, mais il n’est pas disponible pour les utilisateurs finaux dans la page de paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="04069-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="04069-146">Pour le moment, il est disponible uniquement avec la connectivité RTC en ligne.</span><span class="sxs-lookup"><span data-stu-id="04069-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="04069-147">Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="04069-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="04069-148">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="04069-148">Related topics</span></span>
[<span data-ttu-id="04069-149">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="04069-149">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="04069-150">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="04069-150">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="04069-151">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="04069-151">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="04069-152">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="04069-152">Emergency calling terms and conditions</span></span>](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

<span data-ttu-id="04069-153">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="04069-153">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 