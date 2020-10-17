---
title: 'Lync Server 2013 : plans de numérotation et règles de normalisation'
description: 'Lync Server 2013 : plans de numérotation et règles de normalisation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0341d0c5267a2272ff45bd93408b2bd14f0ceeaa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559740"
---
# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="ce406-103">Plans de numérotation et règles de normalisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce406-103">Dial plans and normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce406-104">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ce406-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ce406-105">Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="ce406-105">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="ce406-106">Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont routés vers chaque emplacement, utilisateur ou objet contact.</span><span class="sxs-lookup"><span data-stu-id="ce406-106">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="ce406-107">La même chaîne de numérotation peut être interprétée et traduite différemment, en fonction de l’emplacement à partir duquel elle est numérotée et de l’objet contact ou de la personne à l’origine de l’appel.</span><span class="sxs-lookup"><span data-stu-id="ce406-107">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="ce406-108">Étendue du plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="ce406-108">Dial Plan Scope</span></span>

<span data-ttu-id="ce406-109">L' *étendue* d’un plan de numérotation détermine le niveau hiérarchique auquel le plan de numérotation peut être appliqué.</span><span class="sxs-lookup"><span data-stu-id="ce406-109">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="ce406-110">Dans Lync Server, un plan de numérotation par utilisateur peut être affecté à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ce406-110">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="ce406-111">Si aucun plan de numérotation utilisateur n’est affecté, le plan de numérotation du pool de serveurs d’inscriptions est appliqué.</span><span class="sxs-lookup"><span data-stu-id="ce406-111">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="ce406-112">S’il n’existe pas de plan de numérotation de pool de serveurs d’inscriptions, le plan de numérotation de site est appliqué.</span><span class="sxs-lookup"><span data-stu-id="ce406-112">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="ce406-113">Enfin, s’il n’existe aucun autre plan de numérotation applicable à l’utilisateur, le plan de numérotation globale est appliqué.</span><span class="sxs-lookup"><span data-stu-id="ce406-113">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="ce406-114">Les clients obtiennent des niveaux d’étendue de plan de numérotation via des paramètres de mise en service intrabande qui sont fournis lorsque les utilisateurs se connectent à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce406-114">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="ce406-115">En tant qu’administrateur, vous pouvez gérer et affecter des niveaux d’étendue de plan de numérotation à l’aide du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce406-115">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce406-116">Le plan de numérotation de la passerelle PSTN (réseau téléphonique commuté) du niveau de service est appliqué aux appels entrants d’une passerelle particulière.</span><span class="sxs-lookup"><span data-stu-id="ce406-116">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="ce406-117">Les niveaux d’étendue du plan de numérotation sont définis comme suit :</span><span class="sxs-lookup"><span data-stu-id="ce406-117">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="ce406-118">**Plan de numérotation utilisateur :** Peuvent être attribués à des utilisateurs individuels, des groupes ou des objets contact.</span><span class="sxs-lookup"><span data-stu-id="ce406-118">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="ce406-119">Les applications vocales peuvent rechercher un plan de numérotation par utilisateur lorsqu’un appel est reçu avec le contexte téléphonique défini sur User-default.</span><span class="sxs-lookup"><span data-stu-id="ce406-119">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="ce406-120">Pour l’affectation d’un plan de numérotation, un objet contact est considéré comme un utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="ce406-120">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="ce406-121">**Plan de numérotation du pool :** Peuvent être créés au niveau du service pour toute passerelle PSTN ou serveur d’inscriptions dans votre topologie.</span><span class="sxs-lookup"><span data-stu-id="ce406-121">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="ce406-122">Pour définir un plan de numérotation de pool, vous devez spécifier le service particulier (passerelle PSTN ou pool de serveurs d’inscriptions) auquel le plan de numérotation s’applique.</span><span class="sxs-lookup"><span data-stu-id="ce406-122">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="ce406-123">**Plan de numérotation de site :** Peut être créé pour un site entier, à l’exception des utilisateurs, des groupes ou des objets contact auxquels un plan de numérotation de pool ou un plan de numérotation utilisateur est affecté.</span><span class="sxs-lookup"><span data-stu-id="ce406-123">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="ce406-124">Pour définir un plan de numérotation de site, vous devez spécifier le site auquel le plan de numérotation s’applique.</span><span class="sxs-lookup"><span data-stu-id="ce406-124">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="ce406-125">**Plan de numérotation global :** Plan de numérotation par défaut installé avec le produit.</span><span class="sxs-lookup"><span data-stu-id="ce406-125">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="ce406-126">Vous pouvez modifier le plan de numérotation global, mais vous ne pouvez pas le supprimer.</span><span class="sxs-lookup"><span data-stu-id="ce406-126">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="ce406-127">Ce plan de numérotation s’applique à tous les utilisateurs voix entreprise, les groupes et les objets contact de votre déploiement, sauf si vous configurez et affectez un plan de numérotation avec une étendue plus spécifique.</span><span class="sxs-lookup"><span data-stu-id="ce406-127">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="ce406-128">Planification des plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="ce406-128">Planning for Dial Plans</span></span>

