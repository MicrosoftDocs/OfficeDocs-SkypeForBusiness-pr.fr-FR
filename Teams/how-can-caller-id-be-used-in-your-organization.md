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
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: L’identification de l’appelant peut être contrôlée pour les appels entrants et sortants des utilisateurs du système téléphonique à l’aide d’une stratégie appelée CallingLineIdentity.
ms.openlocfilehash: 5c20f439d156997c89ca54c2a3bf39e9c3a42ae4
ms.sourcegitcommit: ded1e92348b6c18aa31f7f67e68ced3db525977d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506197"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="576df-103">Comment utiliser un ID d'appelant dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="576df-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="576df-104">L’identification de l’appelant peut être contrôlée pour les appels entrants et sortants des utilisateurs du système téléphonique à l’aide d’une stratégie appelée CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="576df-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="576df-105">La fonctionnalité d’identification de l’appelant est disponible pour tous les utilisateurs du système téléphonique, quelle que soit la connectivité RTC :</span><span class="sxs-lookup"><span data-stu-id="576df-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>

- <span data-ttu-id="576df-106">Plans d’appel Microsoft</span><span class="sxs-lookup"><span data-stu-id="576df-106">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="576df-107">Routage direct via le système téléphonique</span><span class="sxs-lookup"><span data-stu-id="576df-107">Phone System Direct Routing</span></span> 
  
- <span data-ttu-id="576df-108">Connectivité RTC en ligne</span><span class="sxs-lookup"><span data-stu-id="576df-108">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="576df-109">Connectivité RTC locale avec Skype Entreprise, Édition Cloud Connector (requiert Cloud Connector Édition 1.4.2 et version ultérieure)</span><span class="sxs-lookup"><span data-stu-id="576df-109">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="576df-110">Connectivité RTC locale avec Skype Entreprise Server (requiert Skype Entreprise Server 2015 CU5 et version ultérieure)</span><span class="sxs-lookup"><span data-stu-id="576df-110">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="576df-111">Cette stratégie n'est pas disponible pour Skype Entreprise 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="576df-111">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="576df-112">ID d'appelant sortant</span><span class="sxs-lookup"><span data-stu-id="576df-112">Outbound caller ID</span></span>

<span data-ttu-id="576df-113">Trois options sont disponibles pour l’identification de l’appelant RTC sortant :</span><span class="sxs-lookup"><span data-stu-id="576df-113">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="576df-114">Le numéro de téléphone affecté à l’utilisateur (option par défaut).</span><span class="sxs-lookup"><span data-stu-id="576df-114">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="576df-115">Un numéro de téléphone classé comme *service* et numéro *gratuit* dans l’inventaire de vos offres d’appels.</span><span class="sxs-lookup"><span data-stu-id="576df-115">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="576df-116">Il est généralement attribué à un standard automatique d’organisation ou à une file d’appels.</span><span class="sxs-lookup"><span data-stu-id="576df-116">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="576df-117">Défini sur Anonyme.</span><span class="sxs-lookup"><span data-stu-id="576df-117">Set to anonymous.</span></span>
    
<span data-ttu-id="576df-118">Toutefois, vous ne pouvez pas affecter les types de numéros de téléphone suivants à l'ID d'appelant entrant :</span><span class="sxs-lookup"><span data-stu-id="576df-118">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="576df-119">Les numéros de téléphone classés comme *utilisateur* dans votre inventaire de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="576df-119">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="576df-120">Un numéro de téléphone Skype Entreprise Server local</span><span class="sxs-lookup"><span data-stu-id="576df-120">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="576df-121">Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="576df-121">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="576df-122">Contrôle de l’ID d’appelant sortant par l’utilisateur final</span><span class="sxs-lookup"><span data-stu-id="576df-122">End user control of outbound caller ID</span></span>

