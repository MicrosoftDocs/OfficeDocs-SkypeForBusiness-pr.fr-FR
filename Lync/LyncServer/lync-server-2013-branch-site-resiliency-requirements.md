---
title: 'Lync Server 2013 : configuration requise pour la résistance des sites de succursale'
description: 'Lync Server 2013 : configuration requise pour la résistance des sites de succursale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef05917fb53d1333895236e849cb54596cc41947
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555080"
---
# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a><span data-ttu-id="e08f7-103">Configuration requise pour la résistance des sites de succursale pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e08f7-103">Branch-site resiliency requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e08f7-104">_**Dernière modification de la rubrique :** 2014-02-25_</span><span class="sxs-lookup"><span data-stu-id="e08f7-104">_**Topic Last Modified:** 2014-02-25_</span></span>

<span data-ttu-id="e08f7-105">Cette rubrique a pour but de vous aider à préparer les utilisateurs à la résistance des sites de succursale et à la survivabilité de la messagerie vocale, et indique également les configurations matérielles et logicielles correspondantes requises.</span><span class="sxs-lookup"><span data-stu-id="e08f7-105">This topic will help you to prepare users for branch-site resiliency and voice mail survivability, and also specifies the relevant hardware and software requirements.</span></span>

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a><span data-ttu-id="e08f7-106">Préparation des utilisateurs de succursale à la résistance des sites de succursale</span><span class="sxs-lookup"><span data-stu-id="e08f7-106">Preparing Branch Users for Branch-Site Resiliency</span></span>

<span data-ttu-id="e08f7-107">Préparez les utilisateurs à la résistance des sites de succursale en définissant leur pool de serveurs d’inscriptions comme étant le Survivable Branch Appliance (SBA) ou le serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="e08f7-107">Prepare users for branch-site resiliency by setting their Registrar pool as the Survivable Branch Appliance (SBA) or Survivable Branch Server.</span></span>

<div>

## <a name="registrar-assignments-for-branch-users"></a><span data-ttu-id="e08f7-108">Assignations de serveurs d’inscriptions aux utilisateurs de succursale</span><span class="sxs-lookup"><span data-stu-id="e08f7-108">Registrar Assignments for Branch Users</span></span>

<span data-ttu-id="e08f7-109">Quelle que soit la solution de résistance de site de succursale que vous choisissez, vous devrez affecter un serveur d’inscriptions principal à chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e08f7-109">Regardless of which branch-site resiliency solution you choose, you will need to assign a primary Registrar to each user.</span></span> <span data-ttu-id="e08f7-110">Les utilisateurs de site de succursale doivent toujours s’inscrire auprès du serveur d’inscriptions sur le site de succursale, que ce serveur d’inscriptions réside dans le Survivable Branch appliance, le serveur Survivable Branch Server ou le serveur autonome Lync Server 2013 ou Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="e08f7-110">Branch site users should always register with the Registrar at the branch site, regardless of whether that Registrar resides in the Survivable Branch Appliance, Survivable Branch Server, or stand-alone Lync Server 2013 Standard or Enterprise Edition server.</span></span> <span data-ttu-id="e08f7-111">Un enregistrement de ressource de service (SRV) DNS (Domain Name System) est requis pour qu’un client puisse détecter automatiquement son pool de serveurs d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="e08f7-111">A domain name system (DNS) service (SRV) resource record is required so that a client can discover its Registrar pool.</span></span> <span data-ttu-id="e08f7-112">Si le Survivable Branch Appliance devient indisponible, les clients du site de succursale découvrent automatiquement le serveur d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="e08f7-112">If the Survivable Branch Appliance becomes unavailable, this is how branch site clients will automatically discover the backup Registrar.</span></span>

<span data-ttu-id="e08f7-113">Si un site de succursale ne dispose pas d’un serveur DNS, il existe deux autres façons de configurer la découverte du Survivable Branch Appliance ou du serveur Survivable Branch Server :</span><span class="sxs-lookup"><span data-stu-id="e08f7-113">If a branch site does not have a DNS server, there are two alternative ways to configure discovery of the Survivable Branch Appliance or Survivable Branch Server:</span></span>

  - <span data-ttu-id="e08f7-114">Configurez l’option DHCP 120 sur le serveur DHCP (Dynamic Host Configuration Protocol) du site de succursale pour qu’elle pointe vers le nom de domaine complet (FQDN) du Survivable Branch Appliance ou du serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="e08f7-114">Configure DHCP option 120 on the branch site’s Dynamic Host Configuration Protocol (DHCP) server to point to the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="e08f7-115">Configurez le Survivable Branch Appliance ou le serveur Survivable Branch Server pour répondre aux requêtes DHCP 120.</span><span class="sxs-lookup"><span data-stu-id="e08f7-115">Configure the Survivable Branch Appliance or Survivable Branch Server to respond to DHCP 120 queries.</span></span>

</div>

<div>

## <a name="voice-routing-for-branch-users"></a><span data-ttu-id="e08f7-116">Routage des communications vocales des utilisateurs de succursale</span><span class="sxs-lookup"><span data-stu-id="e08f7-116">Voice Routing for Branch Users</span></span>

