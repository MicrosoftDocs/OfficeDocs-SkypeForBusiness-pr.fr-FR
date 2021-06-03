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
description: L’ID d’appelant peut être contrôlé pour les appels entrants et sortants pour les utilisateurs Système téléphonique à l’aide d’une stratégie appelée CallingLineIdentity.
ms.openlocfilehash: 43d3d6633ca46485aa111a7d97b9bd37b0547818
ms.sourcegitcommit: 02e243d6c58eab463a00ed45dadd80112087006e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52723545"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="8d3eb-103">Comment utiliser un ID d'appelant dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="8d3eb-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="8d3eb-104">L’ID d’appelant se compose de deux informations identifiables :</span><span class="sxs-lookup"><span data-stu-id="8d3eb-104">Caller ID consists of two user-facing identifiable pieces of information:</span></span>

- <span data-ttu-id="8d3eb-105">Un numéro de téléphone (généralement appelé CLID ou ID de ligne d’appel).</span><span class="sxs-lookup"><span data-stu-id="8d3eb-105">A phone number (typically referred to as CLID or calling line ID).</span></span> <span data-ttu-id="8d3eb-106">Il s’agit du numéro de téléphone commuté public (PSTN) présenté comme identification de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-106">This is the Public Switched Telephone Number (PSTN) presented as the identification of the caller.</span></span>

- <span data-ttu-id="8d3eb-107">Nom de l’appelant (généralement appelé CNAM).</span><span class="sxs-lookup"><span data-stu-id="8d3eb-107">A Calling party name (typically referred to as CNAM).</span></span> 
  
<span data-ttu-id="8d3eb-108">La fonctionnalité d’ID d’appelant est disponible pour tous Système téléphonique utilisateurs quelle que soit l’option de connectivité PSTN :</span><span class="sxs-lookup"><span data-stu-id="8d3eb-108">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity option:</span></span>

- <span data-ttu-id="8d3eb-109">Forfaits d’appels Microsoft</span><span class="sxs-lookup"><span data-stu-id="8d3eb-109">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="8d3eb-110">Routage direct via le système téléphonique</span><span class="sxs-lookup"><span data-stu-id="8d3eb-110">Phone System Direct Routing</span></span> 
  
<span data-ttu-id="8d3eb-111">Vous pouvez contrôler l’ID d’appelant pour les appels entrants et sortants à l’aide d’une stratégie appelée CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-111">You can control Caller ID for both inbound and outbound calls by using a policy called CallingLineIdentity.</span></span> <span data-ttu-id="8d3eb-112">Pour plus d’informations, voir [Plus d’informations sur l’ID de ligne d’appel et le nom de l’appelant.](more-about-calling-line-id-and-calling-party-name.md)</span><span class="sxs-lookup"><span data-stu-id="8d3eb-112">For more information, see [More about Calling Line ID and Calling Party Name](more-about-calling-line-id-and-calling-party-name.md).</span></span>

  
## <a name="outbound-pstn-caller-id"></a><span data-ttu-id="8d3eb-113">ID d’appelant PSTN sortant</span><span class="sxs-lookup"><span data-stu-id="8d3eb-113">Outbound PSTN caller ID</span></span>

<span data-ttu-id="8d3eb-114">Pour l’ID d’appelant PSTN sortant, les options suivantes sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-114">For the outbound PSTN caller ID, the following options are available.</span></span> 
  
