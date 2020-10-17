---
title: Configuration requise pour la Conférence rendez-vous Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 944aaf06ce81e5ba326841f6abe91614cdffd134
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498911"
---
# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="433f9-102">Exigences en matière de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="433f9-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="433f9-103">_**Dernière modification de la rubrique :** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="433f9-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="433f9-104">Avant de démarrer le processus de déploiement de Lync Server 2013, vous devez planifier les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="433f9-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="433f9-105">Configuration à utiliser pour la connexion au réseau téléphonique commuté (RTC)</span><span class="sxs-lookup"><span data-stu-id="433f9-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="433f9-106">Votre stratégie d’affectation des régions de conférence rendez-vous aux numéros d’accès entrant</span><span class="sxs-lookup"><span data-stu-id="433f9-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="433f9-107">Votre stratégie de création d’annuaires de conférence</span><span class="sxs-lookup"><span data-stu-id="433f9-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="433f9-108">Planification de la connectivité RTC rendez-vous</span><span class="sxs-lookup"><span data-stu-id="433f9-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="433f9-109">La Conférence rendez-vous nécessite au moins un serveur de médiation et au moins une passerelle RTC.</span><span class="sxs-lookup"><span data-stu-id="433f9-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="433f9-110">Vous pouvez déployer un serveur de médiation dans un site central ou dans un site de succursale.</span><span class="sxs-lookup"><span data-stu-id="433f9-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="433f9-111">Dans un site central, vous pouvez colocaliser un serveur de médiation sur un pool frontal ou un serveur Standard Edition, ou vous pouvez le déployer sur un serveur ou un pool autonome.</span><span class="sxs-lookup"><span data-stu-id="433f9-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="433f9-112">Dans un site de succursale, vous pouvez déployer un serveur de médiation sur un serveur autonome ou en tant que composant du Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="433f9-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="433f9-113">Vous pouvez déployer une passerelle PSTN dans un site central ou dans un site de succursale.</span><span class="sxs-lookup"><span data-stu-id="433f9-113">You can deploy a PSTN gateway in a central site or in a branch site.</span></span> <span data-ttu-id="433f9-114">Dans un site de succursale, la passerelle PSTN peut être autonome ou un composant du Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="433f9-114">In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="433f9-115">La Conférence rendez-vous n’utilise pas le contournement de média car le serveur de conférence A/V ne prend pas en charge la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="433f9-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="433f9-116">Pour plus d’informations sur la planification de votre configuration pour le serveur de médiation et les passerelles PSTN pour la Conférence rendez-vous, voir [composants et topologies pour le serveur de médiation dans Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="433f9-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="433f9-117">Planification des régions de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="433f9-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="433f9-118">Lors de la configuration d’un rendez-vous, vous créez des plans de numérotation et des numéros d’accès aux conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="433f9-118">During dial-in configuration, you create dial plans and dial-in conferencing access numbers.</span></span> <span data-ttu-id="433f9-119">Les plans de numérotation sont des ensembles de règles de normalisation qui spécifient le nombre et le modèle de chiffres dans un numéro de téléphone et traduisent le numéro de téléphone au format E. 164 standard pour le routage des appels.</span><span class="sxs-lookup"><span data-stu-id="433f9-119">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing.</span></span> <span data-ttu-id="433f9-120">Les numéros d’accès aux conférences rendez-vous sont les numéros que les participants participent à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="433f9-120">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="433f9-121">Chaque numéro d’accès à une conférence rendez-vous doit être associé à au moins un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="433f9-121">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> <span data-ttu-id="433f9-122">Les régions de conférence rendez-vous associent un numéro d’accès à des conférences rendez-vous avec ses plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="433f9-122">Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans.</span></span> <span data-ttu-id="433f9-123">Lorsque vous configurez un plan de numérotation, vous spécifiez la région de conférence rendez-vous qui s’applique au plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="433f9-123">When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan.</span></span> <span data-ttu-id="433f9-124">Lorsque vous créez le numéro d’accès entrant, vous sélectionnez les régions qui associent le numéro d’accès aux plans de numérotation appropriés.</span><span class="sxs-lookup"><span data-stu-id="433f9-124">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="433f9-125">Lorsque vous créez un plan de numérotation, vous spécifiez l’étendue du plan de numérotation : étendue utilisateur, étendue du pool ou étendue du site.</span><span class="sxs-lookup"><span data-stu-id="433f9-125">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope.</span></span> <span data-ttu-id="433f9-126">Le plan de numérotation est affecté à chaque utilisateur à partir de l’étendue la plus étroite qui s’applique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="433f9-126">Every user is assigned the dial plan from the narrowest scope that applies to the user.</span></span> <span data-ttu-id="433f9-127">Par exemple, un utilisateur est affecté à un plan de numérotation au niveau de l’utilisateur, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="433f9-127">For example, a user is assigned a user-level dial plan, if one applies.</span></span> <span data-ttu-id="433f9-128">Si aucun plan de numérotation au niveau de l’utilisateur ne s’applique, un plan de numérotation au niveau du pool est affecté à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="433f9-128">If a user-level dial plan does not apply, the user is assigned a pool-level dial plan.</span></span> <span data-ttu-id="433f9-129">Si aucun plan de numérotation au niveau du pool ne s’applique, l’utilisateur est affecté à un plan de numérotation au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="433f9-129">If a pool-level dial plan does not apply, the user is assigned a site-level dial plan.</span></span> <span data-ttu-id="433f9-130">Si un plan de numérotation au niveau du site ne s’applique pas, le plan de numérotation global est affecté à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="433f9-130">If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="433f9-131">Avant de configurer les plans de numérotation, il est important de planifier la façon dont vous souhaitez nommer et utiliser des régions.</span><span class="sxs-lookup"><span data-stu-id="433f9-131">Before you configure the dial plans, is it important to plan how you want to name and use regions.</span></span> <span data-ttu-id="433f9-132">Les considérations suivantes s’appliquent aux régions de conférence rendez-vous :</span><span class="sxs-lookup"><span data-stu-id="433f9-132">The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="433f9-133">Une région est généralement une zone géographique associée à un bureau ou à un groupe de bureaux.</span><span class="sxs-lookup"><span data-stu-id="433f9-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="433f9-134">Les langues sont associées aux numéros d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="433f9-134">Languages are associated with dial-in access numbers.</span></span> <span data-ttu-id="433f9-135">Si vous prenez en charge les zones géographiques qui ont plusieurs langues, vous devez déterminer la manière dont vous souhaitez définir les régions afin de prendre en charge les différentes langues.</span><span class="sxs-lookup"><span data-stu-id="433f9-135">If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages.</span></span> <span data-ttu-id="433f9-136">Par exemple, vous pouvez définir plusieurs régions en fonction d’une combinaison de géographie et de langue, ou vous pouvez définir une région unique basée sur la géographie et disposer de différents numéros d’accès entrant pour chaque langue.</span><span class="sxs-lookup"><span data-stu-id="433f9-136">For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="433f9-137">Lorsqu’un utilisateur planifie une réunion, par défaut, la réunion utilise la région spécifiée par le plan de numérotation de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="433f9-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="433f9-138">Par défaut, tous les numéros d’accès entrant de la région sont inclus dans l’invitation à la réunion.</span><span class="sxs-lookup"><span data-stu-id="433f9-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="433f9-139">Il est important de nommer les régions afin qu’elles soient clairement reconnaissables.</span><span class="sxs-lookup"><span data-stu-id="433f9-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="433f9-140">L’utilisateur peut utiliser les noms des régions pour modifier la région d’une réunion afin que différents numéros d’accès soient inclus dans l’invitation.</span><span class="sxs-lookup"><span data-stu-id="433f9-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="433f9-141">(Lorsque les utilisateurs utilisent Outlook pour planifier une réunion, l’utilisateur utilise le complément de réunion en ligne pour Lync 2013 afin de modifier la région).</span><span class="sxs-lookup"><span data-stu-id="433f9-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="433f9-142">Les régions doivent être conçues de sorte que tout invité souhaitant accéder à une Conférence puisse voir un numéro d’accès local dans l’invitation à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="433f9-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="433f9-143">Vous pouvez configurer l’ordre dans lequel les numéros d’accès au sein d’une région apparaissent sur la page Paramètres de conférence rendez-vous (et, par conséquent, l’ordre dans lequel ils apparaissent dans l’invitation à la Conférence) à l’aide des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="433f9-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="433f9-144">Tout utilisateur de n’importe quel emplacement peut appeler n’importe quel numéro d’accès entrant pour rejoindre une conférence.</span><span class="sxs-lookup"><span data-stu-id="433f9-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="433f9-145">Planification des annuaires de conférence</span><span class="sxs-lookup"><span data-stu-id="433f9-145">Planning for Conference Directories</span></span>