<span data-ttu-id="ce406-129">Pour planifier un plan de numérotation, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ce406-129">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="ce406-130">Répertoriez tous les paramètres régionaux dans lesquels votre organisation a un bureau.</span><span class="sxs-lookup"><span data-stu-id="ce406-130">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="ce406-131">La liste doit être à jour et complète.</span><span class="sxs-lookup"><span data-stu-id="ce406-131">The list must be up-to-date and complete.</span></span> <span data-ttu-id="ce406-132">Il doit être révisé au fur et à mesure que l’organisation de l’entreprise évolue.</span><span class="sxs-lookup"><span data-stu-id="ce406-132">It will need to be revised as company organization evolves.</span></span> <span data-ttu-id="ce406-133">Dans une grande entreprise multinationale avec de nombreuses petites succursales, il peut s’agir d’une tâche longue.</span><span class="sxs-lookup"><span data-stu-id="ce406-133">In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="ce406-134">Identifiez les modèles de numéros valides pour chaque site.</span><span class="sxs-lookup"><span data-stu-id="ce406-134">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="ce406-135">La partie la plus longue de la planification de vos plans de numérotation consiste à identifier les modèles de numéro valides pour chaque site.</span><span class="sxs-lookup"><span data-stu-id="ce406-135">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site.</span></span> <span data-ttu-id="ce406-136">Dans certains cas, vous pouvez copier les règles de normalisation que vous avez écrites pour un plan de numérotation vers d’autres plans de numérotation, en particulier si les sites correspondants se trouvent dans le même continent ou pays ou région.</span><span class="sxs-lookup"><span data-stu-id="ce406-136">In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent.</span></span> <span data-ttu-id="ce406-137">Dans les autres cas, les petites modifications apportées aux numéros dans un plan de numérotation peuvent être suffisantes pour les utiliser dans d’autres plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="ce406-137">In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="ce406-138">Développez un modèle à l’échelle de l’Organisation pour nommer les plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="ce406-138">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="ce406-139">L’adoption d’un modèle de dénomination standard garantit la cohérence au sein d’une organisation et facilite la maintenance et les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="ce406-139">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="ce406-140">Déterminez si plusieurs plans de numérotation sont requis pour un seul emplacement.</span><span class="sxs-lookup"><span data-stu-id="ce406-140">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="ce406-141">Si votre organisation gère un plan de numérotation unique sur plusieurs emplacements, il se peut que vous deviez créer un plan de numérotation distinct pour les utilisateurs de voix entreprise qui migrent à partir d’un PBX (Private Branch Exchange) et qui doivent conserver leurs extensions existantes.</span><span class="sxs-lookup"><span data-stu-id="ce406-141">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="ce406-142">Déterminez si des plans de numérotation par utilisateur sont requis.</span><span class="sxs-lookup"><span data-stu-id="ce406-142">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="ce406-143">Par exemple, si vous avez des utilisateurs sur un site de succursale inscrits auprès du site central ou si vous avez des utilisateurs inscrits sur un Survivable Branch appliance, vous pouvez envisager des scénarios de numérotation spéciaux pour ces utilisateurs qui utilisent des plans de numérotation par utilisateur et des règles de normalisation.</span><span class="sxs-lookup"><span data-stu-id="ce406-143">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="ce406-144">Pour plus d’informations, consultez la rubrique [Configuration requise pour la résistance des sites de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce406-144">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="ce406-145">Déterminez l’étendue du plan de numérotation (tel que décrit précédemment dans cette rubrique).</span><span class="sxs-lookup"><span data-stu-id="ce406-145">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="ce406-146">Pour créer un plan de numérotation, vous spécifiez des valeurs dans les champs suivants, selon vos besoins, à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ce406-146">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="ce406-147">Nom et nom simple</span><span class="sxs-lookup"><span data-stu-id="ce406-147">Name and Simple Name</span></span>

