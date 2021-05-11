---
title: Comment utiliser un ID d'appelant dans votre organisation
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
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
description: L’ID d’appelant peut être contrôlé pour les appels entrants et sortants pour Système téléphonique utilisateurs à l’aide d’une stratégie appelée CallingLineIdentity.
ms.openlocfilehash: 2a104679be84dfdaa4574353ccc79142d8a82284
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308343"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="6d407-103">Comment utiliser un ID d'appelant dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="6d407-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="6d407-104">L’ID d’appelant se compose de deux informations identifiables :</span><span class="sxs-lookup"><span data-stu-id="6d407-104">Caller ID consists of two user-facing identifiable pieces of information:</span></span>

- <span data-ttu-id="6d407-105">Un numéro de téléphone (généralement appelé CLID ou ID de ligne d’appel).</span><span class="sxs-lookup"><span data-stu-id="6d407-105">A phone number (typically referred to as CLID or calling line ID).</span></span> <span data-ttu-id="6d407-106">Il s’agit du numéro de téléphone commuté public (PSTN) présenté comme identification de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="6d407-106">This is the Public Switched Telephone Number (PSTN) presented as the identification of the caller.</span></span>

- <span data-ttu-id="6d407-107">Nom de l’appelant (généralement appelé CNAM).</span><span class="sxs-lookup"><span data-stu-id="6d407-107">A Calling party name (typically referred to as CNAM).</span></span> 
  
<span data-ttu-id="6d407-108">La fonctionnalité d’ID d’appelant est disponible pour tous Système téléphonique utilisateurs quelle que soit l’option de connectivité PSTN :</span><span class="sxs-lookup"><span data-stu-id="6d407-108">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity option:</span></span>

- <span data-ttu-id="6d407-109">Forfaits d’appels Microsoft</span><span class="sxs-lookup"><span data-stu-id="6d407-109">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="6d407-110">Routage direct via le système téléphonique</span><span class="sxs-lookup"><span data-stu-id="6d407-110">Phone System Direct Routing</span></span> 
  
<span data-ttu-id="6d407-111">Vous pouvez contrôler l’ID d’appelant pour les appels entrants et sortants à l’aide d’une stratégie appelée CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="6d407-111">You can control Caller ID for both inbound and outbound calls by using a policy called CallingLineIdentity.</span></span> <span data-ttu-id="6d407-112">Pour plus d’informations, voir [Plus d’informations sur l’ID de ligne d’appel et le nom de l’appelant.](more-about-calling-line-id-and-calling-party-name.md)</span><span class="sxs-lookup"><span data-stu-id="6d407-112">For more information, see [More about Calling Line ID and Calling Party Name](more-about-calling-line-id-and-calling-party-name.md).</span></span>

  
## <a name="outbound-pstn-caller-id"></a><span data-ttu-id="6d407-113">ID d’appelant PSTN sortant</span><span class="sxs-lookup"><span data-stu-id="6d407-113">Outbound PSTN caller ID</span></span>

<span data-ttu-id="6d407-114">Pour l’ID d’appelant PSTN sortant, les options suivantes sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="6d407-114">For the outbound PSTN caller ID, the following options are available.</span></span> 

> [!NOTE]
> <span data-ttu-id="6d407-115">Certaines options, indiquées ci-dessous, sont disponibles en version d’aperçu.</span><span class="sxs-lookup"><span data-stu-id="6d407-115">Some options, indicated below, are in preview release.</span></span>
  