<span data-ttu-id="433f9-146">Les annuaires de conférence maintiennent un mappage entre l’ID de réunion alphanumérique qu’un participant utilise pour participer à une conférence en utilisant Lync 2013 et l’ID de conférence numérique uniquement qu’un participant de conférence rendez-vous utilise pour rejoindre la Conférence.</span><span class="sxs-lookup"><span data-stu-id="433f9-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="433f9-147">Le format de l’ID de conférence est le suivant :</span><span class="sxs-lookup"><span data-stu-id="433f9-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="433f9-148">La création de plusieurs annuaires de conférences permet de s’assurer que les ID de conférence resteront courts jusqu’à ce qu’une quantité importante de conférences ait été créée.</span><span class="sxs-lookup"><span data-stu-id="433f9-148">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="433f9-149">Dans une organisation avec un nombre classique de conférences par utilisateur, nous vous recommandons de créer un annuaire de conférences pour chaque 999 utilisateurs du pool.</span><span class="sxs-lookup"><span data-stu-id="433f9-149">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="433f9-150">À l’aide de cette instruction, les ID de conférence peuvent généralement être réduits.</span><span class="sxs-lookup"><span data-stu-id="433f9-150">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="433f9-151">Toutefois, une fois que le nombre d’annuaires de conférence (dans les pools) est supérieur à 9, le numéro d’identification de conférence augmentera pour prendre en charge des conférences supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="433f9-151">However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="433f9-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="433f9-152">See Also</span></span>


[<span data-ttu-id="433f9-153">Composant de serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="433f9-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="433f9-154">Plans de numérotation et règles de normalisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="433f9-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

