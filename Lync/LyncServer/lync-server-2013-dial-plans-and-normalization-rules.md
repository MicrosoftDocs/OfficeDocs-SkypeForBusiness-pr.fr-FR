---
title: 'Lync Server 2013 : plans de numérotation et règles de normalisation'
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
ms.openlocfilehash: 4adcd2cd6bebfb0797427d15819399c9b2b9f86d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="e9387-102">Plans de numérotation et règles de normalisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9387-102">Dial plans and normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9387-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e9387-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e9387-104">Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="e9387-104">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="e9387-105">Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont routés vers chaque emplacement, utilisateur ou objet contact.</span><span class="sxs-lookup"><span data-stu-id="e9387-105">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="e9387-106">La même chaîne de numérotation peut être interprétée et traduite différemment, en fonction de l’emplacement à partir duquel elle est numérotée et de l’objet contact ou de la personne à l’origine de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e9387-106">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="e9387-107">Étendue du plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="e9387-107">Dial Plan Scope</span></span>

<span data-ttu-id="e9387-108">L' *étendue* d’un plan de numérotation détermine le niveau hiérarchique auquel le plan de numérotation peut être appliqué.</span><span class="sxs-lookup"><span data-stu-id="e9387-108">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="e9387-109">Dans Lync Server, un plan de numérotation par utilisateur peut être affecté à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e9387-109">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="e9387-110">Si aucun plan de numérotation utilisateur n’est affecté, le plan de numérotation du pool de serveurs d’inscriptions est appliqué.</span><span class="sxs-lookup"><span data-stu-id="e9387-110">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="e9387-111">S’il n’existe pas de plan de numérotation de pool de serveurs d’inscriptions, le plan de numérotation de site est appliqué.</span><span class="sxs-lookup"><span data-stu-id="e9387-111">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="e9387-112">Enfin, s’il n’existe aucun autre plan de numérotation applicable à l’utilisateur, le plan de numérotation globale est appliqué.</span><span class="sxs-lookup"><span data-stu-id="e9387-112">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="e9387-113">Les clients obtiennent des niveaux d’étendue de plan de numérotation via des paramètres de mise en service intrabande qui sont fournis lorsque les utilisateurs se connectent à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9387-113">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="e9387-114">En tant qu’administrateur, vous pouvez gérer et affecter des niveaux d’étendue de plan de numérotation à l’aide du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9387-114">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9387-115">Le plan de numérotation de la passerelle PSTN (réseau téléphonique commuté) du niveau de service est appliqué aux appels entrants d’une passerelle particulière.</span><span class="sxs-lookup"><span data-stu-id="e9387-115">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="e9387-116">Les niveaux d’étendue du plan de numérotation sont définis comme suit :</span><span class="sxs-lookup"><span data-stu-id="e9387-116">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="e9387-117">**Plan de numérotation utilisateur :** Peuvent être attribués à des utilisateurs individuels, des groupes ou des objets contact.</span><span class="sxs-lookup"><span data-stu-id="e9387-117">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="e9387-118">Les applications vocales peuvent rechercher un plan de numérotation par utilisateur lorsqu’un appel est reçu avec le contexte téléphonique défini sur User-default.</span><span class="sxs-lookup"><span data-stu-id="e9387-118">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="e9387-119">Pour l’affectation d’un plan de numérotation, un objet contact est considéré comme un utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="e9387-119">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="e9387-120">**Plan de numérotation du pool :** Peuvent être créés au niveau du service pour toute passerelle PSTN ou serveur d’inscriptions dans votre topologie.</span><span class="sxs-lookup"><span data-stu-id="e9387-120">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="e9387-121">Pour définir un plan de numérotation de pool, vous devez spécifier le service particulier (passerelle PSTN ou pool de serveurs d’inscriptions) auquel le plan de numérotation s’applique.</span><span class="sxs-lookup"><span data-stu-id="e9387-121">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="e9387-122">**Plan de numérotation de site :** Peut être créé pour un site entier, à l’exception des utilisateurs, des groupes ou des objets contact auxquels un plan de numérotation de pool ou un plan de numérotation utilisateur est affecté.</span><span class="sxs-lookup"><span data-stu-id="e9387-122">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="e9387-123">Pour définir un plan de numérotation de site, vous devez spécifier le site auquel le plan de numérotation s’applique.</span><span class="sxs-lookup"><span data-stu-id="e9387-123">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="e9387-124">**Plan de numérotation global :** Plan de numérotation par défaut installé avec le produit.</span><span class="sxs-lookup"><span data-stu-id="e9387-124">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="e9387-125">Vous pouvez modifier le plan de numérotation global, mais vous ne pouvez pas le supprimer.</span><span class="sxs-lookup"><span data-stu-id="e9387-125">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="e9387-126">Ce plan de numérotation s’applique à tous les utilisateurs voix entreprise, les groupes et les objets contact de votre déploiement, sauf si vous configurez et affectez un plan de numérotation avec une étendue plus spécifique.</span><span class="sxs-lookup"><span data-stu-id="e9387-126">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="e9387-127">Planification des plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="e9387-127">Planning for Dial Plans</span></span>

