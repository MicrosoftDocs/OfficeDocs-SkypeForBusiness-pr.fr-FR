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
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: ID de l’appelant peut être contrôlé pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l’aide d’une stratégie appelée CallingLineIdentity.
ms.openlocfilehash: c2a508e89f9fbf279e048fcdccca1ac1b0534305
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883563"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="fd0ef-103">Comment utiliser un ID d'appelant dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="fd0ef-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="fd0ef-104">ID de l’appelant peut être contrôlé pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l’aide d’une stratégie appelée CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="fd0ef-105">La fonctionnalité d’ID de l’appelant est disponible pour tous les utilisateurs du système téléphonique quelle que soit la connectivité PSTN :</span><span class="sxs-lookup"><span data-stu-id="fd0ef-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="fd0ef-106">Connectivité RTC en ligne</span><span class="sxs-lookup"><span data-stu-id="fd0ef-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="fd0ef-107">Connectivité RTC locale avec Skype Entreprise, Édition Cloud Connector (requiert Cloud Connector Édition 1.4.2 et version ultérieure)</span><span class="sxs-lookup"><span data-stu-id="fd0ef-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="fd0ef-108">Connectivité RTC locale avec Skype Entreprise Server (requiert Skype Entreprise Server 2015 CU5 et version ultérieure)</span><span class="sxs-lookup"><span data-stu-id="fd0ef-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="fd0ef-109">Cette stratégie n'est pas disponible pour Skype Entreprise 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="fd0ef-110">ID d'appelant sortant</span><span class="sxs-lookup"><span data-stu-id="fd0ef-110">Outbound caller ID</span></span>

<span data-ttu-id="fd0ef-111">Trois options sont disponibles pour l'ID d'appelant RTC sortant :</span><span class="sxs-lookup"><span data-stu-id="fd0ef-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="fd0ef-112">Le numéro de téléphone attribué à l’utilisateur, qui est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="fd0ef-113">Un numéro de téléphone considéré comme un numéro *de service* et *gratuit* dans votre stock de numéros de téléphones de vos Forfaits d’appels dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="fd0ef-114">Il est généralement attribué à un standard automatique d’organisation ou à une file d’appels.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="fd0ef-115">Défini sur Anonyme.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-115">Set to anonymous.</span></span>
    
<span data-ttu-id="fd0ef-116">Toutefois, vous ne pouvez pas affecter les types de numéros de téléphone suivants à l'ID d'appelant entrant :</span><span class="sxs-lookup"><span data-stu-id="fd0ef-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="fd0ef-117">Les numéros de téléphone qui sont classés en tant qu' *utilisateur* de votre téléphone de l’appel des Plans de numéro d’inventaire</span><span class="sxs-lookup"><span data-stu-id="fd0ef-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="fd0ef-118">Un numéro de téléphone Skype Entreprise Server local</span><span class="sxs-lookup"><span data-stu-id="fd0ef-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="fd0ef-119">Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="fd0ef-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="fd0ef-120">Contrôle de l'ID d'appelant sortant par l'utilisateur final</span><span class="sxs-lookup"><span data-stu-id="fd0ef-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="fd0ef-121">L'attribut EnableUserOverride permet à un ou plusieurs utilisateurs de modifier leur paramètre d'ID d'appelant pour le définir sur **Anonyme**.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="fd0ef-122">Cela s'applique uniquement lorsqu'une stratégie CallingLineIdentity est configurée avec un paramètre CallingIDSubstitute défini sur LineURI ou Substitute.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="fd0ef-123">La valeur par défaut de EnableUserOverride est False.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="fd0ef-124">Vos utilisateurs finaux peuvent définir leur ID d’appelant **anonyme** à l’aide de l’onglet **Paramètres d’appel vers l’avant** dans le Skype pour le client de bureau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-124">Your end users can set their caller ID to **Anonymous** by using the **Call Forward Settings** tab in the Skype for Business desktop client.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="fd0ef-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="fd0ef-125">**Windows**</span></span> <br/> |<span data-ttu-id="fd0ef-126">**Version**</span><span class="sxs-lookup"><span data-stu-id="fd0ef-126">**Version**</span></span> <br/> |<span data-ttu-id="fd0ef-127">**Prise en charge**</span><span class="sxs-lookup"><span data-stu-id="fd0ef-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="fd0ef-128">Démarrer en un clic</span><span class="sxs-lookup"><span data-stu-id="fd0ef-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="fd0ef-129">Canal actuel publié le 6 décembre 2016 - version 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="fd0ef-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="fd0ef-130">Oui</span><span class="sxs-lookup"><span data-stu-id="fd0ef-130">Yes</span></span>  <br/> |
|<span data-ttu-id="fd0ef-131">Démarrer en un clic</span><span class="sxs-lookup"><span data-stu-id="fd0ef-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="fd0ef-132">Première version du canal différé publiée le 22 février 2017 - version 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="fd0ef-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="fd0ef-133">Oui</span><span class="sxs-lookup"><span data-stu-id="fd0ef-133">Yes</span></span>  <br/> |
|<span data-ttu-id="fd0ef-134">Démarrer en un clic</span><span class="sxs-lookup"><span data-stu-id="fd0ef-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="fd0ef-135">Canal Différé publié le 13 juin 2017 - Version 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="fd0ef-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="fd0ef-136">Oui</span><span class="sxs-lookup"><span data-stu-id="fd0ef-136">Yes</span></span>  <br/> |
|<span data-ttu-id="fd0ef-137">MSI</span><span class="sxs-lookup"><span data-stu-id="fd0ef-137">MSI</span></span>  <br/> |<span data-ttu-id="fd0ef-138">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="fd0ef-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="fd0ef-139">Non</span><span class="sxs-lookup"><span data-stu-id="fd0ef-139">No</span></span>  <br/> |
|<span data-ttu-id="fd0ef-140">Mac</span><span class="sxs-lookup"><span data-stu-id="fd0ef-140">Mac</span></span>  <br/> |<span data-ttu-id="fd0ef-141">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="fd0ef-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="fd0ef-142">Non</span><span class="sxs-lookup"><span data-stu-id="fd0ef-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="fd0ef-143">ID d'appelant entrant</span><span class="sxs-lookup"><span data-stu-id="fd0ef-143">Inbound Caller ID</span></span>

<span data-ttu-id="fd0ef-144">L'attribut BlockIncomingCallerID permet de bloquer l'ID d'appelant dans les appels RTC entrants.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="fd0ef-145">Vous pouvez définir cet attribut, mais il n’est pas disponible pour les utilisateurs finaux dans la page de paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="fd0ef-146">Pour le moment, il est disponible uniquement avec la connectivité RTC en ligne.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="fd0ef-147">Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="fd0ef-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fd0ef-148">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="fd0ef-148">Related topics</span></span>
[<span data-ttu-id="fd0ef-149">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="fd0ef-149">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="fd0ef-150">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="fd0ef-150">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="fd0ef-151">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="fd0ef-151">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="fd0ef-152">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="fd0ef-152">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="fd0ef-153">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="fd0ef-153">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 