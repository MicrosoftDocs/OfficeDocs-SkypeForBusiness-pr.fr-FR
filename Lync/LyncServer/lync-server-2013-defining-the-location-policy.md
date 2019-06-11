---
title: 'Lync Server 2013: définition de la stratégie d’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b0e9aca4b3e66202d6b3c4a47b90db4f207fda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="9729c-102">Définition de la stratégie d’emplacement pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9729c-102">Defining the location policy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9729c-103">_**Dernière modification de la rubrique:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="9729c-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="9729c-104">Chaque stratégie d’emplacement renferme les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9729c-104">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="9729c-105">**Services d’urgence activés**</span><span class="sxs-lookup"><span data-stu-id="9729c-105">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="9729c-106">Lorsque cette valeur est **Oui**, le client est activé pour E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="9729c-106">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="9729c-107">Lors de l’inscription d’un client, ce dernier tente d’acquérir un emplacement auprès du service d’information d’emplacement et inclut les informations d’emplacement dans le cadre d’un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="9729c-107">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="9729c-108">**Emplacement requis**</span><span class="sxs-lookup"><span data-stu-id="9729c-108">**Location Required**</span></span>  
    <span data-ttu-id="9729c-109">Ce paramètre est utilisé uniquement lorsque l’option **services d’urgence** est définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="9729c-109">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="9729c-110">Vous pouvez configurer le paramètre de l' **emplacement requis** pour définir le comportement du client.</span><span class="sxs-lookup"><span data-stu-id="9729c-110">You can configure the **Location Required** setting to define the client behavior.</span></span> <span data-ttu-id="9729c-111">Si vous sélectionnez \*\*Non \*\*, l’utilisateur ne sera pas invité à entrer un emplacement.</span><span class="sxs-lookup"><span data-stu-id="9729c-111">Setting the value to **No** means that the user will not be prompted for a location.</span></span> <span data-ttu-id="9729c-112">Si vous sélectionnez \*\*Oui \*\*, l’utilisateur sera invité à entrer un emplacement, mais pourra ignorer le message d’invite.</span><span class="sxs-lookup"><span data-stu-id="9729c-112">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="9729c-113">Si vous sélectionnez \*\*Clause d’exclusion de responsabilité \*\*, l’utilisateur sera invité à entrer un emplacement, et une notification d’exclusion s’affichera également s’il essaie d’ignorer le message d’invite.</span><span class="sxs-lookup"><span data-stu-id="9729c-113">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="9729c-114">Dans tous les cas, l'utilisateur peut continuer d'utiliser le client.</span><span class="sxs-lookup"><span data-stu-id="9729c-114">In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9729c-p103">Le texte de la clause d’exclusion de responsabilité ne s’affiche pas si un utilisateur a entré manuellement un emplacement avant d’avoir été activé pour E9-1-1. Les mises à jour apportées à ce texte ne s’afficheront pas pour les utilisateurs ayant déjà pris connaissance de la clause d’exclusion de responsabilité. </span><span class="sxs-lookup"><span data-stu-id="9729c-p103">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="9729c-117">**Clause d’exclusion de responsabilité du service d’urgence**</span><span class="sxs-lookup"><span data-stu-id="9729c-117">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="9729c-118">Ce paramètre spécifie la clause d’exclusion de responsabilité qui s’affiche si les utilisateurs ignorent l’invite pour un emplacement.</span><span class="sxs-lookup"><span data-stu-id="9729c-118">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="9729c-119">Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour définir différentes exclusions de responsabilité pour différents paramètres régionaux ou ensembles d’utilisateurs différents.</span><span class="sxs-lookup"><span data-stu-id="9729c-119">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9729c-120">Ce paramètre de stratégie d’emplacement est différent de celui de Lync Server 2010, à partir duquel vous avez utilisé l’applet de passe <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> pour définir une exclusion de responsabilité globale pour l’ensemble de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="9729c-120">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="9729c-121">S’il existe déjà une clause d’exclusion de responsabilité globale, vous devez spécifier ce démenti dans la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="9729c-121">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="9729c-122">Autrement dit, Lync Server 2013 utilise uniquement les exclusions de responsabilité spécifiées dans la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="9729c-122">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="9729c-123">**Chaîne de numérotation d’urgence**</span><span class="sxs-lookup"><span data-stu-id="9729c-123">**Emergency Dial String**</span></span>  
    <span data-ttu-id="9729c-124">Cette chaîne de numérotation (moins le "+" au début, mais y compris la normalisation réalisée par le plan de numérotation de l’utilisateur Lync) signifie qu’un appel est un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="9729c-124">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="9729c-125">La **chaîne de numérotation d’urgence** oblige le client à inclure dans l’appel les informations d’emplacement et de rappel.</span><span class="sxs-lookup"><span data-stu-id="9729c-125">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9729c-126">Si votre organisation n’utilise pas un préfixe d’accès aux lignes externes, vous n’avez pas besoin de créer une règle de normalisation de plan de numérotation correspondante qui ajoute «+» à la chaîne 911 avant d’envoyer l’appel vers le routage sortant sur un serveur de pool Lync. le "+" sera automatiquement ajouté par le client Lync en raison de la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="9729c-126">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="9729c-127">Toutefois, si votre site utilise un préfixe d’accès externe, vous devez ajouter une règle de normalisation à la stratégie de plan de numérotation appropriée qui élimine le préfixe d’accès externe et ajoute le signe «+».</span><span class="sxs-lookup"><span data-stu-id="9729c-127">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="9729c-128">Par exemple, si votre emplacement utilise un préfixe d’accès externe de 9 et qu’un utilisateur&nbsp;compose 9 911 pour passer un appel d’urgence, le client utilise sa stratégie de plan de numérotation pour normaliser cette opération sur + 911 avant que le numéro composé soit évalué par les itinéraires dans l’emplacement de l’appelant. tournage.</span><span class="sxs-lookup"><span data-stu-id="9729c-128">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="9729c-129">**Masques de chaînes de numérotation d’urgence**</span><span class="sxs-lookup"><span data-stu-id="9729c-129">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="9729c-130">Liste séparée par des virgules des chaînes de numérotation traduites dans la chaîne de numérotation de **secours**spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9729c-130">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="9729c-131">Par exemple, vous souhaiterez peut-être ajouter 112, qui est le numéro de service d’urgence pour la plupart des services d’Europe.</span><span class="sxs-lookup"><span data-stu-id="9729c-131">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="9729c-132">Un utilisateur de Lync à partir de l’Europe peut ne pas savoir que 911 est le numéro d’urgence des États-Unis et peut 112 composer le même résultat.</span><span class="sxs-lookup"><span data-stu-id="9729c-132">A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="9729c-133">Comme pour la chaîne de numérotation d’urgence, n’incluez pas de "+" devant chaque numéro et, si vous utilisez des codes d’accès de ligne externe, assurez-vous que la stratégie de plan de numérotation de l’utilisateur dispose de règles de normalisation pour supprimer le code d’accès.</span><span class="sxs-lookup"><span data-stu-id="9729c-133">As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="9729c-134">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="9729c-134">**PSTN Usage**</span></span>  
    <span data-ttu-id="9729c-135">Nom de l’utilisation PSTN qui contient les chemins de routage qui déterminent la jonction SIP, la passerelle PSTN ou la passerelle ELIN vers laquelle les appels seront acheminés.</span><span class="sxs-lookup"><span data-stu-id="9729c-135">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9729c-p109">Seule une utilisation peut être affectée à une stratégie d’emplacement. Cette utilisation PSTN remplace les utilisations PSTN affectées à la stratégie de voix de l’utilisateur, mais s’applique uniquement aux appels passés à la chaîne de numérotation d’urgence ou à l’un des masques de chaîne de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="9729c-p109">Only one usage can be assigned to a location policy. This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="9729c-138">**URI de notification**</span><span class="sxs-lookup"><span data-stu-id="9729c-138">**Notification URI**</span></span>  
    <span data-ttu-id="9729c-p110">Indique les URI SIP des membres du personnel de sécurité qui reçoivent une notification de messagerie instantanée en cas d’appel d’urgence. Les groupes de distribution sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="9729c-p110">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="9729c-141">**URI de la conférence**</span><span class="sxs-lookup"><span data-stu-id="9729c-141">**Conference URI**</span></span>  
    <span data-ttu-id="9729c-142">Indique le numéro SDA (en général, numéro de service de sécurité) qui doit participer à la conférence en cas d’appel d’urgence.  </span><span class="sxs-lookup"><span data-stu-id="9729c-142">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="9729c-143">**Mode Conférence**</span><span class="sxs-lookup"><span data-stu-id="9729c-143">**Conference Mode**</span></span>  
    <span data-ttu-id="9729c-144">Indique si l’URI de conférence participera à l’appel d’urgence via une communication unidirectionnelle ou bidirectionnelle. </span><span class="sxs-lookup"><span data-stu-id="9729c-144">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="9729c-145">**Intervalle d’actualisation d’emplacement**</span><span class="sxs-lookup"><span data-stu-id="9729c-145">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="9729c-146">Spécifie la durée (en heures) entre les demandes des clients pour une mise à jour de l’emplacement du service d’informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="9729c-146">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="9729c-147">La valeur peut être comprise entre 1 et 12.</span><span class="sxs-lookup"><span data-stu-id="9729c-147">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="9729c-148">La valeur par défaut est 4.</span><span class="sxs-lookup"><span data-stu-id="9729c-148">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

