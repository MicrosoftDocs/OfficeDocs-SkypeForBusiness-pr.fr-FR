---
title: 'Lync Server 2013 : vue d’ensemble de l’acheminement en fonction de l’emplacement pour les conférences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adb103d1f2314e033d9ef0958dd05a7648012bde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="01036-102">Vue d’ensemble de l’acheminement en fonction de l’emplacement pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01036-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01036-103">_**Dernière modification de la rubrique :** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="01036-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="01036-104">L’application de conférence de routage basée sur l’emplacement fournit aux conférences Lync un mécanisme de prévention du contournement du numéro RTC.</span><span class="sxs-lookup"><span data-stu-id="01036-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="01036-105">L’application surveille les conférences actives et applique les restrictions de routage basées sur l’emplacement en fonction de l’emplacement des utilisateurs de Lync qui participent.</span><span class="sxs-lookup"><span data-stu-id="01036-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="01036-106">L’application de conférence de routage basée sur l’emplacement détermine si le routage en fonction de l’emplacement doit être appliqué sur une réunion Lync si les critères suivants sont satisfaits :</span><span class="sxs-lookup"><span data-stu-id="01036-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="01036-107">L’organisateur de la réunion est activé pour le routage par emplacement.</span><span class="sxs-lookup"><span data-stu-id="01036-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="01036-108">Les restrictions de routage basées sur les emplacements ne s’appliquent qu’aux conférences organisées par des utilisateurs qui sont configurés pour le routage selon l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="01036-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="01036-109">Au moins un participant à la réunion est un point de terminaison PSTN.</span><span class="sxs-lookup"><span data-stu-id="01036-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="01036-110">Les restrictions de routage basées sur les emplacements ne s’appliquent qu’aux conférences qui incluent des points de terminaison PSTN.</span><span class="sxs-lookup"><span data-stu-id="01036-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="01036-111">Le site réseau sur lequel la passerelle PSTN utilisée pour relier la conférence au réseau téléphonique commuté est localisée, de même que les sites réseau depuis lesquels les organisateurs et les participants se connectent.</span><span class="sxs-lookup"><span data-stu-id="01036-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="01036-112">L’application de conférence de routage basée sur l’emplacement empêche la participation d’utilisateurs Lync et de points de terminaison RTC de différents sites réseau à la même conférence.</span><span class="sxs-lookup"><span data-stu-id="01036-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="01036-113">Si l’organisateur d’une réunion est activé pour le routage sur l’emplacement, l’application de conférence applique les restrictions suivantes :</span><span class="sxs-lookup"><span data-stu-id="01036-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="01036-114">Les points de terminaison qui peuvent participer à une réunion Lync varient en fonction des points de terminaison qui ont déjà rejoint la Conférence, et cette restriction s’ajuste en tant que points de terminaison joints et de nouveaux points de terminaison rejoindre la Conférence.</span><span class="sxs-lookup"><span data-stu-id="01036-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="01036-115">Si les organisateurs et les participants se connectent à une réunion Lync à partir du même site réseau, un point de terminaison PSTN, un autre participant du même site réseau, un autre participant d’un site réseau différent ou un participant d’un site réseau inconnu est autorisé à affiliation.</span><span class="sxs-lookup"><span data-stu-id="01036-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="01036-116">Si les organisateurs et les participants rejoignent la réunion à partir d’autres sites réseaux ou de sites réseau inconnus, un point de terminaison PSTN n’est pas autorisé à rejoindre la réunion si l’appel PSTN provient d’une jonction SIP pour laquelle le routage géodépendant est activé.</span><span class="sxs-lookup"><span data-stu-id="01036-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="01036-117">Si les organisateurs et les participants se connectent à la réunion à partir du même site réseau et qu’il y a des participants qui rejoignent la même réunion à partir du RTC, un point de terminaison Lync d’un site réseau différent n’est pas autorisé à rejoindre la réunion.</span><span class="sxs-lookup"><span data-stu-id="01036-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="01036-118">Ces restrictions de routage basées sur l’emplacement des conférences sont résumées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="01036-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01036-119">Utilisateur(s) dans une conférence à un moment donné</span><span class="sxs-lookup"><span data-stu-id="01036-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="01036-120">Utilisateur(s) autorisés à rejoindre la conférence</span><span class="sxs-lookup"><span data-stu-id="01036-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="01036-121">Utilisateur(s) non autorisés à rejoindre la conférence</span><span class="sxs-lookup"><span data-stu-id="01036-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01036-122">Utilisateurs du client VoIP Lync à partir d’un site réseau unique</span><span class="sxs-lookup"><span data-stu-id="01036-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="01036-123">Utilisateur du client VoIP Lync à partir du même site réseau</span><span class="sxs-lookup"><span data-stu-id="01036-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="01036-124">Utilisateur du client VoIP Lync sur un autre site réseau</span><span class="sxs-lookup"><span data-stu-id="01036-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="01036-125">Utilisateur du client VoIP Lync à partir d’un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="01036-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="01036-126">Utilisateur fédéré du client VoIP Lync</span><span class="sxs-lookup"><span data-stu-id="01036-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="01036-127">Utilisateur rejoignant la conférence à partir d’un point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="01036-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="01036-128">Aucune</span><span class="sxs-lookup"><span data-stu-id="01036-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01036-129">Utilisateur (s) client VoIP Lync à partir d’un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="01036-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="01036-130">Client VoIP Lync sur n’importe quel site</span><span class="sxs-lookup"><span data-stu-id="01036-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="01036-131">Utilisateur du client VoIP Lync d’un site inconnu</span><span class="sxs-lookup"><span data-stu-id="01036-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="01036-132">Utilisateur fédéré du client VoIP Lync</span><span class="sxs-lookup"><span data-stu-id="01036-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="01036-133">Utilisateur rejoignant la conférence via un point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="01036-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01036-134">Utilisateurs du client VoIP Lync provenant de différents sites réseau</span><span class="sxs-lookup"><span data-stu-id="01036-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="01036-135">Utilisateur du client VoIP Lync de n’importe quel site réseau</span><span class="sxs-lookup"><span data-stu-id="01036-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="01036-136">Utilisateur du client VoIP Lync à partir d’un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="01036-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="01036-137">Utilisateur fédéré du client VoIP Lync</span><span class="sxs-lookup"><span data-stu-id="01036-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="01036-138">Utilisateur rejoignant la conférence via un point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="01036-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01036-139">Utilisateurs du client VoIP Lync à partir d’un site réseau unique et utilisateurs qui se connectent à partir d’un point de terminaison RTC</span><span class="sxs-lookup"><span data-stu-id="01036-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="01036-140">Utilisateur du client VoIP Lync à partir du même site réseau</span><span class="sxs-lookup"><span data-stu-id="01036-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="01036-141">Utilisateur du client VoIP Lync sur un autre site réseau</span><span class="sxs-lookup"><span data-stu-id="01036-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="01036-142">Utilisateur du client VoIP Lync à partir d’un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="01036-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="01036-143">Utilisateur fédéré du client VoIP Lync</span><span class="sxs-lookup"><span data-stu-id="01036-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="01036-144">Vous trouverez ci-après des caractéristiques supplémentaires de l’application de conférence de routage basée sur l’emplacement :</span><span class="sxs-lookup"><span data-stu-id="01036-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="01036-145">Lorsqu’un utilisateur ne peut pas participer à une conférence en fonction de restrictions de routage basées sur l’emplacement, les utilisateurs qui participent à la Conférence seront rejetés et son client Lync signalera que l’appel n’a pas abouti ou a pris fin.</span><span class="sxs-lookup"><span data-stu-id="01036-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="01036-146">Un point de terminaison RTC rejoignant une conférence avec des mises en application de routage basées sur les emplacements ne sera pas limité à la Conférence, quel que soit son état, si le point de terminaison est joint par le biais d’un Trunk qui n’est pas activé pour le routage sur site.</span><span class="sxs-lookup"><span data-stu-id="01036-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="01036-147">Un système PBX connecté à un serveur de médiation par le biais d’un réseau SIP qui ne dépose aucun appel vers le RTC aura les mêmes conséquences que les utilisateurs de Lync situés sur le même site réseau où le Trunk SIP est défini.</span><span class="sxs-lookup"><span data-stu-id="01036-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="01036-148">Par exemple, un point de terminaison PSTN peut participer à une conférence avec un utilisateur PBX et un utilisateur Lync s’il se trouve sur le même site réseau. dans le cas contraire, le point de terminaison PSTN ne sera pas autorisé à rejoindre la Conférence si l’utilisateur PBX se trouve sur un autre site réseau que l’utilisateur Lync.</span><span class="sxs-lookup"><span data-stu-id="01036-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

