---
title: 'Lync Server 2013 : Stratégies de voix'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca1e72a1b62a224898d98aec7fcef9bc62ddf8bc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a><span data-ttu-id="c638b-102">Stratégies de voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c638b-102">Voice policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c638b-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c638b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c638b-104">*Politiques vocales* Lync Server définissez les éléments suivants pour chaque utilisateur, site ou organisation affecté à la stratégie:</span><span class="sxs-lookup"><span data-stu-id="c638b-104">Lync Server *voice policies* define the following for each user, site, or organization that is assigned the policy:</span></span>

  - <span data-ttu-id="c638b-105">Un ensemble de fonctionnalités d’appel qui peuvent être activées ou désactivées pour déterminer la fonctionnalité voix entreprise disponible aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c638b-105">A set of calling features that can be enabled or disabled to determine the Enterprise Voice functionality available to users.</span></span>

  - <span data-ttu-id="c638b-106">un ensemble d’enregistrements de l’utilisation du réseau téléphonique commuté (PSTN) qui définissent le type des appels autorisés.</span><span class="sxs-lookup"><span data-stu-id="c638b-106">A set of public switched telephone network (PSTN) usage records that define what types of calls are authorized.</span></span>

<div>

## <a name="planning-for-voice-policies"></a><span data-ttu-id="c638b-107">Planification des politiques vocales</span><span class="sxs-lookup"><span data-stu-id="c638b-107">Planning for Voice Policies</span></span>

<span data-ttu-id="c638b-108">Les étapes suivantes vous aideront à planifier les stratégies vocales dont vous aurez besoin pour votre déploiement voix entreprise:</span><span class="sxs-lookup"><span data-stu-id="c638b-108">The following steps will help you plan the voice policies that you will need for your Enterprise Voice deployment:</span></span>

  - <span data-ttu-id="c638b-109">Déterminez la configuration prévue de votre stratégie de voix globale (stratégie de voix par défaut installée avec le produit).</span><span class="sxs-lookup"><span data-stu-id="c638b-109">Determine how you will configure your global voice policy (the default voice policy that is installed with the product).</span></span> <span data-ttu-id="c638b-110">Ce paramètre s’applique à tous les utilisateurs de l’entreprise voix qui n’ont pas explicitement reçu une stratégie de niveau site ou par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c638b-110">This policy will apply to all Enterprise Voice users who are not explicitly assigned a site-level or per-user policy.</span></span>

  - <span data-ttu-id="c638b-111">Identifiez les stratégies de voix de niveau site dont vous avez éventuellement besoin.</span><span class="sxs-lookup"><span data-stu-id="c638b-111">Identify any site-level voice policies that you might need.</span></span>

  - <span data-ttu-id="c638b-112">Identifiez les stratégies de voix par utilisateur dont vous avez éventuellement besoin.</span><span class="sxs-lookup"><span data-stu-id="c638b-112">Identify any per-user voice policies that you might need.</span></span>

  - <span data-ttu-id="c638b-113">Décidez des fonctionnalités d’appel à activer pour chaque stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="c638b-113">Decide which call features to enable for each voice policy.</span></span>

  - <span data-ttu-id="c638b-114">Déterminez les enregistrements d’utilisation DNS à configurer pour chaque stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="c638b-114">Determine what PSTN usage records to configure for each voice policy.</span></span>

<div>

## <a name="voice-policy-scope"></a><span data-ttu-id="c638b-115">Étendue de stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="c638b-115">Voice Policy Scope</span></span>

