---
title: Planifier des politiques d’emplacement pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Pour plus d’informations sur la planification de stratégies de géolocalisation pour un déploiement Enhanced Emergency Services (E9-1-1) dans Skype entreprise Server, voir la rubrique voix.
ms.openlocfilehash: 8f21a5a0f54fbeaca4c46ed51bf4dafe4c2a3dcb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276753"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="50a9f-103">Planifier des politiques d’emplacement pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="50a9f-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="50a9f-104">Pour plus d’informations sur la planification de stratégies de géolocalisation pour un déploiement Enhanced Emergency Services (E9-1-1) dans Skype entreprise Server, voir la rubrique voix.</span><span class="sxs-lookup"><span data-stu-id="50a9f-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="50a9f-105">Skype entreprise Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client.</span><span class="sxs-lookup"><span data-stu-id="50a9f-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="50a9f-106">Si vous voulez configurer plusieurs numéros d’urgence, vous devez suivre les informations de l’offre [plan pour plusieurs numéros d’urgence dans Skype entreprise Server](multiple-emergency-numbers.md) et [configurer plusieurs numéros d’urgence dans Skype entreprise](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="50a9f-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="50a9f-107">Vous pouvez créer des stratégies d’emplacement à l’aide du panneau de configuration Skype pour les entreprises ou à l’aide de l’applet [de commande New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="50a9f-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="50a9f-108">Pour plus d’informations, reportez-vous à la rubrique [création de stratégies d’emplacement dans Skype entreprise Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="50a9f-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="50a9f-109">Chaque stratégie d’emplacement renferme les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="50a9f-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="50a9f-110">**Activation d'Enhanced 9-1-1**</span><span class="sxs-lookup"><span data-stu-id="50a9f-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="50a9f-111">Si cette valeur est activée, le client est activé pour les services d’urgence étendus (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="50a9f-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="50a9f-112">Lors de l’inscription d’un client, ce dernier tente d’acquérir un emplacement auprès du service d’information d’emplacement et inclut les informations d’emplacement dans le cadre d’un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="50a9f-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="50a9f-113">**Emplacement**</span><span class="sxs-lookup"><span data-stu-id="50a9f-113">**Location**</span></span>
  
<span data-ttu-id="50a9f-114">Ce paramètre est utilisé uniquement lorsque l'**activation d'Enhanced 9-1-1** est activée. </span><span class="sxs-lookup"><span data-stu-id="50a9f-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="50a9f-115">Vous pouvez configurer le paramètre **Emplacement** pour définir le comportement du client de la manière suivante :   </span><span class="sxs-lookup"><span data-stu-id="50a9f-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="50a9f-116">Si vous sélectionnez \*\*Non \*\*, l’utilisateur ne sera pas invité à entrer un emplacement.</span><span class="sxs-lookup"><span data-stu-id="50a9f-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="50a9f-117">Si vous sélectionnez \*\*Oui \*\*, l’utilisateur sera invité à entrer un emplacement, mais pourra ignorer le message d’invite.</span><span class="sxs-lookup"><span data-stu-id="50a9f-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="50a9f-p104">Si vous sélectionnez \*\*Clause d’exclusion de responsabilité \*\*, l’utilisateur sera invité à entrer un emplacement, et une notification d’exclusion s’affichera également s’il essaie d’ignorer le message d’invite. Dans tous les cas, l'utilisateur peut continuer d'utiliser le client.</span><span class="sxs-lookup"><span data-stu-id="50a9f-p104">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="50a9f-p105">Le texte de la clause d’exclusion de responsabilité ne s’affiche pas si un utilisateur a entré manuellement un emplacement avant d’avoir été activé pour E9-1-1. Les mises à jour apportées à ce texte ne s’afficheront pas pour les utilisateurs ayant déjà pris connaissance de la clause d’exclusion de responsabilité. </span><span class="sxs-lookup"><span data-stu-id="50a9f-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="50a9f-122">**Clause d’exclusion de responsabilité du service d’urgence**</span><span class="sxs-lookup"><span data-stu-id="50a9f-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="50a9f-123">Ce paramètre spécifie la clause d’exclusion de responsabilité qui s’affiche si les utilisateurs ignorent l’invite pour un emplacement.</span><span class="sxs-lookup"><span data-stu-id="50a9f-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="50a9f-124">Dans Skype entreprise Server, vous pouvez utiliser la stratégie d’emplacement pour définir différentes exclusions de responsabilité pour différentes régions ou ensembles d’utilisateurs différents.</span><span class="sxs-lookup"><span data-stu-id="50a9f-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="50a9f-125">**Chaîne de numérotation d’urgence (numéro E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="50a9f-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="50a9f-126">Cette chaîne de numérotation (moins le "+" au début, mais y compris la normalisation réalisée par le plan de numérotation de l’utilisateur) signifie qu’un appel est un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="50a9f-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="50a9f-127">La **chaîne de numérotation d’urgence** oblige le client à inclure dans l’appel les informations d’emplacement et de rappel.</span><span class="sxs-lookup"><span data-stu-id="50a9f-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="50a9f-128">Si votre organisation n’utilise pas un préfixe d’accès aux lignes externes, vous n’avez pas besoin de créer une règle de normalisation de plan de numérotation correspondante qui ajoute «+» à la chaîne 911 avant d’envoyer l’appel vers le routage sortant sur un serveur exécutant Skype entreprise Server. le "+" sera automatiquement ajouté par le client Skype entreprise en raison de la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="50a9f-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="50a9f-129">Toutefois, si votre site utilise un préfixe d’accès externe, vous devez ajouter une règle de normalisation à la stratégie de plan de numérotation appropriée qui élimine le préfixe d’accès externe et ajoute le signe «+».</span><span class="sxs-lookup"><span data-stu-id="50a9f-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="50a9f-130">Par exemple, si votre emplacement utilise un préfixe d’accès externe de 9 et qu’un utilisateur compose 9 911 pour passer un appel d’urgence, le client utilisera sa stratégie de plan de numérotation pour normaliser cette opération sur + 911 avant que le numéro composé soit évalué par les itinéraires dans le profil de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="50a9f-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="50a9f-131">**Masques de chaîne de numérotation d’urgence (masque E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="50a9f-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="50a9f-132">Liste séparée par des virgules des chaînes de numérotation traduites dans la chaîne de numérotation de **secours**spécifiée.</span><span class="sxs-lookup"><span data-stu-id="50a9f-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="50a9f-133">Par exemple, vous souhaiterez peut-être ajouter 112, qui est le numéro de service d’urgence pour la plupart des services d’Europe.</span><span class="sxs-lookup"><span data-stu-id="50a9f-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="50a9f-134">Un utilisateur de Skype entreprise en Europe ne sait pas que 911 correspond au numéro d’urgence des États-Unis, mais il peut composer 112 et obtenir le même résultat.</span><span class="sxs-lookup"><span data-stu-id="50a9f-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="50a9f-135">Comme pour la chaîne de numérotation d’urgence, n’incluez pas de "+" devant chaque numéro et, si vous utilisez des codes d’accès de ligne externe, assurez-vous que la stratégie de plan de numérotation de l’utilisateur dispose de règles de normalisation pour supprimer le code d’accès.</span><span class="sxs-lookup"><span data-stu-id="50a9f-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="50a9f-136">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="50a9f-136">**PSTN usage**</span></span>
  
<span data-ttu-id="50a9f-137">Nom de l’utilisation PSTN qui contient les chemins de routage qui déterminent la jonction SIP, la passerelle PSTN ou la passerelle ELIN vers laquelle les appels seront acheminés.</span><span class="sxs-lookup"><span data-stu-id="50a9f-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="50a9f-138">Seule une utilisation peut être affectée à une stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="50a9f-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="50a9f-139">Cette utilisation PSTN remplace les utilisations RTC attribuées à la stratégie vocale de l’utilisateur, mais ne s’applique qu’aux appels passés à la chaîne de numérotation d’urgence ou à un des masques de chaînes de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="50a9f-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="50a9f-140">**URI de notification**</span><span class="sxs-lookup"><span data-stu-id="50a9f-140">**Notification URI**</span></span>
  
<span data-ttu-id="50a9f-p111">Indique les URI SIP des membres du personnel de sécurité qui reçoivent une notification de messagerie instantanée en cas d’appel d’urgence. Les groupes de distribution sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="50a9f-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="50a9f-143">**URI de la conférence**</span><span class="sxs-lookup"><span data-stu-id="50a9f-143">**Conference URI**</span></span>
  
<span data-ttu-id="50a9f-144">Indique le numéro SDA (en général, numéro de service de sécurité) qui doit participer à la conférence en cas d’appel d’urgence.  </span><span class="sxs-lookup"><span data-stu-id="50a9f-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="50a9f-145">**Mode Conférence**</span><span class="sxs-lookup"><span data-stu-id="50a9f-145">**Conference Mode**</span></span>
  
<span data-ttu-id="50a9f-146">Indique si l’URI de conférence participera à l’appel d’urgence via une communication unidirectionnelle ou bidirectionnelle. </span><span class="sxs-lookup"><span data-stu-id="50a9f-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="50a9f-147">**Intervalle d’actualisation d’emplacement**</span><span class="sxs-lookup"><span data-stu-id="50a9f-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="50a9f-148">Spécifie la durée (en heures) entre les demandes des clients pour une mise à jour de l’emplacement du service d’informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="50a9f-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="50a9f-149">La valeur peut être comprise entre 1 et 12.</span><span class="sxs-lookup"><span data-stu-id="50a9f-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="50a9f-150">La valeur par défaut est 4.</span><span class="sxs-lookup"><span data-stu-id="50a9f-150">The default value is 4.</span></span>
  