<span data-ttu-id="e9387-128">Pour planifier un plan de numérotation, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e9387-128">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="e9387-129">Répertoriez tous les paramètres régionaux dans lesquels votre organisation a un bureau.</span><span class="sxs-lookup"><span data-stu-id="e9387-129">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="e9387-130">La liste doit être à jour et complète.</span><span class="sxs-lookup"><span data-stu-id="e9387-130">The list must be up-to-date and complete.</span></span> <span data-ttu-id="e9387-131">Il doit être révisé au fur et à mesure que l’organisation de l’entreprise évolue.</span><span class="sxs-lookup"><span data-stu-id="e9387-131">It will need to be revised as company organization evolves.</span></span> <span data-ttu-id="e9387-132">Dans une grande entreprise multinationale avec de nombreuses petites succursales, il peut s’agir d’une tâche longue.</span><span class="sxs-lookup"><span data-stu-id="e9387-132">In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="e9387-133">Identifiez les modèles de numéros valides pour chaque site.</span><span class="sxs-lookup"><span data-stu-id="e9387-133">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="e9387-134">La partie la plus longue de la planification de vos plans de numérotation consiste à identifier les modèles de numéro valides pour chaque site.</span><span class="sxs-lookup"><span data-stu-id="e9387-134">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site.</span></span> <span data-ttu-id="e9387-135">Dans certains cas, vous pouvez copier les règles de normalisation que vous avez écrites pour un plan de numérotation vers d’autres plans de numérotation, en particulier si les sites correspondants se trouvent dans le même continent ou pays ou région.</span><span class="sxs-lookup"><span data-stu-id="e9387-135">In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent.</span></span> <span data-ttu-id="e9387-136">Dans les autres cas, les petites modifications apportées aux numéros dans un plan de numérotation peuvent être suffisantes pour les utiliser dans d’autres plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="e9387-136">In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="e9387-137">Développez un modèle à l’échelle de l’Organisation pour nommer les plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="e9387-137">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="e9387-138">L’adoption d’un modèle de dénomination standard garantit la cohérence au sein d’une organisation et facilite la maintenance et les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="e9387-138">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="e9387-139">Déterminez si plusieurs plans de numérotation sont requis pour un seul emplacement.</span><span class="sxs-lookup"><span data-stu-id="e9387-139">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="e9387-140">Si votre organisation gère un plan de numérotation unique sur plusieurs emplacements, il se peut que vous deviez créer un plan de numérotation distinct pour les utilisateurs de voix entreprise qui migrent à partir d’un PBX (Private Branch Exchange) et qui doivent conserver leurs extensions existantes.</span><span class="sxs-lookup"><span data-stu-id="e9387-140">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="e9387-141">Déterminez si des plans de numérotation par utilisateur sont requis.</span><span class="sxs-lookup"><span data-stu-id="e9387-141">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="e9387-142">Par exemple, si des utilisateurs d’un site de succursale sont inscrits auprès du site central ou si vous avez des utilisateurs inscrits sur un Survivable Branch appliance, vous pouvez envisager des scénarios de numérotation spéciaux pour ces utilisateurs qui utilisent des plans de numérotation par utilisateur et des règles de normalisation .</span><span class="sxs-lookup"><span data-stu-id="e9387-142">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="e9387-143">Pour plus d’informations, consultez la rubrique [Configuration requise pour la résistance des sites de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9387-143">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="e9387-144">Déterminez l’étendue du plan de numérotation (tel que décrit précédemment dans cette rubrique).</span><span class="sxs-lookup"><span data-stu-id="e9387-144">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="e9387-145">Pour créer un plan de numérotation, vous spécifiez des valeurs dans les champs suivants, selon vos besoins, à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e9387-145">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="e9387-146">Nom et nom simple</span><span class="sxs-lookup"><span data-stu-id="e9387-146">Name and Simple Name</span></span>

