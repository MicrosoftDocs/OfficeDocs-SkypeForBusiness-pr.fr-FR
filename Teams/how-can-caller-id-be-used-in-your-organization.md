---
title: Comment utiliser un ID d'appelant dans votre organisation
author: CarolynRowe
ms.author: crowe
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.voice.callerid.overview
ms.custom:
- Calling Plans
description: L’identification de l’appelant peut être contrôlée pour les appels entrants et sortants des utilisateurs du système téléphonique à l’aide d’une stratégie appelée CallingLineIdentity.
ms.openlocfilehash: f5357ae8c19182329a7c82651ac74a6727228d03
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328309"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="9ee26-103">Comment utiliser un ID d'appelant dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="9ee26-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="9ee26-104">L’identification de l’appelant peut être contrôlée pour les appels entrants et sortants des utilisateurs du système téléphonique à l’aide d’une stratégie appelée CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="9ee26-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="9ee26-105">La fonctionnalité d’identification de l’appelant est disponible pour tous les utilisateurs du système téléphonique, quelle que soit la connectivité RTC :</span><span class="sxs-lookup"><span data-stu-id="9ee26-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="9ee26-106">Connectivité RTC en ligne</span><span class="sxs-lookup"><span data-stu-id="9ee26-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="9ee26-107">Connectivité RTC locale avec Skype Entreprise, Édition Cloud Connector (requiert Cloud Connector Édition 1.4.2 et version ultérieure)</span><span class="sxs-lookup"><span data-stu-id="9ee26-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="9ee26-108">Connectivité RTC locale avec Skype Entreprise Server (requiert Skype Entreprise Server 2015 CU5 et version ultérieure)</span><span class="sxs-lookup"><span data-stu-id="9ee26-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="9ee26-109">Cette stratégie n'est pas disponible pour Skype Entreprise 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="9ee26-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="9ee26-110">ID d'appelant sortant</span><span class="sxs-lookup"><span data-stu-id="9ee26-110">Outbound caller ID</span></span>

<span data-ttu-id="9ee26-111">Trois options sont disponibles pour l'ID d'appelant RTC sortant :</span><span class="sxs-lookup"><span data-stu-id="9ee26-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="9ee26-112">Le numéro de téléphone affecté à l’utilisateur (option par défaut).</span><span class="sxs-lookup"><span data-stu-id="9ee26-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="9ee26-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span><span class="sxs-lookup"><span data-stu-id="9ee26-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="9ee26-115">Défini sur Anonyme.</span><span class="sxs-lookup"><span data-stu-id="9ee26-115">Set to anonymous.</span></span>
    
<span data-ttu-id="9ee26-116">Toutefois, vous ne pouvez pas affecter les types de numéros de téléphone suivants à l'ID d'appelant entrant :</span><span class="sxs-lookup"><span data-stu-id="9ee26-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="9ee26-117">Les numéros de téléphone classés comme *utilisateur* dans votre inventaire de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="9ee26-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="9ee26-118">Un numéro de téléphone Skype Entreprise Server local</span><span class="sxs-lookup"><span data-stu-id="9ee26-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="9ee26-119">Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="9ee26-119">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="9ee26-120">Contrôle de l'ID d'appelant sortant par l'utilisateur final</span><span class="sxs-lookup"><span data-stu-id="9ee26-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="9ee26-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span><span class="sxs-lookup"><span data-stu-id="9ee26-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="9ee26-124">Vos utilisateurs finaux peuvent définir leur ID d’appelant sur **anonyme** à l’aide de l’onglet **paramètres** dans le client de bureau Skype entreprise, sélectionner **appelle un utilisateur final** (s’il est activé par l’administrateur), sélectionner \*\*Masquer mon numéro de téléphone et les informations de profil de tous les appels \*\*.</span><span class="sxs-lookup"><span data-stu-id="9ee26-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="9ee26-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="9ee26-125">**Windows**</span></span> <br/> |<span data-ttu-id="9ee26-126">**Version**</span><span class="sxs-lookup"><span data-stu-id="9ee26-126">**Version**</span></span> <br/> |<span data-ttu-id="9ee26-127">**Prise en charge**</span><span class="sxs-lookup"><span data-stu-id="9ee26-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="9ee26-128">Démarrer en un clic</span><span class="sxs-lookup"><span data-stu-id="9ee26-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="9ee26-129">Canal actuel publié le 6 décembre 2016 - version 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="9ee26-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="9ee26-130">Oui</span><span class="sxs-lookup"><span data-stu-id="9ee26-130">Yes</span></span>  <br/> |
|<span data-ttu-id="9ee26-131">Démarrer en un clic</span><span class="sxs-lookup"><span data-stu-id="9ee26-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="9ee26-132">Première version du canal différé publiée le 22 février 2017 - version 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="9ee26-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="9ee26-133">Oui</span><span class="sxs-lookup"><span data-stu-id="9ee26-133">Yes</span></span>  <br/> |
|<span data-ttu-id="9ee26-134">Démarrer en un clic</span><span class="sxs-lookup"><span data-stu-id="9ee26-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="9ee26-135">Canal Différé publié le 13 juin 2017 - Version 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="9ee26-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="9ee26-136">Oui</span><span class="sxs-lookup"><span data-stu-id="9ee26-136">Yes</span></span>  <br/> |
|<span data-ttu-id="9ee26-137">MSI</span><span class="sxs-lookup"><span data-stu-id="9ee26-137">MSI</span></span>  <br/> |<span data-ttu-id="9ee26-138">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="9ee26-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="9ee26-139">Non</span><span class="sxs-lookup"><span data-stu-id="9ee26-139">No</span></span>  <br/> |
|<span data-ttu-id="9ee26-140">Mac</span><span class="sxs-lookup"><span data-stu-id="9ee26-140">Mac</span></span>  <br/> |<span data-ttu-id="9ee26-141">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="9ee26-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="9ee26-142">Non</span><span class="sxs-lookup"><span data-stu-id="9ee26-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="9ee26-143">ID d'appelant entrant</span><span class="sxs-lookup"><span data-stu-id="9ee26-143">Inbound Caller ID</span></span>

<span data-ttu-id="9ee26-144">Le système téléphonique affiche l’ID appelé d’un numéro de téléphone externe si le numéro est associé à un utilisateur dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9ee26-144">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="9ee26-145">Si ce n’est pas le cas, le nom d’affichage fourni par l’opérateur de télécommunications est affiché s’il est disponible.</span><span class="sxs-lookup"><span data-stu-id="9ee26-145">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="9ee26-146">L'attribut BlockIncomingCallerID permet de bloquer l'ID d'appelant dans les appels RTC entrants.</span><span class="sxs-lookup"><span data-stu-id="9ee26-146">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="9ee26-147">Vous pouvez définir cet attribut, mais il n’est pas disponible pour les utilisateurs finaux dans la page Paramètres de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9ee26-147">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="9ee26-148">Pour le moment, il est disponible uniquement avec la connectivité RTC en ligne.</span><span class="sxs-lookup"><span data-stu-id="9ee26-148">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="9ee26-149">Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="9ee26-149">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9ee26-150">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="9ee26-150">Related topics</span></span>
[<span data-ttu-id="9ee26-151">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="9ee26-151">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="9ee26-152">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="9ee26-152">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="9ee26-153">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="9ee26-153">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="9ee26-154">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="9ee26-154">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="9ee26-155">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="9ee26-155">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
