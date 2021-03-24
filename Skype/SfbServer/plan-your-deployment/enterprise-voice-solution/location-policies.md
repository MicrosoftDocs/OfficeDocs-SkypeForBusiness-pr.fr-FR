---
title: Planifier des stratégies d’emplacement pour Skype Entreprise Server
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Lisez cette rubrique pour découvrir comment planifier des stratégies d’emplacement pour un déploiement des services d’urgence améliorés (E9-1-1) dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 3d9c574d18351594d9773f02770e960c993ae401
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101450"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="8755e-103">Planifier des stratégies d’emplacement pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8755e-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="8755e-104">Lisez cette rubrique pour découvrir comment planifier des stratégies d’emplacement pour un déploiement des services d’urgence améliorés (E9-1-1) dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="8755e-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8755e-105">Skype Entreprise Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client.</span><span class="sxs-lookup"><span data-stu-id="8755e-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="8755e-106">Si vous souhaitez configurer plusieurs numéros d’urgence, vous devez suivre les informations de la zone Planifier plusieurs numéros d’urgence dans Skype Entreprise [Server](multiple-emergency-numbers.md) et configurer plusieurs numéros d’urgence dans [Skype Entreprise.](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="8755e-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="8755e-107">Vous créez des stratégies d’emplacement à l’aide du Panneau de contrôle Skype Entreprise ou de l’cmdlet [New-CsLocationPolicy.](/powershell/module/skype/new-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8755e-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="8755e-108">Pour plus d’informations, voir [Créer des stratégies d’emplacement dans Skype Entreprise Server.](../../deploy/deploy-enterprise-voice/create-location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="8755e-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="8755e-109">Chaque stratégie d’emplacement contient les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="8755e-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="8755e-110">**Activer Enhanced 9-1-1**</span><span class="sxs-lookup"><span data-stu-id="8755e-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="8755e-111">Lorsque cette valeur est activée, le client est activé pour les services d’urgence améliorés (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="8755e-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="8755e-112">Lorsqu’un client s’inscrit, il tente d’acquérir un emplacement auprès du service Informations d’emplacement et inclut les informations d’emplacement dans le cadre d’un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="8755e-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="8755e-113">**Location**</span><span class="sxs-lookup"><span data-stu-id="8755e-113">**Location**</span></span>
  
<span data-ttu-id="8755e-114">Ce paramètre est utilisé uniquement lorsque **l’enable enhanced 9-1-1** est activé.</span><span class="sxs-lookup"><span data-stu-id="8755e-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="8755e-115">Vous pouvez configurer le paramètre **Emplacement** pour définir le comportement du client comme suit :</span><span class="sxs-lookup"><span data-stu-id="8755e-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="8755e-116">Définir la valeur sur **Non** signifie que l’utilisateur ne sera pas invité à se rendre sur un emplacement.</span><span class="sxs-lookup"><span data-stu-id="8755e-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="8755e-117">Si la valeur est **Oui,** l’utilisateur est invité à se rendre sur un emplacement, mais peut ignorer l’invite.</span><span class="sxs-lookup"><span data-stu-id="8755e-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="8755e-118">La définition de la valeur sur **Disclaimer** signifie que l’utilisateur est invité à se rendre sur un emplacement et qu’une clause d’exclusion de responsabilité s’affiche s’il tente d’ignorer l’invite.</span><span class="sxs-lookup"><span data-stu-id="8755e-118">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="8755e-119">Dans tous les cas, l’utilisateur peut continuer à utiliser le client.</span><span class="sxs-lookup"><span data-stu-id="8755e-119">In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8755e-120">Le texte de la clause d’exclusion de responsabilité n’apparaît pas si un utilisateur a entré manuellement un emplacement avant d’être activé pour E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="8755e-120">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1.</span></span> <span data-ttu-id="8755e-121">Les mises à jour du texte de la clause d’exclusion de responsabilité ne seront pas vues par les utilisateurs qui ont déjà vu la clause d’exclusion de responsabilité.</span><span class="sxs-lookup"><span data-stu-id="8755e-121">Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="8755e-122">**Exclusion de responsabilité du service d’urgence amélioré**</span><span class="sxs-lookup"><span data-stu-id="8755e-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="8755e-123">Ce paramètre spécifie la clause d’exclusion de responsabilité que les utilisateurs voient s’ils font disparaître l’invite d’un emplacement.</span><span class="sxs-lookup"><span data-stu-id="8755e-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="8755e-124">Dans Skype Entreprise Server, vous pouvez utiliser la stratégie d’emplacement pour définir différentes clauses d’exclusion de responsabilité pour différents paramètres régionaux ou différents ensembles d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8755e-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="8755e-125">**Chaîne de numérotation d’urgence (numéro E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="8755e-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="8755e-126">Cette chaîne de numérotation (moins le « + » de début, mais incluant toute normalisation effectuée par le plan de numérotation de l’utilisateur) signifie qu’un appel est un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="8755e-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="8755e-127">La **chaîne de numérotation d’urgence** amène le client à inclure les informations de localisation et de rappel avec l’appel.</span><span class="sxs-lookup"><span data-stu-id="8755e-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8755e-128">Si votre organisation n’utilise pas de préfixe d’accès à une ligne externe, vous n’avez pas besoin de créer une règle de normalisation de plan de numérotation correspondante qui ajoute un « + » à la chaîne 911 avant d’envoyer l’appel au routage sortant sur un serveur exécutant Skype Entreprise Server ; Le « + » est automatiquement précédé par le client Skype Entreprise à la suite de la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="8755e-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="8755e-129">Toutefois, si votre site utilise un préfixe d’accès externe, vous devez ajouter une règle de normalisation à la stratégie de plan de numérotation applicable qui exclut le préfixe d’accès externe et ajoute le « + ».</span><span class="sxs-lookup"><span data-stu-id="8755e-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="8755e-130">Par exemple, si votre emplacement utilise un préfixe d’accès externe de 9 et qu’un utilisateur compose le 9 911 pour appeler d’urgence, le client utilisera sa stratégie de plan de numérotation pour le normaliser sur +911 avant que le numéro composé ne soit évalué par les itinéraires dans le profil d’emplacement de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8755e-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="8755e-131">**Masques de chaîne de numérotation d’urgence (masque de numérotation E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="8755e-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="8755e-132">Liste de chaînes de numérotation séparées par des points-virgules qui est traduite dans la chaîne de numérotation **d’urgence spécifiée.**</span><span class="sxs-lookup"><span data-stu-id="8755e-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="8755e-133">Par exemple, vous pouvez ajouter 112, qui est le numéro de service d’urgence pour la plupart de l’Europe.</span><span class="sxs-lookup"><span data-stu-id="8755e-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="8755e-134">Un utilisateur Skype Entreprise en visite en Europe peut ne pas savoir que le 911 est le numéro d’urgence américain, mais il peut composer le 112 et obtenir le même résultat.</span><span class="sxs-lookup"><span data-stu-id="8755e-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="8755e-135">Comme pour la chaîne de numérotation d’urgence, n’incluez pas de « + » avant chaque numéro et, si vous utilisez des codes d’accès aux lignes externes, assurez-vous que la stratégie de plan de numérotation de l’utilisateur comprend des règles de normalisation pour le dédessage du chiffre du code d’accès.</span><span class="sxs-lookup"><span data-stu-id="8755e-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="8755e-136">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="8755e-136">**PSTN usage**</span></span>
  
<span data-ttu-id="8755e-137">Nom de l’utilisation PSTN qui contient les chemins de routage qui déterminent la passerelle SIP, la passerelle PSTN ou la passerelle ELIN vers laquelle les appels d’urgence seront appelés.</span><span class="sxs-lookup"><span data-stu-id="8755e-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8755e-138">Une seule utilisation peut être affectée à une stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="8755e-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="8755e-139">Cette utilisation PSTN remplace les utilisations PSTN affectées à la stratégie de voix de l’utilisateur, mais s’applique uniquement aux appels passé à la chaîne de numérotation d’urgence ou à l’un des masques de chaîne de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="8755e-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="8755e-140">**URI de notification**</span><span class="sxs-lookup"><span data-stu-id="8755e-140">**Notification URI**</span></span>
  
<span data-ttu-id="8755e-141">Spécifie une ou plusieurs UR SIP du personnel de sécurité qui reçoit une notification de messagerie instantanée lorsqu’un appel d’urgence est passé.</span><span class="sxs-lookup"><span data-stu-id="8755e-141">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="8755e-142">Les groupes de distribution sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="8755e-142">Distribution groups are supported.</span></span>
  
 <span data-ttu-id="8755e-143">**URI de la conférence**</span><span class="sxs-lookup"><span data-stu-id="8755e-143">**Conference URI**</span></span>
  
<span data-ttu-id="8755e-144">Spécifie un numéro SDN (numéro de service de sécurité) qui doit être pris en compte lors d’un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="8755e-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="8755e-145">**Mode conférence**</span><span class="sxs-lookup"><span data-stu-id="8755e-145">**Conference Mode**</span></span>
  
<span data-ttu-id="8755e-146">Spécifie si l’URI de conférence sera pris en compte dans l’appel d’urgence à l’aide d’une communication à sens seul ou double.</span><span class="sxs-lookup"><span data-stu-id="8755e-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="8755e-147">**Intervalle d’actualisation de l’emplacement**</span><span class="sxs-lookup"><span data-stu-id="8755e-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="8755e-148">Spécifie la durée (en heures) entre les demandes des clients pour une mise à jour d’emplacement à partir du service Informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="8755e-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="8755e-149">La valeur peut être définie sur n’importe quelle valeur entre 1 et 12.</span><span class="sxs-lookup"><span data-stu-id="8755e-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="8755e-150">La valeur par défaut est 4.</span><span class="sxs-lookup"><span data-stu-id="8755e-150">The default value is 4.</span></span>