<span data-ttu-id="e9387-147">Pour les plans de numérotation utilisateur, vous devez spécifier un nom descriptif qui identifie les utilisateurs, groupes ou objets contact auxquels le plan de numérotation sera affecté.</span><span class="sxs-lookup"><span data-stu-id="e9387-147">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="e9387-148">Pour les plans de numérotation de site, le champ Nom contient déjà le nom du site qui ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="e9387-148">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="e9387-149">Pour les plans de numérotation du pool, le champ nom contient déjà le nom de domaine complet de la passerelle PSTN ou du pool frontal et ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="e9387-149">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="e9387-150">Le *nom simple* du plan de numérotation est pré-rempli avec une chaîne dérivée du nom du plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="e9387-150">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="e9387-151">Le champ nom simple est modifiable, ce qui vous permet de créer une convention d’affectation de noms plus descriptive pour vos plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="e9387-151">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="e9387-152">La valeur de *nom simple* ne peut pas être vide et doit être unique.</span><span class="sxs-lookup"><span data-stu-id="e9387-152">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="e9387-153">Il est recommandé de développer une convention d’affectation de noms pour l’ensemble de votre organisation, puis d’utiliser cette Convention de façon cohérente sur tous les sites et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e9387-153">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="e9387-154">Description</span><span class="sxs-lookup"><span data-stu-id="e9387-154">Description</span></span>

<span data-ttu-id="e9387-155">Nous vous recommandons de taper le nom commun et reconnaissable de l’emplacement géographique auquel le plan de numérotation correspondant s’applique.</span><span class="sxs-lookup"><span data-stu-id="e9387-155">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies.</span></span> <span data-ttu-id="e9387-156">Par exemple, si le nom du plan de numérotation est London.Contoso.com, la description recommandée est London.</span><span class="sxs-lookup"><span data-stu-id="e9387-156">For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="e9387-157">Région de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="e9387-157">Dial-in Conferencing Region</span></span>

<span data-ttu-id="e9387-158">Si vous déployez la Conférence rendez-vous, vous devez spécifier une région de conférence rendez-vous pour associer les numéros d’accès aux conférences rendez-vous avec un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="e9387-158">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="e9387-159">Préfixe d’accès externe</span><span class="sxs-lookup"><span data-stu-id="e9387-159">External Access Prefix</span></span>

<span data-ttu-id="e9387-160">Vous pouvez spécifier un préfixe d’accès externe de quatre caractères maximum\#( \*,, et 0-9) si les utilisateurs doivent composer un ou plusieurs chiffres supplémentaires (par exemple, 9) pour obtenir une ligne externe.</span><span class="sxs-lookup"><span data-stu-id="e9387-160">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9387-161">Si vous spécifiez un préfixe d’accès externe, il n’est pas nécessaire de créer une règle de normalisation supplémentaire pour prendre en compte le préfixe.</span><span class="sxs-lookup"><span data-stu-id="e9387-161">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="e9387-162">Règles de normalisation</span><span class="sxs-lookup"><span data-stu-id="e9387-162">Normalization Rules</span></span>

