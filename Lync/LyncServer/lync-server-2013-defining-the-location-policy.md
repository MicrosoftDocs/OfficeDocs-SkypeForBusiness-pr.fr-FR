---
title: 'Lync Server 2013 : définition de la stratégie d’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64c164f24f0f2c140a140b7343dd526979cc2bff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="e9470-102">Définition de la stratégie d’emplacement pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9470-102">Defining the location policy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9470-103">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="e9470-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="e9470-104">Chaque stratégie d’emplacement contient les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e9470-104">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="e9470-105">**Services d’urgence activés**</span><span class="sxs-lookup"><span data-stu-id="e9470-105">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="e9470-106">Si cette valeur est **Oui**, le client est activé pour E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="e9470-106">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="e9470-107">Lorsqu’un client s’inscrit, il tente d’acquérir un emplacement à partir du service d’informations d’emplacement et inclut les informations d’emplacement dans le cadre d’un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e9470-107">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="e9470-108">**Emplacement requis**</span><span class="sxs-lookup"><span data-stu-id="e9470-108">**Location Required**</span></span>  
    <span data-ttu-id="e9470-109">Ce paramètre est utilisé uniquement lorsque l’option **services d’urgence activé** est définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="e9470-109">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="e9470-110">Vous pouvez configurer le paramètre **emplacement requis** pour définir le comportement du client.</span><span class="sxs-lookup"><span data-stu-id="e9470-110">You can configure the **Location Required** setting to define the client behavior.</span></span> <span data-ttu-id="e9470-111">La définition de la valeur sur **non** signifie que l’utilisateur ne sera pas invité à entrer un emplacement.</span><span class="sxs-lookup"><span data-stu-id="e9470-111">Setting the value to **No** means that the user will not be prompted for a location.</span></span> <span data-ttu-id="e9470-112">La définition de la valeur sur **Oui** signifie que l’utilisateur sera invité à entrer un emplacement, mais peut ignorer l’invite.</span><span class="sxs-lookup"><span data-stu-id="e9470-112">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="e9470-113">Si la valeur est définie sur **clause d’exclusion de responsabilité** , l’utilisateur sera invité à entrer un emplacement et une clause d’exclusion de responsabilité s’affichera si les utilisateurs essaient de le faire.</span><span class="sxs-lookup"><span data-stu-id="e9470-113">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="e9470-114">Dans tous les cas, l’utilisateur peut continuer à utiliser le client.</span><span class="sxs-lookup"><span data-stu-id="e9470-114">In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9470-115">Le texte de la clause d’exclusion de responsabilité n’apparaît pas si un utilisateur a entré manuellement un emplacement avant d’être activé pour E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="e9470-115">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1.</span></span> <span data-ttu-id="e9470-116">Les mises à jour du texte de la clause d’exclusion de responsabilité ne seront pas visibles par les utilisateurs qui ont déjà consulté la clause d’exclusion de responsabilité.</span><span class="sxs-lookup"><span data-stu-id="e9470-116">Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="e9470-117">**Clause d’exclusion de responsabilité de service d’urgence améliorée**</span><span class="sxs-lookup"><span data-stu-id="e9470-117">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="e9470-118">Ce paramètre spécifie la clause d’exclusion de responsabilité que les utilisateurs voient si l’invite pour un emplacement est rejetée.</span><span class="sxs-lookup"><span data-stu-id="e9470-118">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="e9470-119">Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour définir différents clauses d’exclusion de responsabilité pour différents paramètres régionaux ou groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e9470-119">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9470-120">Ce paramètre de stratégie d’emplacement diffère de Lync Server 2010, où vous avez utilisé l’applet de commande <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> pour définir une clause d’exclusion de responsabilité globale pour l’ensemble de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="e9470-120">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="e9470-121">S’il existe déjà une clause d’exclusion de responsabilité globale, vous devez spécifier cette clause d’exclusion de responsabilité dans la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="e9470-121">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="e9470-122">En d’autres conditions, Lync Server 2013 utilise uniquement les clauses d’exclusion de responsabilité spécifiées dans la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="e9470-122">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="e9470-123">**Chaîne de numérotation d’urgence**</span><span class="sxs-lookup"><span data-stu-id="e9470-123">**Emergency Dial String**</span></span>  
    <span data-ttu-id="e9470-124">Cette chaîne de numérotation (moins le « + » de début, mais y compris toute normalisation réalisée par le plan de numérotation de l’utilisateur Lync) signifie qu’un appel est un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e9470-124">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="e9470-125">La **chaîne de numérotation d’urgence** oblige le client à inclure des informations d’emplacement et de rappel avec l’appel.</span><span class="sxs-lookup"><span data-stu-id="e9470-125">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9470-126">Si votre organisation n’utilise pas de préfixe d’accès à une ligne externe, vous n’avez pas besoin de créer une règle de normalisation de plan de numérotation correspondante qui ajoute le signe « + » à la chaîne 911 avant l’envoi de l’appel vers le routage sortant sur un serveur de pool Lync ; le signe « + » sera automatiquement ajouté par le client Lync à la suite de la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="e9470-126">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="e9470-127">Toutefois, si votre site utilise un préfixe d’accès externe, vous devez ajouter une règle de normalisation à la stratégie de plan de numérotation applicable qui supprime le préfixe d’accès externe et ajoute le signe « + ».</span><span class="sxs-lookup"><span data-stu-id="e9470-127">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="e9470-128">Par exemple, si votre emplacement utilise un préfixe d’accès externe de 9 et qu’un utilisateur&nbsp;compose le numéro 9 911 pour passer un appel d’urgence, le client utilise sa stratégie de plan de numérotation pour normaliser cette opération à + 911 avant que le numéro composé soit évalué par les itinéraires dans le profil d’emplacement de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e9470-128">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="e9470-129">**Masques de chaîne de numérotation d’urgence**</span><span class="sxs-lookup"><span data-stu-id="e9470-129">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="e9470-130">Liste de chaînes de numérotation séparées par des points-virgules qui est traduite dans la **chaîne de numérotation d’urgence**spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e9470-130">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="e9470-131">Par exemple, vous pouvez ajouter 112, qui est le numéro de service d’urgence pour la plupart d’Europe.</span><span class="sxs-lookup"><span data-stu-id="e9470-131">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="e9470-132">Un utilisateur de Lync visitant l’Europe peut ne pas savoir que 911 est le numéro de secours américain, mais il peut composer 112 et obtenir le même résultat.</span><span class="sxs-lookup"><span data-stu-id="e9470-132">A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="e9470-133">Comme pour la chaîne de numérotation d’urgence, n’incluez pas de signe « + » devant chaque numéro, et si vous utilisez des codes d’accès aux lignes externes, assurez-vous que les règles de normalisation dans la stratégie de plan de numérotation de l’utilisateur suppriment le chiffre de code d’accès.</span><span class="sxs-lookup"><span data-stu-id="e9470-133">As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="e9470-134">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="e9470-134">**PSTN Usage**</span></span>  
    <span data-ttu-id="e9470-135">Le nom de l’utilisation PSTN qui contient les chemins de routage qui déterminent la jonction SIP, la passerelle PSTN ou les appels d’urgence de passerelle ELIN vers.</span><span class="sxs-lookup"><span data-stu-id="e9470-135">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9470-136">Une seule utilisation peut être affectée à une stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="e9470-136">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="e9470-137">Cette utilisation PSTN remplace les utilisations PSTN attribuées à la stratégie de voix de l’utilisateur, mais s’applique uniquement aux appels passés à la chaîne de numérotation d’urgence ou à l’un des masques de chaîne de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e9470-137">This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="e9470-138">**URI de notification**</span><span class="sxs-lookup"><span data-stu-id="e9470-138">**Notification URI**</span></span>  
    <span data-ttu-id="e9470-139">Spécifie un ou plusieurs URI SIP du personnel de sécurité qui reçoit une notification de messagerie instantanée lors de la mise en place d’un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e9470-139">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="e9470-140">Les groupes de distribution sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e9470-140">Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="e9470-141">**URI de la conférence**</span><span class="sxs-lookup"><span data-stu-id="e9470-141">**Conference URI**</span></span>  
    <span data-ttu-id="e9470-142">Spécifie un numéro de numérotation directe vers l’intérieur (en général, un numéro de service de sécurité) qui doit être mis en conférence en cas d’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e9470-142">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="e9470-143">**Mode conférence**</span><span class="sxs-lookup"><span data-stu-id="e9470-143">**Conference Mode**</span></span>  
    <span data-ttu-id="e9470-144">Indique si l’URI de la Conférence doit être mis en conférence dans l’appel d’urgence via une communication unidirectionnelle ou bidirectionnelle.</span><span class="sxs-lookup"><span data-stu-id="e9470-144">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="e9470-145">**Intervalle d’actualisation de l’emplacement**</span><span class="sxs-lookup"><span data-stu-id="e9470-145">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="e9470-146">Spécifie la durée (en heures) entre les demandes client pour une mise à jour d’emplacement à partir du service d’informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="e9470-146">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="e9470-147">La valeur peut être définie sur n’importe quelle valeur comprise entre 1 et 12.</span><span class="sxs-lookup"><span data-stu-id="e9470-147">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="e9470-148">La valeur par défaut est 4.</span><span class="sxs-lookup"><span data-stu-id="e9470-148">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