<span data-ttu-id="c638b-116">L’*étendue de stratégie de voix* détermine le niveau hiérarchique auquel la stratégie peut être appliquée.</span><span class="sxs-lookup"><span data-stu-id="c638b-116">*Voice policy scope* determines the hierarchical level at which the policy can be applied.</span></span> <span data-ttu-id="c638b-117">Dans Lync Server, vous pouvez configurer des stratégies de voix avec les niveaux d’étendue suivants (classés du plus spécifique au plus général).</span><span class="sxs-lookup"><span data-stu-id="c638b-117">In Lync Server, you can configure voice policies with the following scope levels (listed from the most specific to the most general).</span></span>

  - <span data-ttu-id="c638b-p103">Une **stratégie de voix d’utilisateur** peut être affectée à des utilisateurs individuels, à des groupes ou à des objets contact. Il s’agit de la stratégie de plus bas niveau. Les stratégies de voix d’utilisateur peuvent être déployées afin d’activer des fonctionnalités pour certains utilisateurs ou groupes au niveau d’un site, mais pas pour les autres du même site. Par exemple, il peut être utile de désactiver la numérotation longue distance pour certains employés. Dans le cadre de l’affectation d’une stratégie de voix, un objet contact est traité comme un utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="c638b-p103">**User voice policy** can be assigned to individual users, groups, or contact objects. This is the lowest level policy. User voice policies can be deployed to enable features for certain users or groups at a site, but not for others in the same site. For example, you may want to disable long distance dialing for some employees. For the purpose of assigning a voice policy, a contact object is treated as an individual user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c638b-123">Nous vous recommandons de déployer une stratégie de voix utilisateur pour les utilisateurs de la voix de votre site de succursale et ceux qui sont inscrits auprès du déploiement de site central, ou les utilisateurs enregistrés sur une unité de succursale Survivable.</span><span class="sxs-lookup"><span data-stu-id="c638b-123">We recommend that you deploy a user voice policy for branch site Enterprise Voice users who are registered with the central site deployment, or users who are registered on a Survivable Branch Appliance.</span></span>

    
    </div>

  - <span data-ttu-id="c638b-p104">Une **stratégie de voix de site** s’applique à un site entier, à l’exception des utilisateurs, groupes ou objets contact affectés à une stratégie de voix d’utilisateur. Pour définir une stratégie de voix de site, vous devez spécifier le site auquel la stratégie s’applique. Si aucune stratégie de voix d’utilisateur n’est affectée, la stratégie de voix de site est utilisée.</span><span class="sxs-lookup"><span data-stu-id="c638b-p104">**Site voice policy** applies to an entire site, except for any users, groups, or contact objects that are assigned a user voice policy. To define a site voice policy, you must specify the site to which the policy applies. If a user voice policy is not assigned, the site voice policy is used.</span></span>

  - <span data-ttu-id="c638b-127">La **stratégie de voix globale** est la stratégie de voix par défaut installée avec le produit.</span><span class="sxs-lookup"><span data-stu-id="c638b-127">**Global voice policy** is the default voice policy that is installed with the product.</span></span> <span data-ttu-id="c638b-128">Vous pouvez modifier la stratégie de voix globale pour l’adapter aux besoins spécifiques de votre organisation, mais vous ne pouvez pas la renommer ou la supprimer.</span><span class="sxs-lookup"><span data-stu-id="c638b-128">You can edit the global voice policy to meet the specific needs of your organization, but you cannot rename or delete it.</span></span> <span data-ttu-id="c638b-129">Cette politique vocale s’applique à tous les utilisateurs, à tous les groupes et aux objets de contact Enterprise Voice dans votre déploiement, sauf si vous configurez et attribuez une stratégie vocale avec une étendue plus spécifique.</span><span class="sxs-lookup"><span data-stu-id="c638b-129">This voice policy applies to all Enterprise Voice users, groups, and contact objects in your deployment unless you configure and assign a voice policy with more specific scope.</span></span> <span data-ttu-id="c638b-130">Si vous souhaitez désactiver entièrement cette stratégie, assurez-vous que tous les sites et utilisateurs disposent de stratégies personnalisées affectées.</span><span class="sxs-lookup"><span data-stu-id="c638b-130">If you want to disable this policy entirely, be sure that all sites and users have custom policies assigned to them.</span></span>

</div>

<div>

## <a name="call-features"></a><span data-ttu-id="c638b-131">Fonctionnalités d’appel</span><span class="sxs-lookup"><span data-stu-id="c638b-131">Call Features</span></span>