<span data-ttu-id="e9387-163">Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés dans différents formats doivent être routés pour l’emplacement nommé.</span><span class="sxs-lookup"><span data-stu-id="e9387-163">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location.</span></span> <span data-ttu-id="e9387-164">La même chaîne de numérotation peut être interprétée et traduite différemment, selon les paramètres régionaux à partir desquels elle est numérotée.</span><span class="sxs-lookup"><span data-stu-id="e9387-164">The same number string may be interpreted and translated differently, depending on the locale from which it is dialed.</span></span> <span data-ttu-id="e9387-165">Les règles de normalisation sont nécessaires pour le routage des appels car les utilisateurs peuvent utiliser différents formats lors de la saisie de numéros de téléphone dans leurs listes de contacts.</span><span class="sxs-lookup"><span data-stu-id="e9387-165">Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="e9387-166">La normalisation des numéros de téléphone fournis par l’utilisateur offre un format cohérent qui facilite les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="e9387-166">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="e9387-167">Associez un numéro composé à l’URI SIP du destinataire concerné.</span><span class="sxs-lookup"><span data-stu-id="e9387-167">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="e9387-168">Appliquez les règles d’autorisation de numérotation à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e9387-168">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="e9387-169">Les champs numériques suivants figurent parmi ceux que vos règles de normalisation devront peut-être tenir compte des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e9387-169">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="e9387-170">Plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="e9387-170">Dial plan</span></span>

  - <span data-ttu-id="e9387-171">Indicatif du pays</span><span class="sxs-lookup"><span data-stu-id="e9387-171">Country code</span></span>

  - <span data-ttu-id="e9387-172">Indicatif régional</span><span class="sxs-lookup"><span data-stu-id="e9387-172">Area code</span></span>

  - <span data-ttu-id="e9387-173">Longueur du poste</span><span class="sxs-lookup"><span data-stu-id="e9387-173">Length of extension</span></span>

  - <span data-ttu-id="e9387-174">Préfixe de site</span><span class="sxs-lookup"><span data-stu-id="e9387-174">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="e9387-175">Création de règles de normalisation</span><span class="sxs-lookup"><span data-stu-id="e9387-175">Creating Normalization Rules</span></span>

<span data-ttu-id="e9387-176">Les règles de normalisation utilisent des expressions régulières .NET Framework pour spécifier des modèles de correspondance numérique que le serveur utilise pour convertir des chaînes de numérotation au format E. 164 dans le but d’effectuer une recherche inversée des numéros.</span><span class="sxs-lookup"><span data-stu-id="e9387-176">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="e9387-177">Vous pouvez créer des règles de normalisation dans le panneau de configuration Lync Server en saisissant les expressions manuellement ou en saisissant les chiffres de départ et la longueur des chaînes de numérotation à mettre en correspondance et en laissant le panneau de configuration Lync Server générer le expression régulière pour vous.</span><span class="sxs-lookup"><span data-stu-id="e9387-177">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="e9387-178">Dans les deux cas, lorsque vous avez terminé, vous pouvez entrer un numéro de test pour vérifier que la règle de normalisation fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="e9387-178">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="e9387-179">Pour plus d’informations sur l’utilisation des expressions régulières .NET Framework, voir « .NET [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)Framework regular expressions » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="e9387-179">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="e9387-180">Exemples de règles de normalisation</span><span class="sxs-lookup"><span data-stu-id="e9387-180">Sample Normalization Rules</span></span>

