---
title: 'Lync Server 2013 : liste des tables des enregistrements des détails des appels'
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
ms.openlocfilehash: 6f7f6fed1fad8cf706b86ef0cb141ab04fb39382
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="a3a5d-102">Liste des tables des enregistrements des détails des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3a5d-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3a5d-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="a3a5d-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="a3a5d-104">Le schéma de base de données de l’enregistrement des détails des appels comprend les tables suivantes.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="a3a5d-105">Tables statiques</span><span class="sxs-lookup"><span data-stu-id="a3a5d-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3a5d-106">Table</span><span class="sxs-lookup"><span data-stu-id="a3a5d-106">Table</span></span></th>
<th><span data-ttu-id="a3a5d-107">Description</span><span class="sxs-lookup"><span data-stu-id="a3a5d-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-108"><a href="lync-server-2013-callpriorities-table.md">Table table callpriorities dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-109">Stocke la liste des priorités d’appel possibles, telles que les appels très urgents, urgents, normaux, non urgents, etc.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Table ConferenceJoinTimeThresholds dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-111">Stocke les limites de classification utilisées par le rapport du temps de connexion à la conférence.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-112"><a href="lync-server-2013-deregistertype-table.md">Table DeRegisterType dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-113">Stocke la liste des raisons possibles de l’annulation de l’inscription &quot;d’un utilisateur&quot; &quot;, telles que&quot; &quot;initiée par&quot; le client, l’expiration de l’inscription, le blocage du client et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-114"><a href="lync-server-2013-medialist-table.md">Table médial dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-115">Stocke la liste des types de médias qui peuvent générer des entrées dans la base de données (par exemple, la messagerie instantanée, l’audio, la vidéo et le transfert de fichiers).</span><span class="sxs-lookup"><span data-stu-id="a3a5d-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-116"><a href="lync-server-2013-purgesettings-table.md">Table PurgeSettings dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-117">Stocke les informations qui indiquent si (et quand) les enregistrements des détails des appels obsolètes seront automatiquement supprimés de la base de données d’enregistrement des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-118"><a href="lync-server-2013-roles-table.md">Table Roles dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-119">Stocke la liste possible des rôles de conférence (par exemple, participant et présentateur).</span><span class="sxs-lookup"><span data-stu-id="a3a5d-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Table SIPResponseMetaData dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-121">Stocke une liste des codes de réponse SIP ainsi que la classification et la définition de chacun de ces codes.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="a3a5d-122">Tables de prise en charge</span><span class="sxs-lookup"><span data-stu-id="a3a5d-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3a5d-123">Table</span><span class="sxs-lookup"><span data-stu-id="a3a5d-123">Table</span></span></th>
<th><span data-ttu-id="a3a5d-124">Description</span><span class="sxs-lookup"><span data-stu-id="a3a5d-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-125"><a href="lync-server-2013-clientversions-table.md">Table ClientVersions dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-126">Stocke les clients (à la fois le type de client et le numéro de version) de chaque client impliqué dans un appel comprenant des informations capturées dans cette base de données.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-127"><a href="lync-server-2013-conferenceuris-table.md">Table ConferenceUris dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-128">Stocke une liste de ConferenceURI qui sont utilisés dans les appels relatifs à la conférence.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-129"><a href="lync-server-2013-contenttypes-table.md">Table ContentTypes dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-130">Stocke une liste de types de contenus SIP (Session Initiation Protocol) qui sont utilisés à la fois dans les appels d’égal à égal et les appels de conférence.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-131"><a href="lync-server-2013-devices-table.md">Table Devices dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-132">Stocke une liste d’appareils, notamment leur fabricant, la version du matériel et l’adresse MAC.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-133"><a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-134">Stocke des informations sur les ID de dialogue pour chaque session dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-135"><a href="lync-server-2013-edgeservers-table.md">Table table edgeservers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-136">Stocke une liste de serveurs Edge qui sont utilisés pour les appels externes.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-137"><a href="lync-server-2013-gateways-table.md">Tableau des passerelles dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-138">Stocke une liste de passerelles qui sont utilisées pour les appels VoIP (Voice over Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="a3a5d-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-139"><a href="lync-server-2013-hardwareversions-table.md">Table table hardwareversions dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-140">Stocke une liste de versions matérielles d’appareils (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="a3a5d-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-141"><a href="lync-server-2013-manufacturers-table.md">Table Manufacturers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-142">Stocke une liste de fabricants et d’appareils (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="a3a5d-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-143"><a href="lync-server-2013-mcus-table.md">Table MCU dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-144">Stocke des informations sur les différents serveurs de conférence A/V et leurs URI.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-145"><a href="lync-server-2013-mediationservers-table.md">Table table mediationservers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-146">Stocke une liste de serveurs de médiation qui sont utilisés pour les appels VoIP.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-147"><a href="lync-server-2013-phones-table.md">Table téléphones dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-148">Stocke tous les numéros de téléphone utilisés dans les appels VoIP qui ont été archivés ou dont les détails des appels ont été enregistrés.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-149"><a href="lync-server-2013-pools-table.md">Table pools dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-150">Stocke les noms du pool sur lequel les messages instantanés ont été capturés.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-151"><a href="lync-server-2013-servers-table.md">Table Servers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-152">Stocke le nom des serveurs impliqués dans les appels.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-153"><a href="lync-server-2013-tenants-table.md">Table locataires dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-154">Stocke les clients pris en charge par le déploiement en cours.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="a3a5d-155">Il existe des clients intégrés pour les utilisateurs d’entreprise, les utilisateurs fédérés, les utilisateurs de connectivité de messagerie instantanée publique et les utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-156"><a href="lync-server-2013-useragentdef-table.md">Table table useragentdef dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-157">Mappe les identificateurs d’agents utilisateurs aux noms descriptifs des agents.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-158"><a href="lync-server-2013-users-table.md">Table users dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-159">Stocke les URI des utilisateurs qui ont participé à des sessions enregistrées ou archivées dans cette base de données.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-160"><a href="lync-server-2013-userstatistics-table.md">Table UserStatistics dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-161">Stocke les informations sur l’utilisation du système pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="a3a5d-162">Tables spécifiques aux enregistrements des détails des appels de conférence</span><span class="sxs-lookup"><span data-stu-id="a3a5d-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3a5d-163">Table</span><span class="sxs-lookup"><span data-stu-id="a3a5d-163">Table</span></span></th>
<th><span data-ttu-id="a3a5d-164">Description</span><span class="sxs-lookup"><span data-stu-id="a3a5d-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-165"><a href="lync-server-2013-conferences-table.md">Tableau conférences dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-166">Stocke des informations sur toutes les conférences qui ont été archivées ou dont les détails ont été enregistrés, notamment le ConferenceURI, et l’heure de début et de fin.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Table ConferenceSessionDetails dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-168">Stocke des informations sur chaque session de conférence fondée sur le protocole SIP, notamment l’heure de début et de fin, l’ID utilisateur, le code de réponse et l’ID de diagnostic pour chaque session.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Table FocusJoinsAndLeaves dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-170">Stocke des informations sur les événements d’arrivée et de départ d’un utilisateur dans la conférence, notamment le rôle des utilisateurs et la version du client.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Table McuJoinsAndLeaves dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-172">Stocke des informations sur les serveurs de conférence A/V qui sont impliqués dans une conférence et les heures de départ et d’arrivée de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="a3a5d-173">Tables des messages dans les conférences de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="a3a5d-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3a5d-174">Table</span><span class="sxs-lookup"><span data-stu-id="a3a5d-174">Table</span></span></th>
<th><span data-ttu-id="a3a5d-175">Description</span><span class="sxs-lookup"><span data-stu-id="a3a5d-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-176"><a href="lync-server-2013-conferencemessagecount-table.md">Table ConferenceMessageCount dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-177">Pour chaque conférence de messagerie instantanée, stocke le nombre de messages qui ont été envoyés par chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-178"><a href="lync-server-2013-imreportsummary-table.md">Table IMReportSummary dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-179">Fournit un rapport global sur les sessions de messagerie instantanée ouvertes dans une organisation.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="a3a5d-180">Tables des sessions d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="a3a5d-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3a5d-181">Table</span><span class="sxs-lookup"><span data-stu-id="a3a5d-181">Table</span></span></th>
<th><span data-ttu-id="a3a5d-182">Description</span><span class="sxs-lookup"><span data-stu-id="a3a5d-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-183"><a href="lync-server-2013-sessiondetails-table.md">Table SessionDetails dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-184">Stocke des informations sur chaque session d’égal à égal, notamment l’heure de début et de fin, l’ID utilisateur, le code de réponse et le nombre de messages pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-185"><a href="lync-server-2013-filetransfers-table.md">Table FileTransfers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-186">Stocke des informations sur les sessions de transfert de fichiers, notamment le nom de fichier et le résultat (accepté, rejeté ou annulé).</span><span class="sxs-lookup"><span data-stu-id="a3a5d-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-187"><a href="lync-server-2013-media-table.md">Table Media dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-188">Stocke des informations sur les différents types de médias impliqués dans les sessions d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="a3a5d-189">Table des détails des appels VoIP</span><span class="sxs-lookup"><span data-stu-id="a3a5d-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3a5d-190">Table</span><span class="sxs-lookup"><span data-stu-id="a3a5d-190">Table</span></span></th>
<th><span data-ttu-id="a3a5d-191">Description</span><span class="sxs-lookup"><span data-stu-id="a3a5d-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-192"><a href="lync-server-2013-voipdetails-table.md">Table VoipDetails dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-193">Pour chaque appel VoIP/PSTN à deux utilisateurs, stocke des informations sur l’appel, telles que l’ID téléphonique du téléphone VoIP, la passerelle utilisée, et quel participant a été déconnecté.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="a3a5d-194">Fait référence à la <a href="lync-server-2013-sessiondetails-table.md">table SessionDetails dans Lync Server 2013</a> pour les heures de début et de fin de l’appel et le code de réponse.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a3a5d-195">Si l’un des participants à l’appel est un utilisateur VoIP ou si un serveur de médiation a été impliqué dans cet appel, un enregistrement sera créé dans cette table.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="a3a5d-196">Les informations sur les appels VoIP/VoIP qui n’impliquent pas de téléphone PSTN (réseau téléphonique commuté) sont capturées dans la <A href="lync-server-2013-sessiondetails-table.md">table SessionDetails dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="a3a5d-197">Table pour l’audit d’appel E9-1-1</span><span class="sxs-lookup"><span data-stu-id="a3a5d-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3a5d-198">Table</span><span class="sxs-lookup"><span data-stu-id="a3a5d-198">Table</span></span></th>
<th><span data-ttu-id="a3a5d-199">Description</span><span class="sxs-lookup"><span data-stu-id="a3a5d-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-200"><a href="lync-server-2013-locations-table.md">Table locations dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-201">Pour chaque appel très urgents, tel que l’appel Enhanced 9-1-1 (E9-1-1), stocke les informations d’emplacement concernant l’appel.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="a3a5d-202">Fait référence à la <a href="lync-server-2013-sessiondetails-table.md">table SessionDetails dans Lync Server 2013</a> pour les heures de début et de fin de l’appel et le code de réponse.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a3a5d-p105">Cette table ne contient que le blob d’emplacement pour l’appel E9-1-1. Fait référence à la table SessionDetails pour d’autres informations détaillées concernant l’appel.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="a3a5d-205">Tables de dépannage</span><span class="sxs-lookup"><span data-stu-id="a3a5d-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3a5d-206">Table</span><span class="sxs-lookup"><span data-stu-id="a3a5d-206">Table</span></span></th>
<th><span data-ttu-id="a3a5d-207">Description</span><span class="sxs-lookup"><span data-stu-id="a3a5d-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-208"><a href="lync-server-2013-application-table.md">Table application dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-209">Stocke des informations sur les différents processus de Lync Server 2013 impliqués dans le routage et les connexions.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-210"><a href="lync-server-2013-calltype-table.md">Table CallType dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-211">Stocke des informations sur les types d’appel, tels que « audio », « messagerie instantanée », « audio et vidéo » et « partage d’application ».</span><span class="sxs-lookup"><span data-stu-id="a3a5d-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-212"><a href="lync-server-2013-errorcategory-table.md">Table ErrorCategory dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-213">Stocke le nom convivial de chaque classification de diagnostic Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-214"><a href="lync-server-2013-errordef-table.md">Table table errordef dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-215">Stocke des informations sur les types d’erreurs et leurs définitions.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-216"><a href="lync-server-2013-errorreport-table.md">Table ErrorReport dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-217">Stocke des informations sur les erreurs qui se sont produites.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-218"><a href="lync-server-2013-progressreport-table.md">Table ProgressReport dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3a5d-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-219">Stocke des informations sur les rapports d’avancement des différentes étapes impliquées dans les processus Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a3a5d-220">Les tableaux de la liste suivante sont utilisés en interne par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="a3a5d-221">Elles ne sont pas détaillées dans ce document.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="a3a5d-222">Tables destinées à une utilisation interne par Lync Server</span><span class="sxs-lookup"><span data-stu-id="a3a5d-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3a5d-223">Table</span><span class="sxs-lookup"><span data-stu-id="a3a5d-223">Table</span></span></th>
<th><span data-ttu-id="a3a5d-224">Description</span><span class="sxs-lookup"><span data-stu-id="a3a5d-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-225"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-226">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-227"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-228">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-229"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-230">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-231"><strong>Table FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-232">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-233"><strong>Table MSMQProcessing</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-234">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-235"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-236">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-237"><strong>Table Syndicators</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-238">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-239"><strong>Table SyndicatorsTenantMap</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-240">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-241"><strong>Table Task</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-242">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-244">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-246">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-247"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-248">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-249"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-250">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-251"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-252">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-253"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-254">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-256">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-257"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-258">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3a5d-259"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-260">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3a5d-261"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="a3a5d-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="a3a5d-262">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