<span data-ttu-id="e08f7-117">Nous vous recommandons de créer une stratégie VoIP (Voice over Internet Protocol) distincte au niveau de l’utilisateur pour les utilisateurs d’un site de succursale.</span><span class="sxs-lookup"><span data-stu-id="e08f7-117">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span></span> <span data-ttu-id="e08f7-118">Cette stratégie doit inclure un itinéraire principal qui utilise le Survivable Branch Appliance ou une passerelle de serveur de succursale, ainsi qu’un ou plusieurs itinéraires de sauvegarde qui utilisent une jonction avec une passerelle PSTN (réseau téléphonique commuté) sur le site central.</span><span class="sxs-lookup"><span data-stu-id="e08f7-118">This policy should include a primary route that uses the Survivable Branch Appliance or branch server gateway, and one or more backup routes that use a trunk with a public switched telephone network (PSTN) gateway at the central site.</span></span> <span data-ttu-id="e08f7-119">Si l’itinéraire principal n’est pas disponible, l’itinéraire de sauvegarde qui utilise une ou plusieurs passerelles de site central est utilisé à la place.</span><span class="sxs-lookup"><span data-stu-id="e08f7-119">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span></span> <span data-ttu-id="e08f7-120">De cette façon, quel que soit l’emplacement d’enregistrement d’un utilisateur, sur le serveur de succursale ou sur le pool de serveurs d’inscriptions de sauvegarde du site central, la stratégie VoIP de l’utilisateur est toujours en vigueur.</span><span class="sxs-lookup"><span data-stu-id="e08f7-120">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span></span> <span data-ttu-id="e08f7-121">Il s’agit d’une considération importante pour les scénarios de basculement.</span><span class="sxs-lookup"><span data-stu-id="e08f7-121">This is an important consideration for failover scenarios.</span></span> <span data-ttu-id="e08f7-122">Par exemple, si vous devez renommer le Survivable Branch Appliance ou reconfigurer le Survivable Branch Appliance pour qu’il se connecte à un pool de serveurs d’inscriptions de sauvegarde sur le site central, vous devez déplacer les utilisateurs du site de succursale vers le site central pendant toute la durée.</span><span class="sxs-lookup"><span data-stu-id="e08f7-122">For example, if you need to rename the Survivable Branch Appliance or reconfigure the Survivable Branch Appliance to connect to a backup Registrar pool at the central site, then you must move branch site users to the central site for the duration.</span></span> <span data-ttu-id="e08f7-123">(Pour plus d’informations sur la modification du nom ou la reconfiguration d’un Survivable Branch appliance, voir [annexe B : gestion d’un Survivable Branch Appliance dans Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) dans la documentation de déploiement.) Si ces utilisateurs ne disposent pas de stratégies VoIP au niveau utilisateur ou de plans de numérotation au niveau de l’utilisateur, lorsque les utilisateurs sont déplacés vers un autre site, les stratégies VoIP au niveau du site et les plans de numérotation au niveau du site du site central s’appliquent par défaut aux utilisateurs, et non aux stratégies VoIP et aux plans de numérotation du site de succursale</span><span class="sxs-lookup"><span data-stu-id="e08f7-123">(For details about renaming or reconfiguring a Survivable Branch Appliance, see [Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in the Deployment documentation.) If those users do not have user-level VoIP policies or user-level dial plans, when the users are moved to another site, the site-level VoIP policies and site-level dial plans of the central site apply to the users by default, instead of the branch site site-level VoIP policies and dial plans,.</span></span> <span data-ttu-id="e08f7-124">Dans ce scénario, sauf si les stratégies VoIP au niveau du site et les plans de numérotation au niveau du site utilisés par le pool de serveurs d’inscriptions de sauvegarde peuvent également s’appliquer aux utilisateurs du site de succursale, leurs appels échouent.</span><span class="sxs-lookup"><span data-stu-id="e08f7-124">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span></span> <span data-ttu-id="e08f7-125">Par exemple, si des utilisateurs d’un site de succursale situé au Japon sont déplacés vers un site central à Redmond, un plan de numérotation avec des règles de normalisation qui précèdent + 1425 à tous les appels à 7 chiffres est peu susceptible de traduire correctement les appels pour ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e08f7-125">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e08f7-126">Lorsque vous créez un itinéraire alternatif de succursale, nous vous conseillons d’ajouter deux enregistrements d’utilisation téléphonique PSTN à la stratégie utilisateur de succursale et d’assigner des itinéraires séparés à chacun d’entre eux.</span><span class="sxs-lookup"><span data-stu-id="e08f7-126">When you create a branch office backup route, we recommend that you add two PSTN phone usage records to the branch office user policy and assign separate routes to each one.</span></span> <span data-ttu-id="e08f7-127">Le premier itinéraire, ou principal, achemine les appels vers la passerelle associée au Survivable Branch Appliance (SBA) ou au serveur de succursale ; la deuxième ou la sauvegarde de l’itinéraire dirige les appels vers la passerelle sur le site central.</span><span class="sxs-lookup"><span data-stu-id="e08f7-127">The first, or primary, route would direct calls to the gateway associated with the Survivable Branch Appliance (SBA) or branch server; the second, or backup, route would direct calls to the gateway at the central site.</span></span> <span data-ttu-id="e08f7-128">En dirigeant les appels, le SBA ou le serveur de succursale tente tous les itinéraires assignés au premier enregistrement d’utilisation PSTN avant d’essayer le deuxième enregistrement.</span><span class="sxs-lookup"><span data-stu-id="e08f7-128">In directing calls, the SBA or branch server will attempt all routes assigned to the first PSTN usage record before attempting the second usage record.</span></span>



</div>

<span data-ttu-id="e08f7-129">Pour garantir que les appels entrants vers les utilisateurs de sites de succursale atteindront ces utilisateurs lorsque la passerelle de succursale ou le composant Windows du site Survivable Branch Appliance est indisponible (ce qui se produirait par exemple, si le Survivable Branch Appliance ou la passerelle de succursale était inactif pour maintenance), créez un itinéraire de basculement sur la passerelle (ou travaillez avec votre fournisseur de services d’accès direct à la sauvegarde) pour rediriger les appels entrants vers le pool de serveurs d’inscriptions de sauvegarde sur le site central.</span><span class="sxs-lookup"><span data-stu-id="e08f7-129">To help ensure that inbound calls to branch site users will reach those users when the branch gateway or the Windows component of the Survivable Branch Appliance site is unavailable (which would happen, for example, if the Survivable Branch Appliance or branch gateway were down for maintenance), create a failover route on the gateway (or work with your Direct Inward Dialing (DID) provider) to redirect incoming calls to the backup Registrar pool at the central site.</span></span> <span data-ttu-id="e08f7-130">À partir de là, les appels sont routés sur la liaison de réseau étendu (WAN) en direction des utilisateurs de succursale.</span><span class="sxs-lookup"><span data-stu-id="e08f7-130">From there, the calls will be routed over the WAN link to branch users.</span></span> <span data-ttu-id="e08f7-131">Assurez-vous que l’itinéraire traduit les numéros selon les formats de numéro de téléphone acceptés par la passerelle PSTN ou un autre homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="e08f7-131">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span></span> <span data-ttu-id="e08f7-132">Pour plus d’informations sur la création d’un itinéraire de basculement, voir [configuration d’un itinéraire de basculement dans Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span><span class="sxs-lookup"><span data-stu-id="e08f7-132">For details about creating a failover route, see [Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span></span> <span data-ttu-id="e08f7-133">De même, créez des plans de numérotation au niveau du service pour la jonction associée à la passerelle du site de succursale afin de normaliser les appels entrants.</span><span class="sxs-lookup"><span data-stu-id="e08f7-133">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span></span> <span data-ttu-id="e08f7-134">Si vous avez deux Survivable Branch Appliances sur un site de succursale, vous pouvez créer un plan de numérotation au niveau du site pour les deux, sauf si un plan de niveau de service distinct est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e08f7-134">If you have two Survivable Branch Appliances at a branch site, you can create a site-level dial plan for both unless a separate service-level plan for each is necessary.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e08f7-135">Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central.</span><span class="sxs-lookup"><span data-stu-id="e08f7-135">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as if the user were registered with the central site.</span></span> <span data-ttu-id="e08f7-136">Il n’existe actuellement aucune limite au nombre d’utilisateurs de site de succursale, y compris les utilisateurs enregistrés avec un Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="e08f7-136">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>



</div>

<span data-ttu-id="e08f7-137">Nous vous recommandons également de créer un plan de numérotation et une stratégie de voix au niveau utilisateur, et de les affecter aux utilisateurs de site de succursale.</span><span class="sxs-lookup"><span data-stu-id="e08f7-137">We also recommend that you create a user-level dial plan and voice policy, and then assign it to branch site users.</span></span> <span data-ttu-id="e08f7-138">Pour plus d’informations, reportez-vous à la rubrique [Create a dial plan in Lync server 2013](lync-server-2013-create-a-dial-plan.md) et [Create the VoIP Routing Policy for Branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="e08f7-138">For details, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) and [Create the VoIP routing policy for branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in the Deployment documentation.</span></span>

<div>

## <a name="routing-extension-numbers"></a><span data-ttu-id="e08f7-139">Acheminement des numéros de poste</span><span class="sxs-lookup"><span data-stu-id="e08f7-139">Routing Extension Numbers</span></span>

<span data-ttu-id="e08f7-140">Lors de la préparation des plans de numérotation et des stratégies de voix pour les utilisateurs des sites de succursale, n’oubliez pas d’inclure des règles de normalisation et des règles de traduction qui correspondent aux chaînes et au format de nombre utilisés dans l’attribut msRTCSIP-Line (ou URI de ligne), de sorte que les appels de Lync 2013 activés entre les utilisateurs de site de succursale et les utilisateurs de site central soient acheminés correctement, en particulier lorsque les appels doivent être réacheminés via le réseau téléphonique commuté</span><span class="sxs-lookup"><span data-stu-id="e08f7-140">When preparing dial plans and voice policies for branch site users, be sure to include normalization rules and translation rules that match the strings and number format used in the msRTCSIP-line (or Line URI) attribute, so that Lync 2013 calls enabled between branch site users and central site users will be routed correctly—particularly when calls must be rerouted over the PSTN because the WAN link is unavailable.</span></span> <span data-ttu-id="e08f7-141">D’autres éléments particuliers sont à prendre en considération dans le cas des numéros composés qui incluent des numéros de poste et non simplement des numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="e08f7-141">Additionally, there are special considerations for dialed numbers that include extension numbers, rather just phone numbers.</span></span>

<span data-ttu-id="e08f7-p108">Les règles de normalisation et de traduction qui correspondent à des URI de ligne contenant un numéro de poste, seul ou en plus d’un numéro de téléphone E.164 complet, imposent des exigences supplémentaires. Cette section décrit plusieurs exemples de scénarios pour acheminer les appels pour des URI de ligne constitués d’un numéro de poste.</span><span class="sxs-lookup"><span data-stu-id="e08f7-p108">Normalization rules and translations rules that match Line URIs that contain an extension number, whether exclusively or in addition to a full E.164 phone number, have additional requirements. This section describes several example scenarios to route calls for Line URIs with an extension number.</span></span>

<span data-ttu-id="e08f7-p109">Si votre organisation n’a pas de numéros de téléphone SDA (Sélection directe à l’arrivée) configurés pour les utilisateurs et que l’URI de ligne de chaque utilisateur est configuré avec *uniquement* un numéro de poste, les utilisateurs internes peuvent s’appeler en composant uniquement le numéro de poste. Toutefois, vous devez configurer des règles de normalisation qui puissent s’appliquer aux appels d’un utilisateur d’un site de succursale à destination d’un utilisateur du site central qui correspondent aux numéros de poste.</span><span class="sxs-lookup"><span data-stu-id="e08f7-p109">If your organization does not have Direct Inward Dial (DID) phone numbers configured for individual users and the Line URI of each user is configured with *only* an extension number, internal users can call one another by dialing only an extension number. However, you must configure normalization rules that can apply to calls from a branch site user to a central site user, that match the extension numbers.</span></span>

<span data-ttu-id="e08f7-p110">Dans un scénario où la liaison de réseau étendu entre un site de succursale et un site central est disponible, les appels des utilisateurs du site de succursale à destination des utilisateurs du site central ne nécessitent pas de règle de normalisation correspondante pour traduire le numéro, car l’appel n’est pas acheminé sur le réseau téléphonique commuté. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e08f7-p110">In a scenario where the WAN link between a branch site and a central site is available, calls from branch site users to central site users do not require the matching normalization rule to translate the number because the call is not routed over the PSTN. For example:</span></span>


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
<th><span data-ttu-id="e08f7-148">Nom de la règle</span><span class="sxs-lookup"><span data-stu-id="e08f7-148">Rule name</span></span></th>
<th><span data-ttu-id="e08f7-149">Description</span><span class="sxs-lookup"><span data-stu-id="e08f7-149">Description</span></span></th>
<th><span data-ttu-id="e08f7-150">Type de numéro</span><span class="sxs-lookup"><span data-stu-id="e08f7-150">Number pattern</span></span></th>
<th><span data-ttu-id="e08f7-151">Conversion</span><span class="sxs-lookup"><span data-stu-id="e08f7-151">Translation</span></span></th>
<th><span data-ttu-id="e08f7-152">Exemple</span><span class="sxs-lookup"><span data-stu-id="e08f7-152">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e08f7-153">5digitExtensions</span><span class="sxs-lookup"><span data-stu-id="e08f7-153">5digitExtensions</span></span></p></td>
<td><p><span data-ttu-id="e08f7-154">Ne traduit pas les numéros à 5 chiffres</span><span class="sxs-lookup"><span data-stu-id="e08f7-154">Does not translate 5-digit numbers</span></span></p></td>
<td><p><span data-ttu-id="e08f7-155">^(\d{5})$</span><span class="sxs-lookup"><span data-stu-id="e08f7-155">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="e08f7-156">$1</span><span class="sxs-lookup"><span data-stu-id="e08f7-156">$1</span></span></p></td>
<td><p><span data-ttu-id="e08f7-157">10001 n’est pas traduit</span><span class="sxs-lookup"><span data-stu-id="e08f7-157">10001 is not translated</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e08f7-p111">Vous devez également faire face aux scénarios de numéros de poste spécifiques où la liaison de réseau étendu entre un site de succursale et un site central n’est pas disponible et où un appel émanant d’un site de succursale doit être acheminé sur le réseau téléphonique commuté. En cas de panne de réseau étendu, si l’utilisateur d’un site de succursale appelle un utilisateur du site central en composant uniquement le numéro de poste de ce dernier, vous devez disposer d’une règle de traduction sortante qui ajoute le numéro de téléphone complet de l’utilisateur du site central. Si l’URI de ligne d’un utilisateur contient le numéro de téléphone complet de votre organisation et le numéro de poste unique de l’utilisateur au lieu d’un numéro de téléphone complet propre à l’utilisateur, vous devez disposer d’une règle de traduction sortante qui ajoute le numéro de téléphone complet de l’organisation. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e08f7-p111">You must also accommodate extension numbers for specific scenarios, such as when the WAN link between a branch site and central site is unavailable and a call from a branch site must be routed over the PSTN. During a WAN outage, if a branch site user calls a central site user only by dialing the central site user’s extension, you must have an outbound translation rule that adds the central site user’s full phone number. If a user’s Line URI contains your organization’s full phone number and the user’s unique extension number instead of a full phone number that is unique to the user, then you must have an outbound translation rule that adds your organization’s full phone number instead. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e08f7-162">Description</span><span class="sxs-lookup"><span data-stu-id="e08f7-162">Description</span></span></th>
<th><span data-ttu-id="e08f7-163">Modèle de correspondance</span><span class="sxs-lookup"><span data-stu-id="e08f7-163">Matching pattern</span></span></th>
<th><span data-ttu-id="e08f7-164">Conversion</span><span class="sxs-lookup"><span data-stu-id="e08f7-164">Translation</span></span></th>
<th><span data-ttu-id="e08f7-165">Exemple</span><span class="sxs-lookup"><span data-stu-id="e08f7-165">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e08f7-166">Traduit les numéros à 5 chiffres en numéro de téléphone d’utilisateur avec numéro de poste</span><span class="sxs-lookup"><span data-stu-id="e08f7-166">Translates 5-digit numbers to a user’s phone number and extension</span></span></p></td>
<td><p><span data-ttu-id="e08f7-167">^(\d{5})$</span><span class="sxs-lookup"><span data-stu-id="e08f7-167">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="e08f7-168">+ 14255550123 ; EXT = $1</span><span class="sxs-lookup"><span data-stu-id="e08f7-168">+14255550123;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="e08f7-169">10001 devient +14255550123;ext=10001</span><span class="sxs-lookup"><span data-stu-id="e08f7-169">10001 is translated to +14255550123;ext=10001</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e08f7-170">Traduit les numéros à 5 chiffres en numéro de téléphone de votre organisation complété du poste d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="e08f7-170">Translates 5-digit numbers to your organization’s phone number and a user’s extension</span></span></p></td>
<td><p><span data-ttu-id="e08f7-171">^(\d{5})$</span><span class="sxs-lookup"><span data-stu-id="e08f7-171">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="e08f7-172">+ 14255550100 ; EXT = $1</span><span class="sxs-lookup"><span data-stu-id="e08f7-172">+14255550100;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="e08f7-173">10001 devient +14255550100;ext=10001</span><span class="sxs-lookup"><span data-stu-id="e08f7-173">10001 is translated to +14255550100;ext=10001</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e08f7-p112">Dans ce scénario, si l’homologue de jonction qui traite le réacheminement vers le réseau téléphonique commuté ne prend pas en charge les numéros de poste, la règle de traduction sortante doit également supprimer le numéro de poste. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e08f7-p112">In this scenario, if the trunk peer that handles rerouting to the PSTN does not support extension numbers, then the outbound translation rule must also remove the extension number. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e08f7-176">Description</span><span class="sxs-lookup"><span data-stu-id="e08f7-176">Description</span></span></th>
<th><span data-ttu-id="e08f7-177">Modèle de correspondance</span><span class="sxs-lookup"><span data-stu-id="e08f7-177">Matching pattern</span></span></th>
<th><span data-ttu-id="e08f7-178">Conversion</span><span class="sxs-lookup"><span data-stu-id="e08f7-178">Translation</span></span></th>
<th><span data-ttu-id="e08f7-179">Exemple</span><span class="sxs-lookup"><span data-stu-id="e08f7-179">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e08f7-180">Supprime le poste des numéros de téléphone présentant un numéro de poste</span><span class="sxs-lookup"><span data-stu-id="e08f7-180">Removes extension from phone numbers with extensions</span></span></p></td>
<td><p><span data-ttu-id="e08f7-181">^\+(\d *); EXT = (\d*) $</span><span class="sxs-lookup"><span data-stu-id="e08f7-181">^\+(\d *);ext=(\d*)$</span></span></p></td>
<td><p><span data-ttu-id="e08f7-182">+ $1</span><span class="sxs-lookup"><span data-stu-id="e08f7-182">+$1</span></span></p></td>
<td><p><span data-ttu-id="e08f7-183">+14255550123;ext=10001 devient +14255550123</span><span class="sxs-lookup"><span data-stu-id="e08f7-183">+14255550123;ext=10001 is translated to +14255550123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e08f7-p113">Qu’une liaison de réseau étendu soit disponible ou pas, si votre organisation n’a pas de numéros SDA configurés pour les utilisateurs individuels et que l’URI de ligne d’un utilisateur contient le numéro de téléphone de votre organisation et le numéro de poste unique de l’utilisateur, vous devez configurer l’URI de ligne du numéro de téléphone de votre organisation avec un numéro joignable pour l’homologue de jonction ou la passerelle PSTN du site de succursale. Vous devez également configurer l’URI de ligne du numéro de téléphone de votre organisation de sorte qu’il contienne son propre poste unique pour les appels devant être acheminés vers ce numéro.</span><span class="sxs-lookup"><span data-stu-id="e08f7-p113">Whether or not a WAN link is available, if your organization does not have DID numbers configured for individual users and the Line URI for a user contains your organization’s phone number and the user’s unique extension number, then you must configure your organization’s phone number Line URI with a number that is reachable by the trunk peer or PSTN gateway at the branch site. You must also configure your organization’s phone number Line URI to include its own unique extension for calls to be routed to that number.</span></span>

<span data-ttu-id="e08f7-186">Pour plus d’informations sur les appels d’un utilisateur de site central vers un utilisateur de site de succursale lorsque la liaison de réseau étendu entre les deux sites n’est pas disponible, voir la section « Préparation à la survivabilité de la messagerie vocale » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="e08f7-186">For details about calls from a central site user to a branch site user when the WAN link between the sites is unavailable, see "Preparing for Voice Mail Survivability" later in this topic.</span></span> <span data-ttu-id="e08f7-187">Pour plus d’informations sur les plans de numérotation et les règles de normalisation, y compris d’autres exemples de règles, voir [Dial plans and Normalization Rules in Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) dans la documentation de planification et [Configuring Dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="e08f7-187">For details about dial plans and normalization rules, including other sample rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation and [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in the Deployment documentation.</span></span> <span data-ttu-id="e08f7-188">Pour plus d’informations sur les règles de traduction sortante, voir [règles de conversion dans Lync server 2013](lync-server-2013-translation-rules.md) dans la documentation de planification et [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="e08f7-188">For details about outbound translation rules, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md) in the Planning documentation and [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a><span data-ttu-id="e08f7-189">Préparation de la survavibilité de la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="e08f7-189">Preparing for Voice Mail Survivability</span></span>

<span data-ttu-id="e08f7-190">La messagerie unifiée Exchange est généralement installée uniquement sur un site central et non sur des sites de succursale.</span><span class="sxs-lookup"><span data-stu-id="e08f7-190">Exchange Unified Messaging (UM) is usually installed only at a central site and not at branch sites.</span></span> <span data-ttu-id="e08f7-191">Un appelant doit pouvoir laisser un message vocal, même si la liaison de réseau étendu entre un site de succursale et le site central n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="e08f7-191">A caller should be able to leave a voice mail message, even if the WAN link between branch site and central site is unavailable.</span></span> <span data-ttu-id="e08f7-192">Par conséquent, la configuration de l’URI de ligne pour le numéro de téléphone du standard automatique de messagerie unifiée Exchange qui fournit la messagerie vocale pour les utilisateurs de site de succursale nécessite des considérations spéciales, ainsi que la stratégie de voix, le plan de numérotation et les règles de normalisation applicables à ce numéro de messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="e08f7-192">As a result, configuring the Line URI for the Exchange UM Auto Attendant phone number that provides voice mail for branch site users requires special considerations, in addition to the voice policy, dial plan, and normalization rules applicable to that voice mail number.</span></span>

<span data-ttu-id="e08f7-193">Survivable Branch Appliances (SBA) et les serveurs Survivable Branch Server offrent une survivabilité de la messagerie vocale pour les utilisateurs de succursale lors d’une panne de réseau étendu.</span><span class="sxs-lookup"><span data-stu-id="e08f7-193">Survivable Branch Appliances (SBAs) and Survivable Branch Servers provide voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="e08f7-194">Plus précisément, si vous utilisez un Survivable Branch Appliance ou un serveur Survivable Branch Server et que le réseau étendu devient indisponible, le SBA ou le Survivable Branch Server redirige les appels sans réponse sur le RTC vers la messagerie unifiée Exchange au niveau du site central.</span><span class="sxs-lookup"><span data-stu-id="e08f7-194">Specifically, if you are using a Survivable Branch Appliance or Survivable Branch Server and the WAN becomes unavailable, the SBA or Survivable Branch Server reroutes unanswered calls over the PSTN to Exchange UM at the central site.</span></span> <span data-ttu-id="e08f7-195">Avec un SBA ou un serveur Survivable Branch Server, les utilisateurs peuvent également récupérer des messages vocaux via le RTC lors d’une panne de réseau étendu (WAN).</span><span class="sxs-lookup"><span data-stu-id="e08f7-195">With a SBA or Survivable Branch Server, users can also retrieve voice mail messages through the PSTN during a WAN outage.</span></span> <span data-ttu-id="e08f7-196">Enfin, pendant une panne de réseau étendu, le Survivable Branch Appliance ou le serveur Survivable Branch Server met en file d’attente les notifications d’appels manqués, puis les télécharge sur le serveur de messagerie unifiée Exchange lors de la restauration du réseau étendu.</span><span class="sxs-lookup"><span data-stu-id="e08f7-196">Finally, during a WAN outage the Survivable Branch Appliance or Survivable Branch Server queues missed-call notifications and then uploads them to the Exchange UM server when the WAN is restored.</span></span> <span data-ttu-id="e08f7-197">Pour vous assurer que le reroutage de messagerie vocale est résilient, veillez à ajouter une entrée pour le nom de domaine complet du pool de sites central et une entrée pour le nom de domaine complet du serveur Edge au fichier hosts sur le serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="e08f7-197">To help ensure that voice mail rerouting is resilient, be sure that you add an entry for the central site pool’s FQDN and an entry for the Edge Server FQDN to the hosts file on the Survivable Branch Server.</span></span> <span data-ttu-id="e08f7-198">À défaut, il est possible que la résolution DNS arrive à expiration si vous ne disposez pas de serveur DNS sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="e08f7-198">Otherwise, DNS resolution can time out if you do not have a DNS server at the branch site.</span></span>

<span data-ttu-id="e08f7-199">Pour configurer la survivabilité de la messagerie vocale pour les utilisateurs de site de succursale, les configurations suivantes sont recommandées :</span><span class="sxs-lookup"><span data-stu-id="e08f7-199">We recommend the following configurations for voice mail survivability for branch site users:</span></span>

  - <span data-ttu-id="e08f7-200">Un administrateur Microsoft Exchange doit configurer le standard automatique de messagerie unifiée Exchange (AA) pour qu’il accepte uniquement les messages.</span><span class="sxs-lookup"><span data-stu-id="e08f7-200">An Microsoft Exchange administrator should configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span> <span data-ttu-id="e08f7-201">Cette configuration désactive toutes les autres fonctions génériques, comme le transfert à un utilisateur ou un opérateur, et limite le rôle du standard automatique à la seule réception des messages.</span><span class="sxs-lookup"><span data-stu-id="e08f7-201">This configuration disables all other generic functionality, such as transfer to a user or transfer to an operator, and limits the AA to only accepting messages.</span></span> <span data-ttu-id="e08f7-202">Sinon, l’administrateur Exchange peut utiliser un standard automatique générique ou personnalisé pour router l’appel vers un opérateur.</span><span class="sxs-lookup"><span data-stu-id="e08f7-202">Alternatively, the Exchange administrator can use a generic AA or an AA customized to route the call to an operator.</span></span>

  - <span data-ttu-id="e08f7-203">L’administrateur Lync Server doit prendre le numéro de téléphone AA et utiliser ce numéro de téléphone comme numéro de **standard automatique de messagerie unifiée Exchange** dans les paramètres de réacheminement de la messagerie vocale pour le Survivable Branch Appliance ou le serveur de succursale.</span><span class="sxs-lookup"><span data-stu-id="e08f7-203">The Lync Server administrator should take the AA phone number and use that phone number as the **exchange um auto attendant** number in the voice mail rerouting settings for the Survivable Branch Appliance or branch server.</span></span>

  - <span data-ttu-id="e08f7-204">L’administrateur Lync Server doit obtenir le numéro de téléphone de l’accès abonné de la messagerie UNIFIÉe Exchange et utiliser ce numéro comme numéro d' **accès abonné** dans les paramètres de réacheminement de la messagerie vocale pour le Survivable Branch Appliance ou le serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="e08f7-204">The Lync Server administrator should get the Exchange UM subscriber access phone number and use that number as the **subscriber access** number in the voice mail rerouting settings for the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="e08f7-205">L’administrateur Lync Server doit configurer la messagerie unifiée Exchange de sorte qu’un seul plan de numérotation soit associé à tous les utilisateurs de succursale qui ont besoin d’accéder à la messagerie vocale pendant une panne de réseau étendu (WAN).</span><span class="sxs-lookup"><span data-stu-id="e08f7-205">The Lync Server administrator should configure Exchange UM so that only one dial plan is associated with all branch users who need access to voice mail during a WAN outage.</span></span>

  - <span data-ttu-id="e08f7-206">Lorsque la liaison de réseau étendu n’est pas disponible, les appels à destination des utilisateurs de site de succursale peuvent être acheminés vers la messagerie vocale de la messagerie unifiée Exchange de l’utilisateur, à condition toutefois que la stratégie de voix appliquée à l’appel spécifie un numéro de téléphone de messagerie vocale unique et qu’elle inclue un numéro de poste.</span><span class="sxs-lookup"><span data-stu-id="e08f7-206">When the WAN link is unavailable, calls to branch site users can be routed to the user’s Exchange Unified Messaging (UM) voice mailbox, but only if the voice policy applied to the call specifies a voice mail phone number that is unique and does not include an extension number.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a><span data-ttu-id="e08f7-207">Configuration matérielle et logicielle requise pour la résistance des sites de succursale</span><span class="sxs-lookup"><span data-stu-id="e08f7-207">Hardware and Software Requirements for Branch-Site Resiliency</span></span>

<span data-ttu-id="e08f7-208">La configuration matérielle et logicielle requise varie en fonction de la solution de résistance.</span><span class="sxs-lookup"><span data-stu-id="e08f7-208">The hardware and software requirements vary, depending on your resiliency solution.</span></span>

<div>

## <a name="requirements-for-survivable-branch-appliances"></a><span data-ttu-id="e08f7-209">Configuration requise pour les Survivable Branch Appliances</span><span class="sxs-lookup"><span data-stu-id="e08f7-209">Requirements for Survivable Branch Appliances</span></span>

<span data-ttu-id="e08f7-210">Le matériel et les logiciels requis sont intégrés dans le Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="e08f7-210">Required hardware and software is built into the Survivable Branch Appliance.</span></span> <span data-ttu-id="e08f7-211">Cependant, il est également recommandé que chaque site de succursale déploie un serveur DHCP afin d’obtenir des adresses IP du client ; sinon, lorsque le bail DHCP expire, les clients ne disposent plus de connectivité IP.</span><span class="sxs-lookup"><span data-stu-id="e08f7-211">However, we also recommend that each branch site deploy a DHCP server to obtain client IP addresses; otherwise, when the DHCP lease expires, clients will not have IP connectivity.</span></span>

<span data-ttu-id="e08f7-212">Si les serveurs DNS d’entreprise se trouvent uniquement dans des sites centraux, les utilisateurs de site de succursale ne pourront pas se connecter à eux lors d’une panne de réseau étendu, et par conséquent, la découverte de Lync Server qui utilise l’enregistrement de ressource SRV (SRV) DNS échouera.</span><span class="sxs-lookup"><span data-stu-id="e08f7-212">If the enterprise DNS servers are located only in central sites, branch site users will be unable to connect to them during a WAN outage, and therefore Lync Server discovery that uses DNS SRV (service (SRV) resource record) will fail.</span></span> <span data-ttu-id="e08f7-213">Pour garantir un réacheminement rapide lors d’une panne de réseau étendu, les enregistrements DNS doivent être mis en cache au niveau du site de succursale.</span><span class="sxs-lookup"><span data-stu-id="e08f7-213">To assure prompt rerouting during a WAN outage, DNS records must be cached at the branch site.</span></span> <span data-ttu-id="e08f7-214">Si le routeur de succursale prend en charge le cache DNS, activez-le à cette fin.</span><span class="sxs-lookup"><span data-stu-id="e08f7-214">If the branch router supports it, turn on DNS caching.</span></span> <span data-ttu-id="e08f7-215">Vous pouvez également déployer un serveur DNS au niveau de la succursale.</span><span class="sxs-lookup"><span data-stu-id="e08f7-215">Or, you can deploy a DNS server at the branch.</span></span> <span data-ttu-id="e08f7-216">Il peut s’agir d’un serveur autonome ou d’une version du Survivable Branch appliance qui prend en charge les fonctionnalités DNS.</span><span class="sxs-lookup"><span data-stu-id="e08f7-216">This can be a stand-alone server or a version of the Survivable Branch Appliance that supports DNS capabilities.</span></span> <span data-ttu-id="e08f7-217">Pour plus d’informations, contactez votre fournisseur Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="e08f7-217">For details, contact your Survivable Branch Appliance provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e08f7-218">Il n’est pas nécessaire de disposer d’un contrôleur de domaine sur un site de succursale.</span><span class="sxs-lookup"><span data-stu-id="e08f7-218">It is not necessary to have a domain controller at a branch site.</span></span> <span data-ttu-id="e08f7-219">Le Survivable Branch Appliance authentifie les clients à l’aide d’un certificat spécial qui envoie le client en réponse à la demande de certificat du client lorsqu’il se connecte.</span><span class="sxs-lookup"><span data-stu-id="e08f7-219">The Survivable Branch Appliance authenticates clients by using a special certificate that it sends the client in response to the client’s certificate request when it signs in.</span></span>



</div>

<span data-ttu-id="e08f7-220">Les clients Lync peuvent découvrir Lync Server à l’aide de l’option DHCP 120 (serveur d’inscriptions SIP).</span><span class="sxs-lookup"><span data-stu-id="e08f7-220">Lync clients can discover the Lync Server by using DHCP Option 120 (SIP Registrar Option).</span></span> <span data-ttu-id="e08f7-221">La configuration peut prendre l’une des deux formes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e08f7-221">This can be configured in one of two ways:</span></span>

  - <span data-ttu-id="e08f7-222">Configurez le serveur DHCP sur le site de succursale pour répondre aux requêtes DHCP 120, qui renvoient le nom de domaine complet du serveur d’inscriptions sur le Survivable Branch Appliance ou le serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="e08f7-222">Configure the DHCP server at the branch site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="e08f7-223">Activez le service DHCP Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e08f7-223">Turn on Lync Server DHCP.</span></span> <span data-ttu-id="e08f7-224">Lorsque cette option est activée, le serveur d’inscriptions Lync Server répond aux requêtes DHCP 120.</span><span class="sxs-lookup"><span data-stu-id="e08f7-224">When this is turned on, the Lync Server Registrar responds to DHCP Option 120 queries.</span></span> <span data-ttu-id="e08f7-225">Notez que le serveur d’inscriptions ne répond pas aux requêtes DHCP autres que DHCP, option 120.</span><span class="sxs-lookup"><span data-stu-id="e08f7-225">Note that the Registrar does not respond to any DHCP queries other than DHCP Options 120.</span></span>

<span data-ttu-id="e08f7-226">De plus, pour les sites de succursale plus importants disposant de plusieurs sous-réseaux, les agents de relais DHCP doivent être activés pour transférer les requêtes DHCP, option 120, au serveur DHCP (configuration 1) ou au serveur d’inscriptions (configuration 2).</span><span class="sxs-lookup"><span data-stu-id="e08f7-226">Additionally, for larger branch sites that have multiple subnets, DHCP relay agents should be enabled to forward DHCP Option 120 queries to the DHCP Server (configuration 1) or to the Registrar (configuration 2).</span></span>

<span data-ttu-id="e08f7-227">Pour finir, les utilisateurs de site de succursale doivent être configurés pour voix entreprise et être mis en service avec un point de terminaison de communications unifiées approprié.</span><span class="sxs-lookup"><span data-stu-id="e08f7-227">Finally, branch site users must be configured for Enterprise Voice and provisioned with an appropriate unified communications endpoint.</span></span>

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a><span data-ttu-id="e08f7-228">Configuration requise pour les serveurs Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="e08f7-228">Requirements for Survivable Branch Servers</span></span>

<span data-ttu-id="e08f7-229">La configuration requise pour les serveurs Survivable Branch Server est la même que pour un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="e08f7-229">The requirements for Survivable Branch Servers are the same as the requirements for a Front End Server.</span></span> <span data-ttu-id="e08f7-230">Pour plus d’informations, reportez-vous à la rubrique [Server Hardware Platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="e08f7-230">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a><span data-ttu-id="e08f7-231">Conditions requise pour les déploiements de sites de succursale Lync Server pleine échelle</span><span class="sxs-lookup"><span data-stu-id="e08f7-231">Requirements for Full-Scale Lync Server Branch-Site Deployments</span></span>

<span data-ttu-id="e08f7-232">Pour plus d’informations, reportez-vous à la rubrique [Determining Your infrastructure Requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="e08f7-232">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