<span data-ttu-id="ce406-148">Pour les plans de numérotation utilisateur, vous devez spécifier un nom descriptif qui identifie les utilisateurs, groupes ou objets contact auxquels le plan de numérotation sera affecté.</span><span class="sxs-lookup"><span data-stu-id="ce406-148">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="ce406-149">Pour les plans de numérotation de site, le champ Nom contient déjà le nom du site qui ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="ce406-149">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="ce406-150">Pour les plans de numérotation du pool, le champ nom contient déjà le nom de domaine complet de la passerelle PSTN ou du pool frontal et ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="ce406-150">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="ce406-151">Le *nom simple* du plan de numérotation est pré-rempli avec une chaîne dérivée du nom du plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="ce406-151">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="ce406-152">Le champ nom simple est modifiable, ce qui vous permet de créer une convention d’affectation de noms plus descriptive pour vos plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="ce406-152">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="ce406-153">La valeur de *nom simple* ne peut pas être vide et doit être unique.</span><span class="sxs-lookup"><span data-stu-id="ce406-153">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="ce406-154">Il est recommandé de développer une convention d’affectation de noms pour l’ensemble de votre organisation, puis d’utiliser cette Convention de façon cohérente sur tous les sites et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ce406-154">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="ce406-155">Description</span><span class="sxs-lookup"><span data-stu-id="ce406-155">Description</span></span>

<span data-ttu-id="ce406-156">Nous vous recommandons de taper le nom commun et reconnaissable de l’emplacement géographique auquel le plan de numérotation correspondant s’applique.</span><span class="sxs-lookup"><span data-stu-id="ce406-156">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies.</span></span> <span data-ttu-id="ce406-157">Par exemple, si le nom du plan de numérotation est London.Contoso.com, la description recommandée est London.</span><span class="sxs-lookup"><span data-stu-id="ce406-157">For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="ce406-158">Région de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="ce406-158">Dial-in Conferencing Region</span></span>

<span data-ttu-id="ce406-159">Si vous déployez la Conférence rendez-vous, vous devez spécifier une région de conférence rendez-vous pour associer les numéros d’accès aux conférences rendez-vous avec un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="ce406-159">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="ce406-160">Préfixe d’accès externe</span><span class="sxs-lookup"><span data-stu-id="ce406-160">External Access Prefix</span></span>