<span data-ttu-id="576df-123">L’attribut EnableUserOverride permet à un ou plusieurs utilisateurs de changer leur paramètre d’ID d’appelant en **anonyme**.</span><span class="sxs-lookup"><span data-stu-id="576df-123">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="576df-124">Cela s'applique uniquement lorsqu'une stratégie CallingLineIdentity est configurée avec un paramètre CallingIDSubstitute défini sur LineURI ou Substitute.</span><span class="sxs-lookup"><span data-stu-id="576df-124">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="576df-125">La valeur par défaut de EnableUserOverride est False.</span><span class="sxs-lookup"><span data-stu-id="576df-125">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="576df-126">Vos utilisateurs finaux peuvent définir leur ID d’appelant sur **anonyme** à l’aide de l’onglet **paramètres** dans le client de bureau Skype entreprise, sélectionner **appelle un utilisateur final** (s’il est activé par l’administrateur), puis sélectionner **Masquer mon numéro de téléphone et les informations de profil de tous les appels**.</span><span class="sxs-lookup"><span data-stu-id="576df-126">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="576df-127">Dans Teams, les utilisateurs peuvent accéder à leur image de profil dans le coin supérieur droit, sélectionner **paramètres**des  >  **appels**, puis sous identification de l' **appelant**, sélectionner **Masquer mon numéro de téléphone et les informations de profil de tous les appels**.</span><span class="sxs-lookup"><span data-stu-id="576df-127">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="576df-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="576df-128">**Windows**</span></span> <br/> |<span data-ttu-id="576df-129">**Version**</span><span class="sxs-lookup"><span data-stu-id="576df-129">**Version**</span></span> <br/> |<span data-ttu-id="576df-130">**Prise en charge**</span><span class="sxs-lookup"><span data-stu-id="576df-130">**Supported**</span></span> <br/> |
|<span data-ttu-id="576df-131">Démarrer en un clic</span><span class="sxs-lookup"><span data-stu-id="576df-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="576df-132">Canal actuel publié le 6 décembre 2016 - version 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="576df-132">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="576df-133">Oui</span><span class="sxs-lookup"><span data-stu-id="576df-133">Yes</span></span>  <br/> |
|<span data-ttu-id="576df-134">Démarrer en un clic</span><span class="sxs-lookup"><span data-stu-id="576df-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="576df-135">Première version du canal différé publiée le 22 février 2017 - version 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="576df-135">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="576df-136">Oui</span><span class="sxs-lookup"><span data-stu-id="576df-136">Yes</span></span>  <br/> |
|<span data-ttu-id="576df-137">Démarrer en un clic</span><span class="sxs-lookup"><span data-stu-id="576df-137">Click-to-Run</span></span>  <br/> |<span data-ttu-id="576df-138">Canal Différé publié le 13 juin 2017 - Version 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="576df-138">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="576df-139">Oui</span><span class="sxs-lookup"><span data-stu-id="576df-139">Yes</span></span>  <br/> |
|<span data-ttu-id="576df-140">MSI</span><span class="sxs-lookup"><span data-stu-id="576df-140">MSI</span></span>  <br/> |<span data-ttu-id="576df-141">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="576df-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="576df-142">Non</span><span class="sxs-lookup"><span data-stu-id="576df-142">No</span></span>  <br/> |
|<span data-ttu-id="576df-143">Mac</span><span class="sxs-lookup"><span data-stu-id="576df-143">Mac</span></span>  <br/> |<span data-ttu-id="576df-144">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="576df-144">Skype for Business</span></span>  <br/> |<span data-ttu-id="576df-145">Non</span><span class="sxs-lookup"><span data-stu-id="576df-145">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="576df-146">ID d’appelant entrant</span><span class="sxs-lookup"><span data-stu-id="576df-146">Inbound caller ID</span></span>

<span data-ttu-id="576df-147">Le système téléphonique affiche l’ID appelé d’un numéro de téléphone externe si le numéro est associé à un utilisateur dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="576df-147">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="576df-148">Si ce n’est pas le cas, le nom d’affichage fourni par l’opérateur de télécommunications est affiché s’il est disponible.</span><span class="sxs-lookup"><span data-stu-id="576df-148">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="576df-149">L'attribut BlockIncomingCallerID permet de bloquer l'ID d'appelant dans les appels RTC entrants.</span><span class="sxs-lookup"><span data-stu-id="576df-149">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="576df-150">Vous pouvez définir cet attribut, mais il n’est pas disponible pour les utilisateurs finaux dans la page Paramètres de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="576df-150">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="576df-151">Pour le moment, il est disponible uniquement avec la connectivité RTC en ligne.</span><span class="sxs-lookup"><span data-stu-id="576df-151">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="576df-152">Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="576df-152">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="576df-153">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="576df-153">Related topics</span></span>
[<span data-ttu-id="576df-154">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="576df-154">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="576df-155">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="576df-155">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="576df-156">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="576df-156">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="576df-157">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="576df-157">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="576df-158">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="576df-158">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
