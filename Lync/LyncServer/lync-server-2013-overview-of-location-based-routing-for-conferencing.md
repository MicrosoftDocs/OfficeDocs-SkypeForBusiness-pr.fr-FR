---
title: 'Lync Server 2013 : vue d’ensemble du routage géodépendant pour les conférences'
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
ms.openlocfilehash: 28ca4ea233f783271c91490aa0550bc2344bdaad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="05cd0-102">Vue d’ensemble du routage géodépendant pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05cd0-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05cd0-103">_**Dernière modification de la rubrique :** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="05cd0-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="05cd0-104">L’application de conférence de routage basée sur l’emplacement fournit aux conférences Lync un mécanisme de prévention des appels téléphoniques PSTN.</span><span class="sxs-lookup"><span data-stu-id="05cd0-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="05cd0-105">L’application surveille les conférences actives et applique des restrictions de routage basées sur l’emplacement en fonction de l’emplacement des utilisateurs de Lync qui participent.</span><span class="sxs-lookup"><span data-stu-id="05cd0-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="05cd0-106">L’application de conférence de routage basée sur l’emplacement détermine si le routage géodépendant doit être appliqué à une réunion Lync si les critères suivants sont satisfaits :</span><span class="sxs-lookup"><span data-stu-id="05cd0-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="05cd0-107">L’organisateur de la réunion est activé pour le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="05cd0-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="05cd0-108">Les restrictions de routage basées sur l’emplacement seront appliquées uniquement aux conférences organisées par des utilisateurs activés pour le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="05cd0-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="05cd0-109">Au moins un participant à la réunion est un point de terminaison PSTN.</span><span class="sxs-lookup"><span data-stu-id="05cd0-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="05cd0-110">Les restrictions de routage basées sur l’emplacement sont applicables uniquement pour les conférences qui incluent des points de terminaison PSTN.</span><span class="sxs-lookup"><span data-stu-id="05cd0-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="05cd0-111">Le site réseau où se trouve la passerelle PSTN servant à relier la Conférence au RTC est disponible, ainsi que les sites réseau à partir desquels les organisateurs et les participants se connectent.</span><span class="sxs-lookup"><span data-stu-id="05cd0-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="05cd0-112">L’application de conférence de routage basée sur l’emplacement empêche la participation des utilisateurs Lync et des points de terminaison RTC de différents sites réseau à la même conférence.</span><span class="sxs-lookup"><span data-stu-id="05cd0-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="05cd0-113">Si l’organisateur d’une réunion est activé pour le routage géodépendant, l’application de conférence applique les restrictions suivantes :</span><span class="sxs-lookup"><span data-stu-id="05cd0-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="05cd0-114">Les points de terminaison pouvant rejoindre une réunion Lync dépendent des points de terminaison qui ont déjà rejoint la Conférence, et cette restriction s’ajuste en tant que points de terminaison joints et de nouveaux points de terminaison joignent la Conférence.</span><span class="sxs-lookup"><span data-stu-id="05cd0-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="05cd0-115">Si les organisateurs et les participants rejoignent une réunion Lync à partir du même site réseau, un point de terminaison PSTN, un autre participant du même site réseau, un autre participant d’un site réseau différent ou un participant d’un site réseau inconnu sont autorisés à reli.</span><span class="sxs-lookup"><span data-stu-id="05cd0-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="05cd0-116">Si les organisateurs et les participants rejoignent la réunion à partir de sites réseau différents ou inconnus, un point de terminaison PSTN n’est pas autorisé à participer à la réunion si l’appel RTC pénètre à partir d’une jonction SIP activée pour le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="05cd0-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="05cd0-117">Si les organisateurs et les participants rejoignent la réunion à partir du même site réseau et que des participants rejoignent la même réunion à partir du RTC, un point de terminaison Lync provenant d’un site réseau différent n’est pas autorisé à rejoindre la réunion.</span><span class="sxs-lookup"><span data-stu-id="05cd0-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="05cd0-118">Ces restrictions de routage basées sur l’emplacement des conférences sont résumées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="05cd0-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05cd0-119">Utilisateur (s) dans une conférence à tout moment</span><span class="sxs-lookup"><span data-stu-id="05cd0-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="05cd0-120">Utilisateur (s) autorisé à rejoindre la Conférence</span><span class="sxs-lookup"><span data-stu-id="05cd0-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="05cd0-121">Utilisateur (s) non autorisé à rejoindre la Conférence</span><span class="sxs-lookup"><span data-stu-id="05cd0-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05cd0-122">Utilisateur (s) de client VoIP Lync à partir d’un site réseau unique</span><span class="sxs-lookup"><span data-stu-id="05cd0-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="05cd0-123">Utilisateur de client VoIP Lync à partir du même site réseau</span><span class="sxs-lookup"><span data-stu-id="05cd0-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="05cd0-124">Utilisateur de client VoIP Lync à partir d’un autre site réseau</span><span class="sxs-lookup"><span data-stu-id="05cd0-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="05cd0-125">Utilisateur de client VoIP Lync à partir d’un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="05cd0-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="05cd0-126">Utilisateur client VoIP fédéré de Lync</span><span class="sxs-lookup"><span data-stu-id="05cd0-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="05cd0-127">Appartenance d’un utilisateur à partir d’un point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="05cd0-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="05cd0-128">Aucun</span><span class="sxs-lookup"><span data-stu-id="05cd0-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05cd0-129">Utilisateur (s) de client VoIP Lync à partir d’un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="05cd0-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="05cd0-130">Utilisateur de client VoIP Lync à partir de n’importe quel site</span><span class="sxs-lookup"><span data-stu-id="05cd0-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="05cd0-131">Utilisateur de client VoIP Lync à partir d’un site inconnu</span><span class="sxs-lookup"><span data-stu-id="05cd0-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="05cd0-132">Utilisateur client VoIP fédéré de Lync</span><span class="sxs-lookup"><span data-stu-id="05cd0-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="05cd0-133">Appartenance d’un utilisateur via un point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="05cd0-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05cd0-134">Utilisateurs de clients VoIP Lync provenant de sites réseau différents</span><span class="sxs-lookup"><span data-stu-id="05cd0-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="05cd0-135">Utilisateur de client VoIP Lync à partir de n’importe quel site réseau</span><span class="sxs-lookup"><span data-stu-id="05cd0-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="05cd0-136">Utilisateur de client VoIP Lync à partir d’un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="05cd0-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="05cd0-137">Utilisateur client VoIP fédéré de Lync</span><span class="sxs-lookup"><span data-stu-id="05cd0-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="05cd0-138">Appartenance d’un utilisateur via un point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="05cd0-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05cd0-139">Utilisateurs de clients VoIP Lync à partir d’un site réseau unique et utilisateurs qui rejoignent un point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="05cd0-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="05cd0-140">Utilisateur de client VoIP Lync à partir du même site réseau</span><span class="sxs-lookup"><span data-stu-id="05cd0-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="05cd0-141">Utilisateur de client VoIP Lync à partir d’un autre site réseau</span><span class="sxs-lookup"><span data-stu-id="05cd0-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="05cd0-142">Utilisateur de client VoIP Lync à partir d’un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="05cd0-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="05cd0-143">Utilisateur client VoIP fédéré de Lync</span><span class="sxs-lookup"><span data-stu-id="05cd0-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="05cd0-144">Les caractéristiques supplémentaires de l’application de conférence de routage basée sur l’emplacement sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="05cd0-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="05cd0-145">Lorsqu’un utilisateur n’est pas autorisé à participer à une conférence des restrictions de routage basées sur l’emplacement, les utilisateurs qui appellent la Conférence sont rejetés et son client Lync signale que l’appel n’a pas abouti ou s’est terminé.</span><span class="sxs-lookup"><span data-stu-id="05cd0-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="05cd0-146">Un point de terminaison PSTN joignant une conférence avec des mises en œuvre de routage géodépendant n’est pas limité à rejoindre la Conférence indépendamment de son état si le point de terminaison se joint via une jonction qui n’est pas activée pour le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="05cd0-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="05cd0-147">Un système PBX connecté à un serveur de médiation par le biais d’une jonction SIP qui ne sort pas les appels vers le RTC aura les mêmes mises en œuvre que les utilisateurs Lync situés dans le même site réseau où la jonction SIP est définie.</span><span class="sxs-lookup"><span data-stu-id="05cd0-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="05cd0-148">Par exemple, un point de terminaison PSTN pourra rejoindre une conférence avec un utilisateur PBX et un utilisateur Lync s’il se trouve dans le même site réseau ; dans le cas contraire, le point de terminaison PSTN ne sera pas autorisé à rejoindre la Conférence si l’utilisateur PBX se trouve dans un autre site réseau que l’utilisateur Lync.</span><span class="sxs-lookup"><span data-stu-id="05cd0-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

