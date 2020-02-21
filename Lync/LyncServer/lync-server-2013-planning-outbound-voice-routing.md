---
title: 'Lync Server 2013 : planification du routage des communications vocales sortantes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2fd202d6526f1f093c5824944ffdf3aa58317a2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a><span data-ttu-id="90ac4-102">Planification du routage des communications vocales sortantes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90ac4-102">Planning outbound voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90ac4-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="90ac4-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="90ac4-p101">Le routage des appels sortants s’applique aux appels destinés à une passerelle PSTN, une jonction SIP ou un système PBX. Lorsqu’un utilisateur passe un appel, le serveur normalise le numéro de téléphone au format E.164 et tente de le faire correspondre à un URI SIP. Si le serveur ne parvient pas à établir de correspondance, il applique la logique de routage des appels sortants en fonction de la chaîne de numérotation fournie. Les paramètres de serveur du tableau ci-dessous permettent de configurer la logique de routage des appels sortants.</span><span class="sxs-lookup"><span data-stu-id="90ac4-p101">Outbound call routing applies to calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX). When a user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI. If the server cannot make the match, it applies outbound call routing logic based on the supplied dial string. You define that logic by configuring the server settings that are described in the following table.</span></span>

### <a name="lync-server-outbound-call-routing-settings"></a><span data-ttu-id="90ac4-108">Paramètres de routage des appels sortants Lync Server</span><span class="sxs-lookup"><span data-stu-id="90ac4-108">Lync Server Outbound Call Routing Settings</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90ac4-109">Objet</span><span class="sxs-lookup"><span data-stu-id="90ac4-109">Object</span></span></th>
<th><span data-ttu-id="90ac4-110">Description</span><span class="sxs-lookup"><span data-stu-id="90ac4-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90ac4-111">Plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="90ac4-111">Dial Plan</span></span></p></td>
<td><p><span data-ttu-id="90ac4-112">Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="90ac4-112">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90ac4-113">Règle de normalisation</span><span class="sxs-lookup"><span data-stu-id="90ac4-113">Normalization rule</span></span></p></td>
<td><p><span data-ttu-id="90ac4-p102">Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont acheminés vers chaque emplacement, utilisateur ou objet contact. La même chaîne de numérotation peut être interprétée et traduite différemment selon l’emplacement d’origine de la numérotation et la personne ou l’objet contact passant l’appel. Un ensemble de règles de normalisation associées à un emplacement particulier constitue un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="90ac4-p102">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object that makes the call. A set of normalization rules associated with a particular location constitutes a dial plan.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90ac4-117">Stratégie de la voix</span><span class="sxs-lookup"><span data-stu-id="90ac4-117">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="90ac4-p103">Une stratégie de voix associe un ou plusieurs enregistrements d’utilisation PSTN à un utilisateur ou groupe d’utilisateurs. Elle fournit également une liste de fonctionnalités d’appel que vous pouvez activer ou désactiver.</span><span class="sxs-lookup"><span data-stu-id="90ac4-p103">A voice policy associates one or more PSTN usage records with one user or a group of users. A voice policy also provides a list of calling features that you can enable or disable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90ac4-120">Enregistrement d’utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="90ac4-120">PSTN usage record</span></span></p></td>
<td><p><span data-ttu-id="90ac4-121">Un enregistrement d’utilisation PTSN indique une classe d’appel (interne, local ou longue distance) qui peut être passée par différents utilisateurs, ou groupes d’utilisateurs, dans une organisation.</span><span class="sxs-lookup"><span data-stu-id="90ac4-121">A PSTN usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users, or groups of users, in an organization.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90ac4-122">Itinéraire d’appel</span><span class="sxs-lookup"><span data-stu-id="90ac4-122">Call Route</span></span></p></td>
<td><p><span data-ttu-id="90ac4-p104">Un itinéraire d’appel associe les numéros de téléphone cibles à des jonctions et des enregistrements d’utilisation PTSN spécifiques. Une passerelle PSTN est considérée comme une jonction.</span><span class="sxs-lookup"><span data-stu-id="90ac4-p104">A call route associates destination phone numbers with particular trunks and PSTN usage records. A PSTN gateway is considered a trunk.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="90ac4-125">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="90ac4-125">In This Section</span></span>

<span data-ttu-id="90ac4-126">Cette section explique comment configurer les paramètres serveur de routage des appels sortants suivants :</span><span class="sxs-lookup"><span data-stu-id="90ac4-126">This section provides guidelines for configuring the following outbound call routing server settings:</span></span>

  - <span></span>  
    [<span data-ttu-id="90ac4-127">Plans de numérotation et règles de normalisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90ac4-127">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [<span data-ttu-id="90ac4-128">Stratégies de voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90ac4-128">Voice policies in Lync Server 2013</span></span>](lync-server-2013-voice-policies.md)

  - <span></span>  
    [<span data-ttu-id="90ac4-129">Enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90ac4-129">PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [<span data-ttu-id="90ac4-130">Itinéraires des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90ac4-130">Voice routes in Lync Server 2013</span></span>](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="90ac4-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90ac4-131">See Also</span></span>


[<span data-ttu-id="90ac4-132">Jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90ac4-132">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)  
[<span data-ttu-id="90ac4-133">Connexions SIP directes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90ac4-133">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