- <span data-ttu-id="8d3eb-115">Numéro de téléphone affecté à l’utilisateur (valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="8d3eb-115">The telephone number assigned to the user, which is the default.</span></span>

- <span data-ttu-id="8d3eb-116">Anonyme, disponible en supprimant la présentation du numéro PSTN de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-116">Anonymous, which is available by removing the presentation of the user’s PSTN number.</span></span> 

- <span data-ttu-id="8d3eb-117">Un numéro de téléphone de substitution, qui peut être :</span><span class="sxs-lookup"><span data-stu-id="8d3eb-117">A substitute phone number, which can be:</span></span>

  - <span data-ttu-id="8d3eb-118">Un numéro de téléphone classé comme service et numéro gratuit dans l’inventaire de numéros de téléphone de vos forfaits d’appels.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-118">A telephone number that is classified as a service and toll-free number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="8d3eb-119">Elle est généralement affectée à une Teams Standard automatique ou à une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-119">It is usually assigned to a Teams Auto Attendant or Call Queue.</span></span>

  - <span data-ttu-id="8d3eb-120">Un numéro de téléphone local via un routage direct affecté à un compte de ressource utilisé par une Teams Standard automatique ou une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-120">An on-premises telephone number through Direct Routing that is assigned to a resource account used by a Teams Auto Attendant or Call Queue.</span></span> 

- <span data-ttu-id="8d3eb-121">Nom de l’appelant ou nom de l’appelant dans l’appel RSTN sortant.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-121">The Calling Party Name or CNAM set on the outbound PSTN call.</span></span>  
    
<span data-ttu-id="8d3eb-122">Pour plus d’informations, [voir Définir l’ID d’appelant d’un utilisateur.](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="8d3eb-122">For more information, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="8d3eb-123">Contrôle de l’ID d’appelant sortant par l’utilisateur final</span><span class="sxs-lookup"><span data-stu-id="8d3eb-123">End user control of outbound caller ID</span></span>

<span data-ttu-id="8d3eb-124">Les utilisateurs peuvent définir leur paramètre d’ID d’appelant sur **Anonyme** en paramètres d’attribut EnableUserOverride.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-124">Users can change their caller ID setting to **Anonymous** by setting the EnableUserOverride attribute.</span></span> 

<span data-ttu-id="8d3eb-125">Si l’ID d’appelant sortant est définie sur Anonyme, le contrôle EnableUserOverride n’a aucun effet et l’ID d’appelant est toujours définie sur Anonyme.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-125">If the outbound caller ID is set to Anonymous, the EnableUserOverride has no effect and the caller ID is always set to Anonymous.</span></span> <span data-ttu-id="8d3eb-126">La valeur par défaut de EnableUserOverride est False.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-126">The default value of EnableUserOverride is False.</span></span>

<span data-ttu-id="8d3eb-127">Vos utilisateurs finaux peuvent définir leur ID d’appelant sur Anonyme en sélectionnant **Paramètres > Appels,** puis sous **ID** de l’appelant, sélectionnez Masquer mon numéro de téléphone et les informations de profil pour tous **les appels.**</span><span class="sxs-lookup"><span data-stu-id="8d3eb-127">Your end users can set their caller ID to Anonymous by going to **Settings > Calls**, and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>

### <a name="notes"></a><span data-ttu-id="8d3eb-128">Remarques</span><span class="sxs-lookup"><span data-stu-id="8d3eb-128">Notes</span></span>

<span data-ttu-id="8d3eb-129">Tenez compte des points suivants :</span><span class="sxs-lookup"><span data-stu-id="8d3eb-129">Keep the following in mind:</span></span>

- <span data-ttu-id="8d3eb-130">Vous ne pouvez pas affecter les types suivants de numéros de téléphone à l’ID d’appelant sortant :</span><span class="sxs-lookup"><span data-stu-id="8d3eb-130">You can't assign the following types of phone numbers for the outbound caller ID:</span></span>

  - <span data-ttu-id="8d3eb-131">Les numéros de téléphone classés comme utilisateurs dans l’inventaire de numéros de téléphone de vos forfaits d’appels.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-131">Any phone numbers that are classified as a user in your Calling Plans telephone number inventory.</span></span>

  - <span data-ttu-id="8d3eb-132">Tout numéro de téléphone local via un routage direct affecté à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-132">Any on-premises telephone number via Direct Routing that is assigned to a user.</span></span>

  - <span data-ttu-id="8d3eb-133">Un Skype Entreprise Server numéro de téléphone local.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-133">A Skype for Business Server on-premises telephone number.</span></span>

- <span data-ttu-id="8d3eb-134">L’utilisation du substitution de numéros de téléphone de compte de ressource fonctionne uniquement pour Teams utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-134">The use of resource account phone number substitution only works for Teams users.</span></span> <span data-ttu-id="8d3eb-135">Le remplacement d’un numéro de téléphone de service est disponible pour les Skype Entreprise Ligne et Teams service.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-135">The substitution of service phone number works for both Skype for Business Online and Teams users.</span></span>

- <span data-ttu-id="8d3eb-136">Le nom de l’appelant n’est envoyé que sur les appels pour lequel l’ID d’appelant remplace LineUri, un numéro de téléphone de compte de service ou de ressource, et lorsque l’appelant est un Teams utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-136">Calling Party Name is only sent on calls where the caller ID is substituted with LineUri, a service or resource account phone number and when the caller is a Teams user.</span></span>

- <span data-ttu-id="8d3eb-137">Le nom de l’appelant peut avoir un maximum de 200 caractères, mais les systèmes en aval peuvent prendre en charge moins de caractères.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-137">Calling Party Name can have a maximum of 200 characters, but downstream systems might support fewer characters.</span></span>

- <span data-ttu-id="8d3eb-138">Pour un routage direct, le substitution de numéros de téléphone et le nom de l’appelant sont envoyés dans l’en-tête FROM SIP.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-138">For Direct Routing, the phone number substitution and the Calling Party Name is sent in the FROM SIP header.</span></span> <span data-ttu-id="8d3eb-139">Si le OnlinePstnGateway correspondant est configuré avec ForwardPai = True, l’en-tête SIP P-ENED-IDENTITY contient l’utilisateur réel de l’appel.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-139">If the corresponding OnlinePstnGateway is configured with ForwardPai = True, the P-ASSERTED-IDENTITY SIP header will contain the real calling user.</span></span>

- <span data-ttu-id="8d3eb-140">EnableUserOverride a la préséance sur les autres paramètres de la stratégie, sauf si le remplacement est réglé sur Anonyme.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-140">EnableUserOverride has precedence over other settings in the policy--unless substitution is set to Anonymous.</span></span> <span data-ttu-id="8d3eb-141">Par exemple, supposons que l’instance de stratégie ait le remplacement à l’aide d’un compte de ressource et qu’EnableUserOverride est définie et activée par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-141">For example, assume policy instance has substitution using a resource account and EnableUserOverride is set and enabled by the user.</span></span> <span data-ttu-id="8d3eb-142">Dans ce cas, l’ID d’appelant sortant est bloqué et anonyme est utilisé.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-142">In this case, the outbound caller ID will be blocked and Anonymous will be used.</span></span> <span data-ttu-id="8d3eb-143">Si une instance de stratégie a été définie sur Anonyme et EnableUserOverride, l’ID d’appelant sortant sera toujours anonyme, quel que soit le paramètre de l’utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-143">If a policy instance has substitution set to Anonymous and EnableUserOverride is set, then the outbound caller ID will always be Anonymous, regardless of the end user setting.</span></span>

   
## <a name="inbound-caller-id"></a><span data-ttu-id="8d3eb-144">ID d’appelant entrant</span><span class="sxs-lookup"><span data-stu-id="8d3eb-144">Inbound caller ID</span></span>

<span data-ttu-id="8d3eb-145">Système téléphonique affiche le numéro de téléphone externe entrant comme ID de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-145">Phone System will show the incoming external phone number as the caller ID.</span></span> <span data-ttu-id="8d3eb-146">Si le numéro est associé à un utilisateur ou à un contact dans Azure AD ou un contact personnel, les clients Skype Entreprise et Teams afficheront l’ID d’appelant sur la base de ces informations.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-146">If the number is associated with a user or contact in Azure AD or a personal contact, the Skype for Business and Teams clients will show the caller ID based on that information.</span></span> <span data-ttu-id="8d3eb-147">Si le numéro de téléphone n’est pas dans Azure AD ou un contact personnel, le nom complet fourni par le telco s’affiche s’il est disponible.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-147">If the phone number is not in Azure AD or a personal contact, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="8d3eb-148">L'attribut BlockIncomingCallerID permet de bloquer l'ID d'appelant dans les appels RTC entrants.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-148">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="8d3eb-149">Vous pouvez définir cet attribut, mais il n’est pas disponible pour vos utilisateurs finaux sur la page des paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-149">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="8d3eb-150">Lorsque ce paramètre est activé, l’appelant PSTN entrant s’affiche comme provenant d’anonyme.</span><span class="sxs-lookup"><span data-stu-id="8d3eb-150">When this setting is enabled the incoming PSTN caller will be displayed as coming from Anonymous.</span></span>
  
<span data-ttu-id="8d3eb-151">Pour bloquer l’ID d’appelant entrant, [consultez Définir l’ID d’appelant d’un utilisateur.](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="8d3eb-151">To block the inbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8d3eb-152">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="8d3eb-152">Related topics</span></span>
[<span data-ttu-id="8d3eb-153">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="8d3eb-153">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="8d3eb-154">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="8d3eb-154">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="8d3eb-155">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="8d3eb-155">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="8d3eb-156">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="8d3eb-156">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="8d3eb-157">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8d3eb-157">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