<span data-ttu-id="e9387-181">Le tableau suivant présente des exemples de règles de normalisation écrites sous la forme d’expressions régulières .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9387-181">The following table shows sample normalization rules that are written as .NET Framework regular expressions.</span></span> <span data-ttu-id="e9387-182">Les exemples ne sont que des exemples et ne sont pas destinés à être une référence normative pour la création de règles de normalisation.</span><span class="sxs-lookup"><span data-stu-id="e9387-182">The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="e9387-183">Tableau 1. règles de normalisation à l’aide d’expressions régulières .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e9387-183">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

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
<th><span data-ttu-id="e9387-184">Nom de la règle</span><span class="sxs-lookup"><span data-stu-id="e9387-184">Rule name</span></span></th>
<th><span data-ttu-id="e9387-185">Description</span><span class="sxs-lookup"><span data-stu-id="e9387-185">Description</span></span></th>
<th><span data-ttu-id="e9387-186">Type de numéro</span><span class="sxs-lookup"><span data-stu-id="e9387-186">Number pattern</span></span></th>
<th><span data-ttu-id="e9387-187">Conversion</span><span class="sxs-lookup"><span data-stu-id="e9387-187">Translation</span></span></th>
<th><span data-ttu-id="e9387-188">Exemple</span><span class="sxs-lookup"><span data-stu-id="e9387-188">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9387-189">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="e9387-189">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="e9387-190">Traduit les extensions à 4 chiffres</span><span class="sxs-lookup"><span data-stu-id="e9387-190">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="e9387-191">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="e9387-191">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="e9387-192">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="e9387-192">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="e9387-193">0100 est converti en + 14255550100</span><span class="sxs-lookup"><span data-stu-id="e9387-193">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9387-194">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="e9387-194">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="e9387-195">Traduit les extensions à 5 chiffres</span><span class="sxs-lookup"><span data-stu-id="e9387-195">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="e9387-196">^ 5 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="e9387-196">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="e9387-197">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="e9387-197">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="e9387-198">50100 est converti en + 14255550100</span><span class="sxs-lookup"><span data-stu-id="e9387-198">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9387-199">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="e9387-199">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="e9387-200">Traduit les numéros à 7 chiffres en numéros locaux Redmond</span><span class="sxs-lookup"><span data-stu-id="e9387-200">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="e9387-201">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="e9387-201">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="e9387-202">+ 1425 $1</span><span class="sxs-lookup"><span data-stu-id="e9387-202">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="e9387-203">5550100 est converti en + 14255550100</span><span class="sxs-lookup"><span data-stu-id="e9387-203">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9387-204">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="e9387-204">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="e9387-205">Traduit les numéros à 7 chiffres en numéros locaux Dallas</span><span class="sxs-lookup"><span data-stu-id="e9387-205">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="e9387-206">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="e9387-206">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="e9387-207">+ 1972 $1</span><span class="sxs-lookup"><span data-stu-id="e9387-207">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="e9387-208">5550100 est converti en + 19725550100</span><span class="sxs-lookup"><span data-stu-id="e9387-208">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9387-209">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="e9387-209">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="e9387-210">Traduit les numéros à 10 chiffres aux États-Unis</span><span class="sxs-lookup"><span data-stu-id="e9387-210">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="e9387-211">^ (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="e9387-211">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="e9387-212">+ 1 $1</span><span class="sxs-lookup"><span data-stu-id="e9387-212">+1$1</span></span></p></td>
<td><p><span data-ttu-id="e9387-213">2065550100 est converti en + 12065550100</span><span class="sxs-lookup"><span data-stu-id="e9387-213">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9387-214">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="e9387-214">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="e9387-215">Traduit les numéros avec des préfixes longue distance aux États-Unis</span><span class="sxs-lookup"><span data-stu-id="e9387-215">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="e9387-216">^ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="e9387-216">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="e9387-217">+ $1</span><span class="sxs-lookup"><span data-stu-id="e9387-217">+$1</span></span></p></td>
<td><p><span data-ttu-id="e9387-218">12145550100 est converti en + 2145550100</span><span class="sxs-lookup"><span data-stu-id="e9387-218">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9387-219">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="e9387-219">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="e9387-220">Traduit des numéros avec des préfixes internationaux aux États-Unis</span><span class="sxs-lookup"><span data-stu-id="e9387-220">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="e9387-221">^ 011 (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="e9387-221">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="e9387-222">+ $1</span><span class="sxs-lookup"><span data-stu-id="e9387-222">+$1</span></span></p></td>
<td><p><span data-ttu-id="e9387-223">01191445550100 est converti en + 91445550100</span><span class="sxs-lookup"><span data-stu-id="e9387-223">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9387-224">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="e9387-224">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="e9387-225">Traduit les opérateurs 0 à Redmond</span><span class="sxs-lookup"><span data-stu-id="e9387-225">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="e9387-226">^ $0</span><span class="sxs-lookup"><span data-stu-id="e9387-226">^0$</span></span></p></td>
<td><p><span data-ttu-id="e9387-227">+ 14255550100</span><span class="sxs-lookup"><span data-stu-id="e9387-227">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="e9387-228">0 est converti en + 14255550100</span><span class="sxs-lookup"><span data-stu-id="e9387-228">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9387-229">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="e9387-229">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="e9387-230">Traduit les numéros avec un préfixe réseau (6) et le code de site de Redmond (222)</span><span class="sxs-lookup"><span data-stu-id="e9387-230">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="e9387-231">^ 6222 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="e9387-231">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="e9387-232">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="e9387-232">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="e9387-233">62220100 est converti en + 14255550100</span><span class="sxs-lookup"><span data-stu-id="e9387-233">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9387-234">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="e9387-234">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="e9387-235">Traduit les numéros avec un préfixe réseau (6) et le code de site NY (333)</span><span class="sxs-lookup"><span data-stu-id="e9387-235">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="e9387-236">^ 6333 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="e9387-236">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="e9387-237">+ 1202555 $1</span><span class="sxs-lookup"><span data-stu-id="e9387-237">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="e9387-238">63330100 est converti en + 12025550100</span><span class="sxs-lookup"><span data-stu-id="e9387-238">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9387-239">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="e9387-239">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="e9387-240">Traduit les numéros avec un préfixe sur le réseau (6) et le code de site Dallas (444)</span><span class="sxs-lookup"><span data-stu-id="e9387-240">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="e9387-241">^ 6444 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="e9387-241">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="e9387-242">+ 1972555 $1</span><span class="sxs-lookup"><span data-stu-id="e9387-242">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="e9387-243">64440100 est converti en + 19725550100</span><span class="sxs-lookup"><span data-stu-id="e9387-243">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e9387-244">Le tableau suivant illustre un exemple de plan de numérotation pour Redmond, Washington, États-Unis, basé sur les règles de normalisation indiquées dans le tableau précédent.</span><span class="sxs-lookup"><span data-stu-id="e9387-244">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="e9387-245">Tableau 2.</span><span class="sxs-lookup"><span data-stu-id="e9387-245">Table 2.</span></span> <span data-ttu-id="e9387-246">Plan de numérotation de Redmond basé sur les règles de normalisation indiquées dans le tableau 1</span><span class="sxs-lookup"><span data-stu-id="e9387-246">Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9387-247">Redmond. forestFQDN</span><span class="sxs-lookup"><span data-stu-id="e9387-247">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9387-248">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="e9387-248">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9387-249">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="e9387-249">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9387-250">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="e9387-250">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9387-251">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="e9387-251">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9387-252">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="e9387-252">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9387-253">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="e9387-253">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9387-254">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="e9387-254">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9387-255">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="e9387-255">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e9387-256">Les noms des règles de normalisation indiqués dans le tableau précédent n’incluent pas d’espaces, mais c’est une question de choix.</span><span class="sxs-lookup"><span data-stu-id="e9387-256">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice.</span></span> <span data-ttu-id="e9387-257">Le premier nom de la table, par exemple, aurait pu avoir été écrit « extension de 5 chiffres » ou « poste à 5 chiffres » et être toujours valide.</span><span class="sxs-lookup"><span data-stu-id="e9387-257">The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