<span data-ttu-id="c638b-132">Vous pouvez activer ou désactiver les fonctionnalités d’appel suivantes pour chaque stratégie de voix :</span><span class="sxs-lookup"><span data-stu-id="c638b-132">You can enable or disable the following call features for each voice policy:</span></span>

  - <span data-ttu-id="c638b-p106">**Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients. Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="c638b-p106">**Call forwarding** enables users to forward calls to other phones and client devices. Enabled by default.</span></span>

  - <span data-ttu-id="c638b-p107">**Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place. Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="c638b-p107">**Delegation** enables users to specify other users to send and receive calls on their behalf. Enabled by default.</span></span>

  - <span data-ttu-id="c638b-p108">**Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="c638b-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>

  - <span data-ttu-id="c638b-p109">**Parcage d’appel** permet aux utilisateurs de parquer des appels pour décrocher l’appel depuis un téléphone ou un client distinct. Désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="c638b-p109">**Call park** enables users to park calls and then pick up the call from a different phone or client. Disabled by default.</span></span>

  - <span data-ttu-id="c638b-p110">**Sonnerie simultanée** permet aux appels entrants de sonner sur un téléphone supplémentaire (par exemple, un téléphone mobile) ou sur d’autres périphériques de terminaison. Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="c638b-p110">**Simultaneous ringing** enables incoming calls to ring on an additional phone (for example, a mobile phone) or other endpoint devices. Enabled by default.</span></span>

  - <span data-ttu-id="c638b-p111">**Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre aux appels destinés à d’autres membres de l’équipe. Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="c638b-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>

  - <span data-ttu-id="c638b-p112">**Réacheminement PSTN** permet de réacheminer sur le réseau téléphonique commuté les appels effectués depuis des utilisateurs auxquels cette stratégie est affectée vers d’autres utilisateurs d’entreprise, si le réseau étendu est saturé ou indisponible. Activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="c638b-p112">**PSTN reroute** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>

  - <span data-ttu-id="c638b-p113">**Remplacement de stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie du contrôle d’admission des appels pour un utilisateur particulier. Désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="c638b-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>

  - <span data-ttu-id="c638b-149">Le **suivi des appels malveillants** permet aux utilisateurs de signaler des appels malveillants en utilisant le client Lync, puis de marquer ces appels dans les enregistrements des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="c638b-149">**Malicious call tracing** enables users to report malicious calls by using the Lync client, and then flags such calls in the call detail records.</span></span> <span data-ttu-id="c638b-150">Désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="c638b-150">Disabled by default.</span></span>

  - <span data-ttu-id="c638b-151">La boîte **vocale** d’arrêt empêche le routage des appels vers le système de messagerie vocale du téléphone mobile de l’utilisateur lorsqu’une sonnerie simultanée est configurée et que le téléphone est éteint, hors batterie ou en dehors de la plage et repose sur une valeur de minuteur.</span><span class="sxs-lookup"><span data-stu-id="c638b-151">**Voicemail escape** prevents calls from being immediately routed to the user’s mobile phone voicemail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range, and is based on a timer value.</span></span> <span data-ttu-id="c638b-152">Ce paramètre active et désactive le minuteur et définit la valeur de Timer.</span><span class="sxs-lookup"><span data-stu-id="c638b-152">This setting enables and disables the timer and sets the value of the timer.</span></span> <span data-ttu-id="c638b-153">Il peut être configuré uniquement à l’aide de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c638b-153">It can be configured only by using the Lync Server Management Shell.</span></span> <span data-ttu-id="c638b-154">Désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="c638b-154">Disabled by default.</span></span>

  - <span data-ttu-id="c638b-155">Le **transfert d’appel et la sonnerie simultanée des utilisations RTC** permettent aux administrateurs de spécifier la même utilisation PSTN que la stratégie vocale pour le transfert d’appel et la sonnerie simultanée, limiter le transfert d’appel et la sonnerie simultanée aux utilisateurs de Lync internes uniquement; vous pouvez ou spécifier une utilisation PSTN personnalisée qui est différente de l’utilisation du RTC de la stratégie vocale.</span><span class="sxs-lookup"><span data-stu-id="c638b-155">**Call forwarding and simultaneous ringing PSTN usages** enables administrators to specify the same PSTN usage as the voice policy for call forwarding and simultaneous ringing, restrict call forwarding and simultaneous ringing to internal Lync users only, or specify a custom PSTN usage that is different from the voice policy’s PSTN usage.</span></span> <span data-ttu-id="c638b-156">L’utilisation de la même utilisation PSTN que la stratégie de voix pour le transfert d’appel et la sonnerie simultanée est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="c638b-156">The default is to use the same PSTN usage as the voice policy for call forwarding and simultaneous ringing.</span></span>

</div>

<div>

## <a name="pstn-usage-records"></a><span data-ttu-id="c638b-157">Enregistrements d’utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="c638b-157">PSTN Usage Records</span></span>

<span data-ttu-id="c638b-158">Chaque stratégie de voix doit disposer d’un ou de plusieurs enregistrements d’utilisation PSTN associés.</span><span class="sxs-lookup"><span data-stu-id="c638b-158">Each voice policy should have one or more associated PSTN usage records.</span></span> <span data-ttu-id="c638b-159">Les utilisations PSTN peuvent être associées à la stratégie de voix pour les besoins de la sonnerie simultanée et du transfert d’appel uniquement.</span><span class="sxs-lookup"><span data-stu-id="c638b-159">PSTN usages can be associated with a voice policy for the purpose of simultaneous ringing and call forwarding only.</span></span> <span data-ttu-id="c638b-160">Pour plus d’informations sur la planification des enregistrements d’utilisation RTC, voir [enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="c638b-160">For details about planning PSTN usage records, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c638b-p118">L’ordre des utilisations PSTN est important parce que, lors de la mise en correspondance des utilisateurs et des itinéraires, la fonctionnalité de routage sortant compare les utilisations PSTN du haut vers le bas. Si la première utilisation correspond à l’itinéraire d’appel, cet itinéraire est utilisé. Sinon, la fonctionnalité de routage sortant examine l’utilisation PSTN suivante dans la liste et continue jusqu’à trouver une correspondance. Ainsi, les utilisations PSTN suivantes assurent une alternative si la première de la liste est indisponible.</span><span class="sxs-lookup"><span data-stu-id="c638b-p118">PSTN usage order is critical because in matching users to routes, the outbound routing functionality compares PSTN usages from top to bottom. If the first usage matches the call route, that route is used. If not, the outbound routing functionality looks at the next PSTN usage on the list and continues until a match is found. In effect, the subsequent PSTN usages provide backup if the first one on the list is unavailable.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

