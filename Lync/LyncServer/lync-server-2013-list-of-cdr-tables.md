---
title: 'Lync Server 2013 : liste des tables des enregistrements des détails des appels'
description: 'Lync Server 2013 : liste des tables des enregistrements des détails des appels.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21d0f683ffeb0f5f1cbba5db4c45d248aa14e8e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558700"
---
# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="2c54d-103">Liste des tables des enregistrements des détails des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c54d-103">List of CDR tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c54d-104">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="2c54d-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="2c54d-105">Le schéma de base de données de l’enregistrement des détails des appels comprend les tables suivantes.</span><span class="sxs-lookup"><span data-stu-id="2c54d-105">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="2c54d-106">Tables statiques</span><span class="sxs-lookup"><span data-stu-id="2c54d-106">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c54d-107">Table</span><span class="sxs-lookup"><span data-stu-id="2c54d-107">Table</span></span></th>
<th><span data-ttu-id="2c54d-108">Description</span><span class="sxs-lookup"><span data-stu-id="2c54d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-109"><a href="lync-server-2013-callpriorities-table.md">Table table callpriorities dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-109"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-110">Stocke la liste des priorités d’appel possibles, telles que les appels très urgents, urgents, normaux, non urgents, etc.</span><span class="sxs-lookup"><span data-stu-id="2c54d-110">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">Table ConferenceJoinTimeThresholds dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-112">Stocke les limites de classification utilisées par le rapport du temps de connexion à la conférence.</span><span class="sxs-lookup"><span data-stu-id="2c54d-112">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-113"><a href="lync-server-2013-deregistertype-table.md">Table DeRegisterType dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-113"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-114">Stocke la liste des raisons possibles de l’annulation de l’inscription d’un utilisateur, telles que &quot; initiée par le client, &quot; &quot; l’expiration de l’inscription, le &quot; &quot; blocage du client &quot; et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="2c54d-114">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-115"><a href="lync-server-2013-medialist-table.md">Table médial dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-115"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-116">Stocke la liste des types de médias qui peuvent générer des entrées dans la base de données (par exemple, la messagerie instantanée, l’audio, la vidéo et le transfert de fichiers).</span><span class="sxs-lookup"><span data-stu-id="2c54d-116">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-117"><a href="lync-server-2013-purgesettings-table.md">Table PurgeSettings dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-117"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-118">Stocke les informations qui indiquent si (et quand) les enregistrements des détails des appels obsolètes seront automatiquement supprimés de la base de données d’enregistrement des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="2c54d-118">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-119"><a href="lync-server-2013-roles-table.md">Table Roles dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-119"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-120">Stocke la liste possible des rôles de conférence (par exemple, participant et présentateur).</span><span class="sxs-lookup"><span data-stu-id="2c54d-120">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-121"><a href="lync-server-2013-sipresponsemetadata-table.md">Table SIPResponseMetaData dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-121"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-122">Stocke une liste des codes de réponse SIP ainsi que la classification et la définition de chacun de ces codes.</span><span class="sxs-lookup"><span data-stu-id="2c54d-122">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="2c54d-123">Tables de prise en charge</span><span class="sxs-lookup"><span data-stu-id="2c54d-123">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c54d-124">Table</span><span class="sxs-lookup"><span data-stu-id="2c54d-124">Table</span></span></th>
<th><span data-ttu-id="2c54d-125">Description</span><span class="sxs-lookup"><span data-stu-id="2c54d-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-126"><a href="lync-server-2013-clientversions-table.md">Table ClientVersions dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-126"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-127">Stocke les clients (à la fois le type de client et le numéro de version) de chaque client impliqué dans un appel comprenant des informations capturées dans cette base de données.</span><span class="sxs-lookup"><span data-stu-id="2c54d-127">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-128"><a href="lync-server-2013-conferenceuris-table.md">Table ConferenceUris dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-128"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-129">Stocke une liste de ConferenceURI qui sont utilisés dans les appels relatifs à la conférence.</span><span class="sxs-lookup"><span data-stu-id="2c54d-129">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-130"><a href="lync-server-2013-contenttypes-table.md">Table ContentTypes dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-130"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-131">Stocke une liste de types de contenus SIP (Session Initiation Protocol) qui sont utilisés à la fois dans les appels d’égal à égal et les appels de conférence.</span><span class="sxs-lookup"><span data-stu-id="2c54d-131">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-132"><a href="lync-server-2013-devices-table.md">Table Devices dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-132"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-133">Stocke une liste d’appareils, notamment leur fabricant, la version du matériel et l’adresse MAC.</span><span class="sxs-lookup"><span data-stu-id="2c54d-133">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-134"><a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-134"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-135">Stocke des informations sur les ID de dialogue pour chaque session dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2c54d-135">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-136"><a href="lync-server-2013-edgeservers-table.md">Table table edgeservers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-136"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-137">Stocke une liste de serveurs Edge qui sont utilisés pour les appels externes.</span><span class="sxs-lookup"><span data-stu-id="2c54d-137">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-138"><a href="lync-server-2013-gateways-table.md">Tableau des passerelles dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-138"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-139">Stocke une liste de passerelles qui sont utilisées pour les appels VoIP (Voice over Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="2c54d-139">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-140"><a href="lync-server-2013-hardwareversions-table.md">Table table hardwareversions dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-140"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-141">Stocke une liste de versions matérielles d’appareils (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="2c54d-141">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-142"><a href="lync-server-2013-manufacturers-table.md">Table Manufacturers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-142"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-143">Stocke une liste de fabricants et d’appareils (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="2c54d-143">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-144"><a href="lync-server-2013-mcus-table.md">Table MCU dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-144"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-145">Stocke des informations sur les différents serveurs de conférence A/V et leurs URI.</span><span class="sxs-lookup"><span data-stu-id="2c54d-145">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-146"><a href="lync-server-2013-mediationservers-table.md">Table table mediationservers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-146"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-147">Stocke une liste de serveurs de médiation qui sont utilisés pour les appels VoIP.</span><span class="sxs-lookup"><span data-stu-id="2c54d-147">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-148"><a href="lync-server-2013-phones-table.md">Table téléphones dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-148"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-149">Stocke tous les numéros de téléphone utilisés dans les appels VoIP qui ont été archivés ou dont les détails des appels ont été enregistrés.</span><span class="sxs-lookup"><span data-stu-id="2c54d-149">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-150"><a href="lync-server-2013-pools-table.md">Table pools dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-150"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-151">Stocke les noms du pool sur lequel les messages instantanés ont été capturés.</span><span class="sxs-lookup"><span data-stu-id="2c54d-151">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-152"><a href="lync-server-2013-servers-table.md">Table Servers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-152"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-153">Stocke le nom des serveurs impliqués dans les appels.</span><span class="sxs-lookup"><span data-stu-id="2c54d-153">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-154"><a href="lync-server-2013-tenants-table.md">Table locataires dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-154"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-155">Stocke les clients pris en charge par le déploiement en cours.</span><span class="sxs-lookup"><span data-stu-id="2c54d-155">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="2c54d-156">Il existe des clients intégrés pour les utilisateurs d’entreprise, les utilisateurs fédérés, les utilisateurs de connectivité de messagerie instantanée publique et les utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="2c54d-156">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-157"><a href="lync-server-2013-useragentdef-table.md">Table table useragentdef dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-157"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-158">Mappe les identificateurs d’agents utilisateurs aux noms descriptifs des agents.</span><span class="sxs-lookup"><span data-stu-id="2c54d-158">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-159"><a href="lync-server-2013-users-table.md">Table users dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-159"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-160">Stocke les URI des utilisateurs qui ont participé à des sessions enregistrées ou archivées dans cette base de données.</span><span class="sxs-lookup"><span data-stu-id="2c54d-160">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-161"><a href="lync-server-2013-userstatistics-table.md">Table UserStatistics dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-161"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-162">Stocke les informations sur l’utilisation du système pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2c54d-162">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="2c54d-163">Tables spécifiques aux enregistrements des détails des appels de conférence</span><span class="sxs-lookup"><span data-stu-id="2c54d-163">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c54d-164">Table</span><span class="sxs-lookup"><span data-stu-id="2c54d-164">Table</span></span></th>
<th><span data-ttu-id="2c54d-165">Description</span><span class="sxs-lookup"><span data-stu-id="2c54d-165">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-166"><a href="lync-server-2013-conferences-table.md">Tableau conférences dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-166"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-167">Stocke des informations sur toutes les conférences qui ont été archivées ou dont les détails ont été enregistrés, notamment le ConferenceURI, et l’heure de début et de fin.</span><span class="sxs-lookup"><span data-stu-id="2c54d-167">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-168"><a href="lync-server-2013-conferencesessiondetails-table.md">Table ConferenceSessionDetails dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-168"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-169">Stocke des informations sur chaque session de conférence fondée sur le protocole SIP, notamment l’heure de début et de fin, l’ID utilisateur, le code de réponse et l’ID de diagnostic pour chaque session.</span><span class="sxs-lookup"><span data-stu-id="2c54d-169">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">Table FocusJoinsAndLeaves dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-171">Stocke des informations sur les événements d’arrivée et de départ d’un utilisateur dans la conférence, notamment le rôle des utilisateurs et la version du client.</span><span class="sxs-lookup"><span data-stu-id="2c54d-171">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">Table McuJoinsAndLeaves dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-173">Stocke des informations sur les serveurs de conférence A/V qui sont impliqués dans une conférence et les heures de départ et d’arrivée de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2c54d-173">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="2c54d-174">Tables des messages dans les conférences de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="2c54d-174">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c54d-175">Table</span><span class="sxs-lookup"><span data-stu-id="2c54d-175">Table</span></span></th>
<th><span data-ttu-id="2c54d-176">Description</span><span class="sxs-lookup"><span data-stu-id="2c54d-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-177"><a href="lync-server-2013-conferencemessagecount-table.md">Table ConferenceMessageCount dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-177"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-178">Pour chaque conférence de messagerie instantanée, stocke le nombre de messages qui ont été envoyés par chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2c54d-178">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-179"><a href="lync-server-2013-imreportsummary-table.md">Table IMReportSummary dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-179"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-180">Fournit un rapport global sur les sessions de messagerie instantanée ouvertes dans une organisation.</span><span class="sxs-lookup"><span data-stu-id="2c54d-180">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="2c54d-181">Tables des sessions d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="2c54d-181">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c54d-182">Table</span><span class="sxs-lookup"><span data-stu-id="2c54d-182">Table</span></span></th>
<th><span data-ttu-id="2c54d-183">Description</span><span class="sxs-lookup"><span data-stu-id="2c54d-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-184"><a href="lync-server-2013-sessiondetails-table.md">Table SessionDetails dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-184"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-185">Stocke des informations sur chaque session d’égal à égal, notamment l’heure de début et de fin, l’ID utilisateur, le code de réponse et le nombre de messages pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2c54d-185">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-186"><a href="lync-server-2013-filetransfers-table.md">Table FileTransfers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-186"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-187">Stocke des informations sur les sessions de transfert de fichiers, notamment le nom de fichier et le résultat (accepté, rejeté ou annulé).</span><span class="sxs-lookup"><span data-stu-id="2c54d-187">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-188"><a href="lync-server-2013-media-table.md">Table Media dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-188"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-189">Stocke des informations sur les différents types de médias impliqués dans les sessions d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="2c54d-189">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="2c54d-190">Table des détails des appels VoIP</span><span class="sxs-lookup"><span data-stu-id="2c54d-190">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c54d-191">Table</span><span class="sxs-lookup"><span data-stu-id="2c54d-191">Table</span></span></th>
<th><span data-ttu-id="2c54d-192">Description</span><span class="sxs-lookup"><span data-stu-id="2c54d-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-193"><a href="lync-server-2013-voipdetails-table.md">Table VoipDetails dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-193"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-194">Pour chaque appel VoIP/PSTN à deux utilisateurs, stocke des informations sur l’appel, telles que l’ID téléphonique du téléphone VoIP, la passerelle utilisée, et quel participant a été déconnecté.</span><span class="sxs-lookup"><span data-stu-id="2c54d-194">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="2c54d-195">Fait référence à la <a href="lync-server-2013-sessiondetails-table.md">table SessionDetails dans Lync Server 2013</a> pour les heures de début et de fin de l’appel et le code de réponse.</span><span class="sxs-lookup"><span data-stu-id="2c54d-195">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="2c54d-196">Si l’un des participants à l’appel est un utilisateur VoIP ou si un serveur de médiation a été impliqué dans cet appel, un enregistrement sera créé dans cette table.</span><span class="sxs-lookup"><span data-stu-id="2c54d-196">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="2c54d-197">Les informations sur les appels VoIP/VoIP qui n’impliquent pas de téléphone PSTN (réseau téléphonique commuté) sont capturées dans la <A href="lync-server-2013-sessiondetails-table.md">table SessionDetails dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2c54d-197">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="2c54d-198">Table pour l’audit d’appel E9-1-1</span><span class="sxs-lookup"><span data-stu-id="2c54d-198">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c54d-199">Table</span><span class="sxs-lookup"><span data-stu-id="2c54d-199">Table</span></span></th>
<th><span data-ttu-id="2c54d-200">Description</span><span class="sxs-lookup"><span data-stu-id="2c54d-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-201"><a href="lync-server-2013-locations-table.md">Table locations dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-201"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-202">Pour chaque appel très urgents, tel que l’appel Enhanced 9-1-1 (E9-1-1), stocke les informations d’emplacement concernant l’appel.</span><span class="sxs-lookup"><span data-stu-id="2c54d-202">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="2c54d-203">Fait référence à la <a href="lync-server-2013-sessiondetails-table.md">table SessionDetails dans Lync Server 2013</a> pour les heures de début et de fin de l’appel et le code de réponse.</span><span class="sxs-lookup"><span data-stu-id="2c54d-203">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="2c54d-p105">Cette table ne contient que le blob d’emplacement pour l’appel E9-1-1. Fait référence à la table SessionDetails pour d’autres informations détaillées concernant l’appel.</span><span class="sxs-lookup"><span data-stu-id="2c54d-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="2c54d-206">Tables de dépannage</span><span class="sxs-lookup"><span data-stu-id="2c54d-206">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c54d-207">Table</span><span class="sxs-lookup"><span data-stu-id="2c54d-207">Table</span></span></th>
<th><span data-ttu-id="2c54d-208">Description</span><span class="sxs-lookup"><span data-stu-id="2c54d-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-209"><a href="lync-server-2013-application-table.md">Table application dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-209"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-210">Stocke des informations sur les différents processus de Lync Server 2013 impliqués dans le routage et les connexions.</span><span class="sxs-lookup"><span data-stu-id="2c54d-210">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-211"><a href="lync-server-2013-calltype-table.md">Table CallType dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-211"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-212">Stocke des informations sur les types d’appel, tels que « audio », « messagerie instantanée », « audio et vidéo » et « partage d’application ».</span><span class="sxs-lookup"><span data-stu-id="2c54d-212">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-213"><a href="lync-server-2013-errorcategory-table.md">Table ErrorCategory dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-213"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-214">Stocke le nom convivial de chaque classification de diagnostic Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2c54d-214">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-215"><a href="lync-server-2013-errordef-table.md">Table table errordef dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-215"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-216">Stocke des informations sur les types d’erreurs et leurs définitions.</span><span class="sxs-lookup"><span data-stu-id="2c54d-216">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-217"><a href="lync-server-2013-errorreport-table.md">Table ErrorReport dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-217"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-218">Stocke des informations sur les erreurs qui se sont produites.</span><span class="sxs-lookup"><span data-stu-id="2c54d-218">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-219"><a href="lync-server-2013-progressreport-table.md">Table ProgressReport dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2c54d-219"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2c54d-220">Stocke des informations sur les rapports d’avancement des différentes étapes impliquées dans les processus Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2c54d-220">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2c54d-221">Les tableaux de la liste suivante sont utilisés en interne par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2c54d-221">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="2c54d-222">Elles ne sont pas détaillées dans ce document.</span><span class="sxs-lookup"><span data-stu-id="2c54d-222">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="2c54d-223">Tables destinées à une utilisation interne par Lync Server</span><span class="sxs-lookup"><span data-stu-id="2c54d-223">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c54d-224">Table</span><span class="sxs-lookup"><span data-stu-id="2c54d-224">Table</span></span></th>
<th><span data-ttu-id="2c54d-225">Description</span><span class="sxs-lookup"><span data-stu-id="2c54d-225">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-226"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-226"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-227">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-227">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-228"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-228"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-229">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-229">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-230"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-230"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-231">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-231">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-232"><strong>Table FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-232"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-233">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-233">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-234"><strong>Table MSMQProcessing</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-234"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-235">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-235">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-236"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-236"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-237">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-237">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-238"><strong>Table Syndicators</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-238"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-239">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-239">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-240"><strong>Table SyndicatorsTenantMap</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-240"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-241">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-241">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-242"><strong>Table Task</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-242"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-243">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-243">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-244"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-244"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-245">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-245">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-246"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-246"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-247">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-247">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-248"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-248"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-249">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-249">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-250"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-250"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-251">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-251">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-252"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-252"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-253">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-253">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-254"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-254"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-255">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-255">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-256"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-256"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-257">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-257">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-258"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-258"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-259">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-259">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c54d-260"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-260"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-261">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-261">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c54d-262"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="2c54d-262"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="2c54d-263">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2c54d-263">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

