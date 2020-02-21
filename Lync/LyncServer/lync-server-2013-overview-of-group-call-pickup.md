---
title: 'Lync Server 2013 : vue d’ensemble de la prise d’appel de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9001d3e89e07943915b923ec4bfa8abf2683c78
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="82700-102">Vue d’ensemble de la prise d’appel de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82700-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82700-103">_**Dernière modification de la rubrique :** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="82700-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="82700-104">Group Call Pick, une nouvelle fonctionnalité des mises à jour cumulatives pour Lync Server 2013 : février 2013, permet aux utilisateurs de répondre à leurs collègues à partir de leurs propres téléphones.</span><span class="sxs-lookup"><span data-stu-id="82700-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="82700-105">Cette nouvelle fonctionnalité augmente la disponibilité de la ligne d’un utilisateur en permettant à d’autres utilisateurs de répondre à un appel entrant en composant un numéro de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="82700-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="82700-106">Lorsque la prise d’appel de groupe est déployée, le nombre d’appels entrants acheminés vers la messagerie vocale peut être considérablement réduit, ce qui est particulièrement utile pour les appels provenant de clients externes à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="82700-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="82700-107">La fonctionnalité de prise d’appel de groupe est conçue en particulier pour les divisions dans des environnements Office ouverts.</span><span class="sxs-lookup"><span data-stu-id="82700-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="82700-108">Les appels entrants ne sont pas perturbés car ils ne sonnent qu’au niveau de destination prévu.</span><span class="sxs-lookup"><span data-stu-id="82700-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="82700-109">Toutefois, les autres utilisateurs qui entendent la sonnerie peuvent toujours reprendre l’appel en composant le numéro de groupe.</span><span class="sxs-lookup"><span data-stu-id="82700-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="82700-110">Dans les environnements où les utilisateurs ne se trouvent pas dans un aménagement de bureau ouvert ou dans lesquels les utilisateurs qui partagent une responsabilité commune sont répartis géographiquement, les appels d’équipe présentent la solution la plus appropriée.</span><span class="sxs-lookup"><span data-stu-id="82700-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="82700-111">La principale différence entre la prise d’appel de groupe et l’appel d’équipe est que, avec la prise d’appel de groupe, un appel entrant sonne uniquement à la destination prévue, mais tout le monde peut toujours choisir de le répondre en composant un numéro de groupe.</span><span class="sxs-lookup"><span data-stu-id="82700-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="82700-112">Avec l’appel d’équipe, l’appel sonne sur tous les téléphones des membres de l’équipe et n’importe quel utilisateur de l’équipe peut prendre le téléphone pour répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="82700-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="82700-113">Une autre différence entre la prise d’appel de groupe et l’appel d’équipe est que la prise d’appel de groupe est gérée par un administrateur via Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82700-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="82700-114">Avec l’appel d’équipe, les utilisateurs finaux gèrent la fonctionnalité à l’aide du client Lync.</span><span class="sxs-lookup"><span data-stu-id="82700-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="82700-115">Avec la prise d’appel de groupe, cet aspect de la gestion des appels peut donc être centralisé.</span><span class="sxs-lookup"><span data-stu-id="82700-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="82700-116">La prise d’appel de groupe est basée sur l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="82700-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="82700-117">Lorsque vous déployez la prise d’appel de groupe, vous configurez la table d’orbites de parcage d’appel avec des plages de numéros d’extension séparées qui sont désignées comme numéros de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="82700-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="82700-118">Comme les numéros d’orbite de parcage d’appel, les numéros de groupe de prise d’appel doivent être des extensions virtuelles auxquelles aucun utilisateur ou téléphone n’est affecté.</span><span class="sxs-lookup"><span data-stu-id="82700-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="82700-119">Chaque pool frontal où vous déployez la prise d’appel de groupe peut avoir une ou plusieurs plages de numéros de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="82700-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="82700-120">Les plages de numéros de groupe doivent être uniques au niveau global dans le déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82700-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="82700-121">Les plages de numéros qui sont désignées comme numéros de prise d’appel de groupe dans la table des orbites de parcage d’appel ne peuvent pas être gérées ou visualisées à l’aide du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82700-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="82700-122">La seule façon d’afficher toutes les plages de numéros dans la table des orbites de parcage d’appel consiste à utiliser Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="82700-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="82700-123">De même, la seule façon d’ajouter, de modifier ou de supprimer des numéros de prise d’appel de groupe est d’utiliser Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="82700-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="82700-124">Après avoir configuré les numéros de groupe de prise d’appel, vous affectez des utilisateurs à un groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="82700-124">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="82700-125">Tout utilisateur affecté à un groupe de prise d’appel peut faire en sorte que les appels soient traités par d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="82700-125">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="82700-126">Lorsqu’un appel arrive à un utilisateur affecté à un groupe de prise d’appel, tout autre utilisateur qui remarque l’appel peut y répondre en appelant manuellement le numéro de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="82700-126">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="82700-127">L’utilisateur qui sélectionne l’appel ne doit pas nécessairement être membre du groupe.</span><span class="sxs-lookup"><span data-stu-id="82700-127">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="82700-128">Lorsqu’un autre utilisateur reçoit un appel, une notification est envoyée au numéro initialement appelé.</span><span class="sxs-lookup"><span data-stu-id="82700-128">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="82700-129">Un utilisateur ne peut être membre que d’un seul groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="82700-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="82700-130">Bien que tous les utilisateurs du déploiement Lync Server puissent répondre à un appel à un membre du groupe de prise d’appel, la personne répondant à l’appel doit indiquer le numéro de groupe de prise d’appel correct à composer.</span><span class="sxs-lookup"><span data-stu-id="82700-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="82700-131">Si un utilisateur compose un numéro de groupe de prise d’appel pour répondre à un appel lorsque plusieurs téléphones dans le groupe sonnent, l’utilisateur répond à l’appel qui a été le plus long.</span><span class="sxs-lookup"><span data-stu-id="82700-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="82700-132">Les paramètres de sonnerie simultanée fonctionneront pour les utilisateurs disposant de la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="82700-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="82700-133">Autrement dit, un appel passé à un utilisateur disposant de la prise d’appel de groupe sonnera pour toutes les destinations configurées, et un autre utilisateur pourra répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="82700-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="82700-134">L’exception à cette règle est lorsque l’utilisateur configure la sonnerie simultanée pour appeler tous les membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="82700-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="82700-135">La prise d’appel de groupe ne peut pas être utilisée pour répondre aux types d’appels suivants :</span><span class="sxs-lookup"><span data-stu-id="82700-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="82700-136">Appels vers une ligne privée</span><span class="sxs-lookup"><span data-stu-id="82700-136">Calls to a private line</span></span>

  - <span data-ttu-id="82700-137">Appels à partir d’un contact auquel a été attribuée la relation de confidentialité amis et famille</span><span class="sxs-lookup"><span data-stu-id="82700-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="82700-138">Un utilisateur membre d’un groupe de prise d’appel peut empêcher l’extraction de certains appels via la prise d’appel de groupe en marquant le contact comme contact personnel dans le client Lync.</span><span class="sxs-lookup"><span data-stu-id="82700-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="82700-139">Pour marquer un contact comme contact personnel, définissez la relation de confidentialité du contact sur amis et famille.</span><span class="sxs-lookup"><span data-stu-id="82700-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="82700-140">Les appels entrants provenant de contacts dont la relation de confidentialité est définie sur amis et la famille ne peuvent pas être récupérés à l’aide de la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="82700-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="82700-141">Partie vidéo des appels audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="82700-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82700-142">Si un utilisateur répond à un appel audio/vidéo, il reçoit uniquement l’audio.</span><span class="sxs-lookup"><span data-stu-id="82700-142">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="82700-143">La personne qui appelle ou la personne qui répond à l’appel peut escalader l’appel pour ajouter de la vidéo.</span><span class="sxs-lookup"><span data-stu-id="82700-143">Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="82700-144">Appels de sonnerie simultanés routés vers les membres de l’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="82700-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="82700-145">Appels routés vers un délégué</span><span class="sxs-lookup"><span data-stu-id="82700-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="82700-146">Appels routés vers un groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="82700-146">Calls routed to a response group</span></span>

<span data-ttu-id="82700-147">Les types d’utilisateurs suivants ne peuvent pas participer à la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="82700-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="82700-148">Autrement dit, ils ne doivent pas être inclus dans un groupe de prise d’appel de groupe et ne peuvent pas reprendre d’appels pour les utilisateurs qui ont activé la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="82700-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="82700-149">Utilisateurs hébergés en ligne dans un déploiement hybride</span><span class="sxs-lookup"><span data-stu-id="82700-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="82700-150">Les utilisateurs qui ne sont pas hébergés sur un pool Lync Server 2013 avec des mises à jour cumulatives pour Lync Server 2013 : février 2013 dans un déploiement local</span><span class="sxs-lookup"><span data-stu-id="82700-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="82700-151">Si personne ne répond à un appel à un membre d’un groupe de prise d’appel, l’appel est acheminé comme indiqué dans les paramètres du client.</span><span class="sxs-lookup"><span data-stu-id="82700-151">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="82700-152">Autrement dit, l’appel passe à la messagerie vocale ou est transféré vers une destination différente, comme indiqué dans les paramètres du client.</span><span class="sxs-lookup"><span data-stu-id="82700-152">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