<span data-ttu-id="ce406-161">Vous pouvez spécifier un préfixe d’accès externe de quatre caractères maximum ( \# , \* , et 0-9) si les utilisateurs doivent composer un ou plusieurs chiffres supplémentaires (par exemple, 9) pour obtenir une ligne externe.</span><span class="sxs-lookup"><span data-stu-id="ce406-161">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce406-162">Si vous spécifiez un préfixe d’accès externe, il n’est pas nécessaire de créer une règle de normalisation supplémentaire pour prendre en compte le préfixe.</span><span class="sxs-lookup"><span data-stu-id="ce406-162">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="ce406-163">Règles de normalisation</span><span class="sxs-lookup"><span data-stu-id="ce406-163">Normalization Rules</span></span>

<span data-ttu-id="ce406-164">Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés dans différents formats doivent être routés pour l’emplacement nommé.</span><span class="sxs-lookup"><span data-stu-id="ce406-164">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location.</span></span> <span data-ttu-id="ce406-165">La même chaîne de numérotation peut être interprétée et traduite différemment, selon les paramètres régionaux à partir desquels elle est numérotée.</span><span class="sxs-lookup"><span data-stu-id="ce406-165">The same number string may be interpreted and translated differently, depending on the locale from which it is dialed.</span></span> <span data-ttu-id="ce406-166">Les règles de normalisation sont nécessaires pour le routage des appels car les utilisateurs peuvent utiliser différents formats lors de la saisie de numéros de téléphone dans leurs listes de contacts.</span><span class="sxs-lookup"><span data-stu-id="ce406-166">Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="ce406-167">La normalisation des numéros de téléphone fournis par l’utilisateur offre un format cohérent qui facilite les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce406-167">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="ce406-168">Associez un numéro composé à l’URI SIP du destinataire concerné.</span><span class="sxs-lookup"><span data-stu-id="ce406-168">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="ce406-169">Appliquez les règles d’autorisation de numérotation à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ce406-169">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="ce406-170">Les champs numériques suivants figurent parmi ceux que vos règles de normalisation devront peut-être tenir compte des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="ce406-170">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="ce406-171">Plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="ce406-171">Dial plan</span></span>

  - <span data-ttu-id="ce406-172">Indicatif du pays</span><span class="sxs-lookup"><span data-stu-id="ce406-172">Country code</span></span>

  - <span data-ttu-id="ce406-173">Indicatif régional</span><span class="sxs-lookup"><span data-stu-id="ce406-173">Area code</span></span>

  - <span data-ttu-id="ce406-174">Longueur du poste</span><span class="sxs-lookup"><span data-stu-id="ce406-174">Length of extension</span></span>

  - <span data-ttu-id="ce406-175">Préfixe de site</span><span class="sxs-lookup"><span data-stu-id="ce406-175">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="ce406-176">Création de règles de normalisation</span><span class="sxs-lookup"><span data-stu-id="ce406-176">Creating Normalization Rules</span></span>

<span data-ttu-id="ce406-177">Les règles de normalisation utilisent des expressions régulières .NET Framework pour spécifier des modèles de correspondance numérique que le serveur utilise pour convertir des chaînes de numérotation au format E. 164 dans le but d’effectuer une recherche inversée des numéros.</span><span class="sxs-lookup"><span data-stu-id="ce406-177">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="ce406-178">Vous pouvez créer des règles de normalisation dans le panneau de configuration Lync Server en saisissant les expressions manuellement ou en saisissant les chiffres de départ et la longueur des chaînes de numérotation à mettre en correspondance et en laissant le panneau de configuration Lync Server générer l’expression régulière correspondante.</span><span class="sxs-lookup"><span data-stu-id="ce406-178">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="ce406-179">Dans les deux cas, lorsque vous avez terminé, vous pouvez entrer un numéro de test pour vérifier que la règle de normalisation fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="ce406-179">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="ce406-180">Pour plus d’informations sur l’utilisation des expressions régulières .NET Framework, voir « .NET Framework regular expressions » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="ce406-180">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="ce406-181">Exemples de règles de normalisation</span><span class="sxs-lookup"><span data-stu-id="ce406-181">Sample Normalization Rules</span></span>

<span data-ttu-id="ce406-182">Le tableau suivant présente des exemples de règles de normalisation écrites sous la forme d’expressions régulières .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ce406-182">The following table shows sample normalization rules that are written as .NET Framework regular expressions.</span></span> <span data-ttu-id="ce406-183">Les exemples ne sont que des exemples et ne sont pas destinés à être une référence normative pour la création de règles de normalisation.</span><span class="sxs-lookup"><span data-stu-id="ce406-183">The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="ce406-184">Tableau 1. règles de normalisation à l’aide d’expressions régulières .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ce406-184">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce406-185">Nom de la règle</span><span class="sxs-lookup"><span data-stu-id="ce406-185">Rule name</span></span></th>
<th><span data-ttu-id="ce406-186">Description</span><span class="sxs-lookup"><span data-stu-id="ce406-186">Description</span></span></th>
<th><span data-ttu-id="ce406-187">Type de numéro</span><span class="sxs-lookup"><span data-stu-id="ce406-187">Number pattern</span></span></th>
<th><span data-ttu-id="ce406-188">Conversion</span><span class="sxs-lookup"><span data-stu-id="ce406-188">Translation</span></span></th>
<th><span data-ttu-id="ce406-189">Exemple</span><span class="sxs-lookup"><span data-stu-id="ce406-189">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce406-190">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="ce406-190">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="ce406-191">Traduit les extensions à 4 chiffres</span><span class="sxs-lookup"><span data-stu-id="ce406-191">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="ce406-192">^(\d{4})$</span><span class="sxs-lookup"><span data-stu-id="ce406-192">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="ce406-193">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="ce406-193">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="ce406-194">0100 est converti en + 14255550100</span><span class="sxs-lookup"><span data-stu-id="ce406-194">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce406-195">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="ce406-195">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="ce406-196">Traduit les extensions à 5 chiffres</span><span class="sxs-lookup"><span data-stu-id="ce406-196">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="ce406-197">^ 5 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="ce406-197">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="ce406-198">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="ce406-198">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="ce406-199">50100 est converti en + 14255550100</span><span class="sxs-lookup"><span data-stu-id="ce406-199">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce406-200">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="ce406-200">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="ce406-201">Traduit les numéros à 7 chiffres en numéros locaux Redmond</span><span class="sxs-lookup"><span data-stu-id="ce406-201">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="ce406-202">^(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="ce406-202">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="ce406-203">+ 1425 $1</span><span class="sxs-lookup"><span data-stu-id="ce406-203">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="ce406-204">5550100 est converti en + 14255550100</span><span class="sxs-lookup"><span data-stu-id="ce406-204">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce406-205">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="ce406-205">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="ce406-206">Traduit les numéros à 7 chiffres en numéros locaux Dallas</span><span class="sxs-lookup"><span data-stu-id="ce406-206">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="ce406-207">^(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="ce406-207">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="ce406-208">+ 1972 $1</span><span class="sxs-lookup"><span data-stu-id="ce406-208">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="ce406-209">5550100 est converti en + 19725550100</span><span class="sxs-lookup"><span data-stu-id="ce406-209">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce406-210">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="ce406-210">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="ce406-211">Traduit les numéros à 10 chiffres aux États-Unis</span><span class="sxs-lookup"><span data-stu-id="ce406-211">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="ce406-212">^(\d{10})$</span><span class="sxs-lookup"><span data-stu-id="ce406-212">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="ce406-213">+1$1</span><span class="sxs-lookup"><span data-stu-id="ce406-213">+1$1</span></span></p></td>
<td><p><span data-ttu-id="ce406-214">2065550100 est converti en + 12065550100</span><span class="sxs-lookup"><span data-stu-id="ce406-214">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce406-215">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="ce406-215">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="ce406-216">Traduit les numéros avec des préfixes longue distance aux États-Unis</span><span class="sxs-lookup"><span data-stu-id="ce406-216">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="ce406-217">^ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="ce406-217">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="ce406-218">+ $1</span><span class="sxs-lookup"><span data-stu-id="ce406-218">+$1</span></span></p></td>
<td><p><span data-ttu-id="ce406-219">12145550100 est converti en + 2145550100</span><span class="sxs-lookup"><span data-stu-id="ce406-219">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce406-220">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="ce406-220">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="ce406-221">Traduit des numéros avec des préfixes internationaux aux États-Unis</span><span class="sxs-lookup"><span data-stu-id="ce406-221">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="ce406-222">^ 011 (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="ce406-222">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="ce406-223">+ $1</span><span class="sxs-lookup"><span data-stu-id="ce406-223">+$1</span></span></p></td>
<td><p><span data-ttu-id="ce406-224">01191445550100 est converti en + 91445550100</span><span class="sxs-lookup"><span data-stu-id="ce406-224">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce406-225">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="ce406-225">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="ce406-226">Traduit les opérateurs 0 à Redmond</span><span class="sxs-lookup"><span data-stu-id="ce406-226">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="ce406-227">^ $0</span><span class="sxs-lookup"><span data-stu-id="ce406-227">^0$</span></span></p></td>
<td><p><span data-ttu-id="ce406-228">+ 14255550100</span><span class="sxs-lookup"><span data-stu-id="ce406-228">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="ce406-229">0 est converti en + 14255550100</span><span class="sxs-lookup"><span data-stu-id="ce406-229">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce406-230">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="ce406-230">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="ce406-231">Traduit les numéros avec un préfixe réseau (6) et le code de site de Redmond (222)</span><span class="sxs-lookup"><span data-stu-id="ce406-231">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="ce406-232">^ 6222 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="ce406-232">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="ce406-233">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="ce406-233">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="ce406-234">62220100 est converti en + 14255550100</span><span class="sxs-lookup"><span data-stu-id="ce406-234">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce406-235">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="ce406-235">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="ce406-236">Traduit les numéros avec un préfixe réseau (6) et le code de site NY (333)</span><span class="sxs-lookup"><span data-stu-id="ce406-236">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="ce406-237">^ 6333 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="ce406-237">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="ce406-238">+ 1202555 $1</span><span class="sxs-lookup"><span data-stu-id="ce406-238">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="ce406-239">63330100 est converti en + 12025550100</span><span class="sxs-lookup"><span data-stu-id="ce406-239">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce406-240">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="ce406-240">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="ce406-241">Traduit les numéros avec un préfixe sur le réseau (6) et le code de site Dallas (444)</span><span class="sxs-lookup"><span data-stu-id="ce406-241">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="ce406-242">^ 6444 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="ce406-242">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="ce406-243">+ 1972555 $1</span><span class="sxs-lookup"><span data-stu-id="ce406-243">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="ce406-244">64440100 est converti en + 19725550100</span><span class="sxs-lookup"><span data-stu-id="ce406-244">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ce406-245">Le tableau suivant illustre un exemple de plan de numérotation pour Redmond, Washington, États-Unis, basé sur les règles de normalisation indiquées dans le tableau précédent.</span><span class="sxs-lookup"><span data-stu-id="ce406-245">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="ce406-246">Tableau 2.</span><span class="sxs-lookup"><span data-stu-id="ce406-246">Table 2.</span></span> <span data-ttu-id="ce406-247">Plan de numérotation de Redmond basé sur les règles de normalisation indiquées dans le tableau 1</span><span class="sxs-lookup"><span data-stu-id="ce406-247">Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce406-248">Redmond. forestFQDN</span><span class="sxs-lookup"><span data-stu-id="ce406-248">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce406-249">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="ce406-249">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce406-250">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="ce406-250">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce406-251">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="ce406-251">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce406-252">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="ce406-252">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce406-253">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="ce406-253">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce406-254">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="ce406-254">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce406-255">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="ce406-255">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce406-256">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="ce406-256">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ce406-257">Les noms des règles de normalisation indiqués dans le tableau précédent n’incluent pas d’espaces, mais c’est une question de choix.</span><span class="sxs-lookup"><span data-stu-id="ce406-257">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice.</span></span> <span data-ttu-id="ce406-258">Le premier nom de la table, par exemple, aurait pu avoir été écrit « extension de 5 chiffres » ou « poste à 5 chiffres » et être toujours valide.</span><span class="sxs-lookup"><span data-stu-id="ce406-258">The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