- <span data-ttu-id="6d407-116">Le numéro de téléphone affecté à l’utilisateur (valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="6d407-116">The telephone number assigned to the user, which is the default.</span></span>

- <span data-ttu-id="6d407-117">Anonyme, disponible en supprimant la présentation du numéro PSTN de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d407-117">Anonymous, which is available by removing the presentation of the user’s PSTN number.</span></span> 

- <span data-ttu-id="6d407-118">Un numéro de téléphone de substitution, qui peut être :</span><span class="sxs-lookup"><span data-stu-id="6d407-118">A substitute phone number, which can be:</span></span>

  - <span data-ttu-id="6d407-119">Un numéro de téléphone classé comme service et numéro gratuit dans l’inventaire de numéros de téléphone de vos forfaits d’appels.</span><span class="sxs-lookup"><span data-stu-id="6d407-119">A telephone number that is classified as a service and toll-free number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="6d407-120">Elle est généralement affectée à une Teams Standard automatique ou à une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="6d407-120">It is usually assigned to a Teams Auto Attendant or Call Queue.</span></span>

  - <span data-ttu-id="6d407-121">**Version d’aperçu.**</span><span class="sxs-lookup"><span data-stu-id="6d407-121">**Preview release.**</span></span> <span data-ttu-id="6d407-122">Un numéro de téléphone local via un routage direct affecté à un compte de ressource utilisé par une Teams Standard automatique ou une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="6d407-122">An on-premises telephone number through Direct Routing that is assigned to a resource account used by a Teams Auto Attendant or Call Queue.</span></span> 

- <span data-ttu-id="6d407-123">**Version d’aperçu.**</span><span class="sxs-lookup"><span data-stu-id="6d407-123">**Preview release.**</span></span> <span data-ttu-id="6d407-124">Nom de l’appelant ou nom de l’appelant dans l’appel RSTN sortant.</span><span class="sxs-lookup"><span data-stu-id="6d407-124">The Calling Party Name or CNAM set on the outbound PSTN call.</span></span>  
    
<span data-ttu-id="6d407-125">Pour plus d’informations, [voir Définir l’ID d’appelant d’un utilisateur.](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="6d407-125">For more information, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="6d407-126">Contrôle de l’ID d’appelant sortant par l’utilisateur final</span><span class="sxs-lookup"><span data-stu-id="6d407-126">End user control of outbound caller ID</span></span>

<span data-ttu-id="6d407-127">Les utilisateurs peuvent définir leur paramètre d’ID d’appelant sur **Anonyme** en paramètres d’attribut EnableUserOverride.</span><span class="sxs-lookup"><span data-stu-id="6d407-127">Users can change their caller ID setting to **Anonymous** by setting the EnableUserOverride attribute.</span></span> 

<span data-ttu-id="6d407-128">Si l’ID d’appelant sortant est définie sur Anonyme, le contrôle EnableUserOverride n’a aucun effet et l’ID d’appelant est toujours définie sur Anonyme.</span><span class="sxs-lookup"><span data-stu-id="6d407-128">If the outbound caller ID is set to Anonymous, the EnableUserOverride has no effect and the caller ID is always set to Anonymous.</span></span> <span data-ttu-id="6d407-129">La valeur par défaut de EnableUserOverride est False.</span><span class="sxs-lookup"><span data-stu-id="6d407-129">The default value of EnableUserOverride is False.</span></span>

<span data-ttu-id="6d407-130">Vos utilisateurs finaux peuvent définir leur ID d’appelant sur Anonyme en sélectionnant **Paramètres > Appels,** puis sous **ID** de l’appelant, sélectionnez Masquer mon numéro de téléphone et les informations de profil pour tous les **appels.**</span><span class="sxs-lookup"><span data-stu-id="6d407-130">Your end users can set their caller ID to Anonymous by going to **Settings > Calls**, and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>

### <a name="notes"></a><span data-ttu-id="6d407-131">Remarques</span><span class="sxs-lookup"><span data-stu-id="6d407-131">Notes</span></span>

<span data-ttu-id="6d407-132">Tenez compte des points suivants :</span><span class="sxs-lookup"><span data-stu-id="6d407-132">Keep the following in mind:</span></span>

- <span data-ttu-id="6d407-133">Vous ne pouvez pas affecter les types suivants de numéros de téléphone à l’ID d’appelant sortant :</span><span class="sxs-lookup"><span data-stu-id="6d407-133">You can't assign the following types of phone numbers for the outbound caller ID:</span></span>

  - <span data-ttu-id="6d407-134">Les numéros de téléphone classés comme utilisateurs dans le stock des numéros de téléphone de vos forfaits d’appels.</span><span class="sxs-lookup"><span data-stu-id="6d407-134">Any phone numbers that are classified as a user in your Calling Plans telephone number inventory.</span></span>

  - <span data-ttu-id="6d407-135">Tout numéro de téléphone local via un routage direct affecté à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d407-135">Any on-premises telephone number via Direct Routing that is assigned to a user.</span></span>

  - <span data-ttu-id="6d407-136">Un Skype Entreprise Server numéro de téléphone local.</span><span class="sxs-lookup"><span data-stu-id="6d407-136">A Skype for Business Server on-premises telephone number.</span></span>

- <span data-ttu-id="6d407-137">L’utilisation du substitution de numéros de téléphone de compte de ressource fonctionne uniquement pour Teams utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6d407-137">The use of resource account phone number substitution only works for Teams users.</span></span> <span data-ttu-id="6d407-138">Le remplacement d’un numéro de téléphone de service est disponible pour les Skype Entreprise Ligne et Teams service.</span><span class="sxs-lookup"><span data-stu-id="6d407-138">The substitution of service phone number works for both Skype for Business Online and Teams users.</span></span>

- <span data-ttu-id="6d407-139">Le nom de l’appelant n’est envoyé que sur les appels pour lequel l’ID d’appelant remplace LineUri, un numéro de téléphone de compte de service ou de ressource, et lorsque l’appelant est Teams utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d407-139">Calling Party Name is only sent on calls where the caller ID is substituted with LineUri, a service or resource account phone number and when the caller is a Teams user.</span></span>

- <span data-ttu-id="6d407-140">Le nom de l’appelant peut avoir un maximum de 200 caractères, mais les systèmes en aval peuvent prendre en charge moins de caractères.</span><span class="sxs-lookup"><span data-stu-id="6d407-140">Calling Party Name can have a maximum of 200 characters, but downstream systems might support fewer characters.</span></span>

- <span data-ttu-id="6d407-141">Pour un routage direct, le substitution de numéros de téléphone et le nom de l’appelant sont envoyés dans l’en-tête FROM SIP.</span><span class="sxs-lookup"><span data-stu-id="6d407-141">For Direct Routing, the phone number substitution and the Calling Party Name is sent in the FROM SIP header.</span></span> <span data-ttu-id="6d407-142">Si le OnlinePstnGateway correspondant est configuré avec ForwardPai = True, l’en-tête SIP P-ENED-IDENTITY contient l’utilisateur réel de l’appel.</span><span class="sxs-lookup"><span data-stu-id="6d407-142">If the corresponding OnlinePstnGateway is configured with ForwardPai = True, the P-ASSERTED-IDENTITY SIP header will contain the real calling user.</span></span>

- <span data-ttu-id="6d407-143">EnableUserOverride a la préséance sur les autres paramètres de la stratégie, sauf si le remplacement est réglé sur Anonyme.</span><span class="sxs-lookup"><span data-stu-id="6d407-143">EnableUserOverride has precedence over other settings in the policy--unless substitution is set to Anonymous.</span></span> <span data-ttu-id="6d407-144">Par exemple, supposons que l’instance de stratégie ait le remplacement à l’aide d’un compte de ressource et qu’EnableUserOverride est définie et activée par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d407-144">For example, assume policy instance has substitution using a resource account and EnableUserOverride is set and enabled by the user.</span></span> <span data-ttu-id="6d407-145">Dans ce cas, l’ID d’appelant sortant est bloqué et anonyme est utilisé.</span><span class="sxs-lookup"><span data-stu-id="6d407-145">In this case, the outbound caller ID will be blocked and Anonymous will be used.</span></span> <span data-ttu-id="6d407-146">Si une instance de stratégie a été définie sur Anonyme et EnableUserOverride, l’ID d’appelant sortant sera toujours anonyme, quel que soit le paramètre de l’utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="6d407-146">If a policy instance has substitution set to Anonymous and EnableUserOverride is set, then the outbound caller ID will always be Anonymous, regardless of the end user setting.</span></span>

   
## <a name="inbound-caller-id"></a><span data-ttu-id="6d407-147">ID d’appelant entrant</span><span class="sxs-lookup"><span data-stu-id="6d407-147">Inbound caller ID</span></span>

<span data-ttu-id="6d407-148">Système téléphonique affiche le numéro de téléphone externe entrant comme ID de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="6d407-148">Phone System will show the incoming external phone number as the caller ID.</span></span> <span data-ttu-id="6d407-149">Si le numéro est associé à un utilisateur ou à un contact dans Azure AD ou un contact personnel, les clients Skype Entreprise et Teams afficheront l’ID d’appelant sur la base de ces informations.</span><span class="sxs-lookup"><span data-stu-id="6d407-149">If the number is associated with a user or contact in Azure AD or a personal contact, the Skype for Business and Teams clients will show the caller ID based on that information.</span></span> <span data-ttu-id="6d407-150">Si le numéro de téléphone n’est pas dans Azure AD ou un contact personnel, le nom complet fourni par le telco s’affiche s’il est disponible.</span><span class="sxs-lookup"><span data-stu-id="6d407-150">If the phone number is not in Azure AD or a personal contact, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="6d407-151">L'attribut BlockIncomingCallerID permet de bloquer l'ID d'appelant dans les appels RTC entrants.</span><span class="sxs-lookup"><span data-stu-id="6d407-151">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="6d407-152">Vous pouvez définir cet attribut, mais il n’est pas disponible pour vos utilisateurs finaux sur la page des paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d407-152">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="6d407-153">Lorsque ce paramètre est activé, l’appelant PSTN entrant s’affiche comme provenant d’anonyme.</span><span class="sxs-lookup"><span data-stu-id="6d407-153">When this setting is enabled the incoming PSTN caller will be displayed as coming from Anonymous.</span></span>
  
<span data-ttu-id="6d407-154">Pour bloquer l’ID d’appelant entrant, [consultez Définir l’ID d’appelant d’un utilisateur.](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="6d407-154">To block the inbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6d407-155">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="6d407-155">Related topics</span></span>
[<span data-ttu-id="6d407-156">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="6d407-156">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="6d407-157">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="6d407-157">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="6d407-158">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="6d407-158">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="6d407-159">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="6d407-159">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="6d407-160">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="6d407-160">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
