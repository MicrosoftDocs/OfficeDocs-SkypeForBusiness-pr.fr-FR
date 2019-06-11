---
title: 'Lync Server 2013: vue d’ensemble de la prise d’appel de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 132d987b7d8007873a27cd74aacfc11e0c882c39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="7a261-102">Présentation de l’enlèvement de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a261-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a261-103">_**Dernière modification de la rubrique:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="7a261-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="7a261-104">Le prélèvement d’appels de groupe, une nouvelle fonctionnalité dans les mises à jour cumulatives de Lync Server 2013: février 2013, permet aux utilisateurs de répondre aux appels entrants de leurs collègues à partir de leur propre téléphone.</span><span class="sxs-lookup"><span data-stu-id="7a261-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="7a261-105">Cette nouvelle fonctionnalité améliore la disponibilité de la ligne d’un utilisateur en permettant à d’autres utilisateurs de répondre à un appel entrant en composant un numéro de groupe.</span><span class="sxs-lookup"><span data-stu-id="7a261-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="7a261-106">Lors du déploiement de la prise d’appel de groupe, le nombre d’appels entrants vers la messagerie vocale peut être considérablement réduit, ce qui est particulièrement utile pour les appels provenant de clients extérieurs à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7a261-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="7a261-107">La fonctionnalité de cueillette des appels de groupe est conçue en particulier pour les unités d’entreprise dans les environnements Office ouverts.</span><span class="sxs-lookup"><span data-stu-id="7a261-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="7a261-108">Les appels entrants n’entraînent pas de perturbation, car ils sonnent uniquement sur le poste de leur destinataire.</span><span class="sxs-lookup"><span data-stu-id="7a261-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="7a261-109">Toutefois, les autres utilisateurs qui entendent la sonnerie peuvent prendre l’appel en composant simplement le numéro de groupe.</span><span class="sxs-lookup"><span data-stu-id="7a261-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="7a261-110">Dans les environnements dans lesquels les utilisateurs ne se trouvent pas dans une mise en page de bureau ouverte ou lorsque les utilisateurs qui partagent une responsabilité commune sont répartis géographiquement, l’équipe appelle la solution la plus adaptée.</span><span class="sxs-lookup"><span data-stu-id="7a261-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="7a261-111">La principale différence entre un appel de groupe et un appel d’équipe réside dans le fait que, si vous utilisez la fonction d’appel de groupe, un appel entrant sonne uniquement vers la destination prévue, mais tout le monde peut tout de même le répondre en composant un numéro de groupe.</span><span class="sxs-lookup"><span data-stu-id="7a261-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="7a261-112">Grâce à l’appel d’équipe, l’appel sonne sur le téléphone des membres de l’équipe, et n’importe quel utilisateur de l’équipe peut capter son téléphone pour répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="7a261-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="7a261-113">Une différence supplémentaire entre le prélèvement d’appels de groupe et l’appel d’équipe est la gestion par un administrateur des appels de groupe par le biais de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a261-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="7a261-114">Avec l’appel d’équipe, les utilisateurs finaux gèrent la fonctionnalité à l’aide du client Lync.</span><span class="sxs-lookup"><span data-stu-id="7a261-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="7a261-115">Ce choix est centralisé grâce à la fonction de redirection des appels de groupe.</span><span class="sxs-lookup"><span data-stu-id="7a261-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="7a261-116">La cueillette des appels de groupe repose sur l’application de stationnement d’appels.</span><span class="sxs-lookup"><span data-stu-id="7a261-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="7a261-117">Lorsque vous déployez un appel de groupe, vous configurez la table d’orbite du parc d’appels avec des plages distinctes de numéros d’extension désignés comme numéros de groupe de cueillette d’appel.</span><span class="sxs-lookup"><span data-stu-id="7a261-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="7a261-118">À l’image des numéros d’appel parqué, les numéros de groupe de prise d’appel doivent être des extensions virtuelles auxquelles n’est affecté aucun utilisateur ou téléphone.</span><span class="sxs-lookup"><span data-stu-id="7a261-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="7a261-119">Chaque pool frontal sur lequel vous déployez la capture d’appels de groupe peut avoir une ou plusieurs gammes de numéros de groupe de cueillette d’appel.</span><span class="sxs-lookup"><span data-stu-id="7a261-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="7a261-120">Les plages de numéros de groupe doivent être globalement uniques dans le déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a261-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a261-121">Les plages de nombres qui sont désignées en tant que numéros de capture d’appel de groupe dans la table de parc d’appels ne peuvent pas être gérées ou affichées à l’aide du panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a261-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="7a261-122">La seule façon d’afficher toutes les plages de chiffres dans la table de stationnement d’appels consiste à utiliser Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7a261-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="7a261-123">De même, la seule façon d’ajouter, de modifier ou de supprimer des numéros de capture d’appels de groupe consiste à utiliser Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7a261-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="7a261-p106">Après avoir configuré les numéros de groupe de prise d’appel, vous affectez les utilisateurs à un groupe de prise d’appel. Les appels destinés à un utilisateur membre d’un groupe de prise d’appel peuvent être pris par les autres utilisateurs. Lorsqu’un appel parvient à un utilisateur affecté à un groupe de prise d’appel, tout autre utilisateur qui remarque l’appel peut y répondre en composant manuellement le numéro du groupe de prise d’appel. Il n’est pas nécessaire que l’utilisateur qui prend l’appel soit membre du groupe. Lorsqu’un appel est pris par un autre utilisateur, une notification est envoyée au numéro initialement appelé.</span><span class="sxs-lookup"><span data-stu-id="7a261-p106">After you configure the call pickup group numbers, you assign users to a call pickup group. Any user who is assigned to a call pickup group can have their calls answered by other users. When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number. The user who picks up the call does not need to be a member of the group. When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a261-129">Un utilisateur ne peut être membre que d’un seul groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="7a261-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7a261-130">Même si tout utilisateur du déploiement de Lync Server peut répondre à un appel d’un membre d’un groupe de capture d’appel, la personne qui répond à l’appel doit connaître le numéro du groupe de capture d’appel approprié pour composer le numéro.</span><span class="sxs-lookup"><span data-stu-id="7a261-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="7a261-131">Si un utilisateur compose un numéro de groupe de prise d’appel pour répondre à un appel alors que plusieurs téléphones du groupe sonnent, il répond à l’appel qui a sonné en premier.</span><span class="sxs-lookup"><span data-stu-id="7a261-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="7a261-132">Les paramètres de sonnerie simultanée fonctionnent pour les utilisateurs qui bénéficient de la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="7a261-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="7a261-133">Autrement dit, un appel passé à un utilisateur disposant d’un appel de groupe sonne pour toutes les destinations configurées et un autre utilisateur peut répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="7a261-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="7a261-134">Toutefois, cette règle ne s’applique pas si l’utilisateur configure une sonnerie simultanée pour appeler tous les membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="7a261-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="7a261-135">La cueillette de groupe ne peut pas être utilisée pour répondre aux types d’appel suivants:</span><span class="sxs-lookup"><span data-stu-id="7a261-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="7a261-136">Appels à destination d’une ligne privée</span><span class="sxs-lookup"><span data-stu-id="7a261-136">Calls to a private line</span></span>

  - <span data-ttu-id="7a261-137">Appels en provenance d’un contact auquel a été affecté le niveau de confidentialité Famille et amis</span><span class="sxs-lookup"><span data-stu-id="7a261-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="7a261-138">Les utilisateurs qui sont membres d’un groupe de captures d’appels peuvent empêcher certains appels d’être récupérés par le biais du prélèvement d’appels de groupe en le marquant en tant que contact personnel dans le client Lync.</span><span class="sxs-lookup"><span data-stu-id="7a261-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="7a261-139">Pour marquer un contact en tant que contact personnel, définissez le niveau de confidentialité du contact sur Famille et amis.</span><span class="sxs-lookup"><span data-stu-id="7a261-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="7a261-140">Tout appel entrant provenant de contacts dont le niveau de confidentialité est défini sur amis et votre famille ne peut pas être récupéré à l’aide de la fonction de cueillette d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="7a261-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="7a261-141">Partie vidéo d’un appel audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="7a261-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a261-p109">Si un utilisateur répond à un appel audio/vidéo, il reçoit uniquement la partie audio. La personne qui passe l’appel ou celle qui y répond peut doter l’appel de la fonctionnalité vidéo.</span><span class="sxs-lookup"><span data-stu-id="7a261-p109">If a user answers an audio/video call, the user receives only the audio. Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="7a261-144">Appels à sonnerie simultanée routés vers les membres d’appel de l’équipe</span><span class="sxs-lookup"><span data-stu-id="7a261-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="7a261-145">Appels routés vers un délégué</span><span class="sxs-lookup"><span data-stu-id="7a261-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="7a261-146">Appels routés vers un service Response Group</span><span class="sxs-lookup"><span data-stu-id="7a261-146">Calls routed to a response group</span></span>

<span data-ttu-id="7a261-147">Les types d’utilisateurs suivants ne peuvent pas participer à la cueillette de groupe.</span><span class="sxs-lookup"><span data-stu-id="7a261-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="7a261-148">Autrement dit, ils ne doivent pas être inclus dans un groupe de prélèvement d’appels de groupe et ne peuvent pas répondre aux appels pour les utilisateurs disposant d’une cueillette de groupe activée.</span><span class="sxs-lookup"><span data-stu-id="7a261-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="7a261-149">Utilisateurs hébergés en ligne dans un déploiement hybride</span><span class="sxs-lookup"><span data-stu-id="7a261-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="7a261-150">Utilisateurs qui ne sont pas hébergés sur un pool Lync Server 2013 avec des mises à jour cumulatives pour Lync Server 2013:2013 février dans un déploiement local</span><span class="sxs-lookup"><span data-stu-id="7a261-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="7a261-p111">Si personne ne répond à un appel destiné à un membre d’un groupe de prise d’appel, l’appel est routé conformément au paramétrage défini dans les paramètres du client. En d’autres termes, l’appel est acheminé vers la messagerie vocale ou transféré à une autre destination.</span><span class="sxs-lookup"><span data-stu-id="7a261-p111">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings. That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

