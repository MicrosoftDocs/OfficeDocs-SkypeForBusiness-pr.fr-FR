---
title: 'Lync Server 2013 : Liste des tables d’enregistrement des détails des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1ac043d144e73d8e1b40ca717e278619e053fdc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="9ce75-102">Liste des tables d’enregistrement des détails des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ce75-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ce75-103">_**Dernière modification de la rubrique:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="9ce75-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="9ce75-104">Le schéma de base de données d’enregistrement des détails des appels (CDR) se compose des tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="9ce75-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="9ce75-105">Tableaux statiques</span><span class="sxs-lookup"><span data-stu-id="9ce75-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ce75-106">Table</span><span class="sxs-lookup"><span data-stu-id="9ce75-106">Table</span></span></th>
<th><span data-ttu-id="9ce75-107">Description</span><span class="sxs-lookup"><span data-stu-id="9ce75-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-108"><a href="lync-server-2013-callpriorities-table.md">Table CallPriorities dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-109">Cette liste contient les différentes priorités d’appels (par exemple, l’urgence, le standard, le standard, les non urgentes, etc.).</span><span class="sxs-lookup"><span data-stu-id="9ce75-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Table ConferenceJoinTimeThresholds dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-111">Stocke les limites de classification utilisées par le rapport de synthèse des heures de participation à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="9ce75-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-112"><a href="lync-server-2013-deregistertype-table.md">Table DeRegisterType dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-113">Stocke la liste des causes possibles de l’inscription d’un utilisateur &quot;, telles que&quot; &quot;le client lancé&quot; &quot;, l’inscription&quot; a expiré, le blocage du client, etc.</span><span class="sxs-lookup"><span data-stu-id="9ce75-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-114"><a href="lync-server-2013-medialist-table.md">Table MediaList dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-115">Stocke la liste de types de médias qui peuvent générer des entrées dans la base de données (par exemple, messagerie instantanée, audio, vidéo et transfert de fichiers).</span><span class="sxs-lookup"><span data-stu-id="9ce75-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-116"><a href="lync-server-2013-purgesettings-table.md">Table PurgeSettings dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-117">Stocke les informations qui spécifient si les enregistrements de détails des appels obsolètes sont automatiquement supprimés de la base de données CDR.</span><span class="sxs-lookup"><span data-stu-id="9ce75-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-118"><a href="lync-server-2013-roles-table.md">Table Roles dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-119">Stocke la liste des rôles de conférences possibles (par exemple, participants et présentateur).</span><span class="sxs-lookup"><span data-stu-id="9ce75-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Table SIPResponseMetaData dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-121">Stocke une liste des codes de réponse SIP et la classification et la définition de chacun de ces codes.</span><span class="sxs-lookup"><span data-stu-id="9ce75-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="9ce75-122">Tableaux pris en charge</span><span class="sxs-lookup"><span data-stu-id="9ce75-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ce75-123">Table</span><span class="sxs-lookup"><span data-stu-id="9ce75-123">Table</span></span></th>
<th><span data-ttu-id="9ce75-124">Description</span><span class="sxs-lookup"><span data-stu-id="9ce75-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-125"><a href="lync-server-2013-clientversions-table.md">Table ClientVersions dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-126">Stocke les clients (le type de client et le numéro de version) de chaque client impliqué dans un appel et les informations capturées dans cette base de données.</span><span class="sxs-lookup"><span data-stu-id="9ce75-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-127"><a href="lync-server-2013-conferenceuris-table.md">Table ConferenceUris dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-128">Stocke une liste de ConferenceURIs utilisés dans les appels liés à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="9ce75-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-129"><a href="lync-server-2013-contenttypes-table.md">Table ContentTypes dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-130">Stocke une liste de types de contenu SIP (Session Initiation Protocol) qui sont utilisés dans les appels d’égal à égal et les téléconférences.</span><span class="sxs-lookup"><span data-stu-id="9ce75-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-131"><a href="lync-server-2013-devices-table.md">Table Devices dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-132">Stocke une liste d’appareils, dont le fabricant, la version matérielle et l’adresse MAC.</span><span class="sxs-lookup"><span data-stu-id="9ce75-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-133"><a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-134">Stocke les informations sur l’ID de boîte de dialogue de chaque session dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="9ce75-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-135"><a href="lync-server-2013-edgeservers-table.md">Table EdgeServers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-136">Stocke une liste de serveurs Edge utilisés pour les appels externes.</span><span class="sxs-lookup"><span data-stu-id="9ce75-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-137"><a href="lync-server-2013-gateways-table.md">Table Gateways dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-138">Stocke une liste des passerelles utilisées pour les appels voix sur IP (VoIP).</span><span class="sxs-lookup"><span data-stu-id="9ce75-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-139"><a href="lync-server-2013-hardwareversions-table.md">Table HardwareVersions dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-140">Stocke une liste de versions matérielles d’appareils (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="9ce75-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-141"><a href="lync-server-2013-manufacturers-table.md">Table Manufacturers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-142">Stocke une liste de fabricants de périphériques (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="9ce75-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-143"><a href="lync-server-2013-mcus-table.md">Table Mcus dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-144">Stocke des informations sur les divers serveurs de conférence A/V et leurs URI.</span><span class="sxs-lookup"><span data-stu-id="9ce75-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-145"><a href="lync-server-2013-mediationservers-table.md">Table MediationServers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-146">Stocke une liste de serveurs de médiation qui sont utilisés pour les appels VoIP.</span><span class="sxs-lookup"><span data-stu-id="9ce75-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-147"><a href="lync-server-2013-phones-table.md">Table !Phones dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-148">Stocke tous les numéros de téléphone utilisés pour les appels VoIP archivés ou dont les détails des appels ont été enregistrés.</span><span class="sxs-lookup"><span data-stu-id="9ce75-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-149"><a href="lync-server-2013-pools-table.md">Table Pools dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-150">Stocke les noms de la liste des messages INSTANTANÉs capturés.</span><span class="sxs-lookup"><span data-stu-id="9ce75-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-151"><a href="lync-server-2013-servers-table.md">Table Servers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-152">Stocke le nom des serveurs impliqué dans les appels.</span><span class="sxs-lookup"><span data-stu-id="9ce75-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-153"><a href="lync-server-2013-tenants-table.md">Table Tenants dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-154">Stocke les locataires pris en charge par le déploiement actuel.</span><span class="sxs-lookup"><span data-stu-id="9ce75-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="9ce75-155">Il s’agit de clients intégrés d’entreprise, d’utilisateurs fédérés, d’utilisateurs de la connectivité de messagerie instantanée publique et d’utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="9ce75-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-156"><a href="lync-server-2013-useragentdef-table.md">Table UserAgentDef dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-157">Mappe des identificateurs d’agent utilisateur aux noms descriptifs de l’agent.</span><span class="sxs-lookup"><span data-stu-id="9ce75-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-158"><a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-159">Stocke les URI utilisateur des utilisateurs qui ont participé à des sessions enregistrées ou archivées dans cette base de données.</span><span class="sxs-lookup"><span data-stu-id="9ce75-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-160"><a href="lync-server-2013-userstatistics-table.md">Table UserStatistics dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-161">Stocke des informations sur l’utilisation individuelle du système par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9ce75-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="9ce75-162">Tableaux spécifiques aux enregistrements de la Conférence CDR</span><span class="sxs-lookup"><span data-stu-id="9ce75-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ce75-163">Table</span><span class="sxs-lookup"><span data-stu-id="9ce75-163">Table</span></span></th>
<th><span data-ttu-id="9ce75-164">Description</span><span class="sxs-lookup"><span data-stu-id="9ce75-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-165"><a href="lync-server-2013-conferences-table.md">Table Conferences dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-166">Stocke des informations sur toutes les conférences archivées ou dont les détails ont été enregistrés, y compris ConferenceURI et les heures de début et de fin.</span><span class="sxs-lookup"><span data-stu-id="9ce75-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Table ConferenceSessionDetails dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-168">Stocke des informations sur chaque session de conférence SIP, y compris l’heure de début et de fin, l’ID d’utilisateur, le code de réponse et l’ID de diagnostic de chaque session.</span><span class="sxs-lookup"><span data-stu-id="9ce75-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Table FocusJoinsAndLeaves dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-170">Stocke des informations sur les joints et les feuilles de conférence, y compris le rôle et la version du client.</span><span class="sxs-lookup"><span data-stu-id="9ce75-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Table McuJoinsAndLeaves dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-172">Stocke des informations sur les serveurs de téléconférence A/V qui participent à une conférence et l’utilisateur a rejoint et laisse des heures.</span><span class="sxs-lookup"><span data-stu-id="9ce75-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="9ce75-173">Tableaux de messages dans les conférences de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="9ce75-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ce75-174">Table</span><span class="sxs-lookup"><span data-stu-id="9ce75-174">Table</span></span></th>
<th><span data-ttu-id="9ce75-175">Description</span><span class="sxs-lookup"><span data-stu-id="9ce75-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-176"><a href="lync-server-2013-conferencemessagecount-table.md">Table ConferenceMessageCount dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-177">Pour chaque conférence par messagerie instantanée, stocke le nombre de messages envoyés par chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9ce75-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-178"><a href="lync-server-2013-imreportsummary-table.md">Table IMReportSummary dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-179">Fournit un rapport global sur les sessions de messagerie instantanée tenues au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="9ce75-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="9ce75-180">Tables pour les sessions d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="9ce75-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ce75-181">Table</span><span class="sxs-lookup"><span data-stu-id="9ce75-181">Table</span></span></th>
<th><span data-ttu-id="9ce75-182">Description</span><span class="sxs-lookup"><span data-stu-id="9ce75-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-183"><a href="lync-server-2013-sessiondetails-table.md">Table SessionDetails dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-184">Stocke des informations sur chaque session d’égal à égal, y compris l’heure de début et de fin, l’ID d’utilisateur, le code de réponse et le nombre de messages pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9ce75-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-185"><a href="lync-server-2013-filetransfers-table.md">Table FileTransfers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-186">Stocke les informations sur les sessions de transfert de fichiers, y compris le nom de fichier et le résultat (accepté, rejeté ou annulé).</span><span class="sxs-lookup"><span data-stu-id="9ce75-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-187"><a href="lync-server-2013-media-table.md">Table Media dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-188">Stocke les informations sur les différents types de médias impliqués dans les sessions d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="9ce75-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="9ce75-189">Tableau des détails des appels VoIP</span><span class="sxs-lookup"><span data-stu-id="9ce75-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ce75-190">Table</span><span class="sxs-lookup"><span data-stu-id="9ce75-190">Table</span></span></th>
<th><span data-ttu-id="9ce75-191">Description</span><span class="sxs-lookup"><span data-stu-id="9ce75-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-192"><a href="lync-server-2013-voipdetails-table.md">Table VoipDetails dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-193">Pour chaque appel VoIP/PSTN à deux tiers, enregistre les informations relatives à l’appel, telles que l’ID de téléphone du téléphone VoIP, la passerelle utilisée et la partie déconnectée.</span><span class="sxs-lookup"><span data-stu-id="9ce75-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="9ce75-194">Fait référence à la <a href="lync-server-2013-sessiondetails-table.md">table SessionDetails dans Lync Server 2013</a> pour les appels de début/fin et le code de réponse.</span><span class="sxs-lookup"><span data-stu-id="9ce75-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="9ce75-195">S’il s’agit d’un utilisateur VoIP ou d’un serveur de médiation qui intervient dans le cas d’un appel, un enregistrement est créé dans ce tableau.</span><span class="sxs-lookup"><span data-stu-id="9ce75-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="9ce75-196">Les informations sur les appels VoIP/VoIP qui n’impliquent pas de téléphone RTC (réseau téléphonique commuté) sont capturées dans la <A href="lync-server-2013-sessiondetails-table.md">table SessionDetails dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9ce75-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="9ce75-197">Tableau pour l’audit d’appels E9-1-1</span><span class="sxs-lookup"><span data-stu-id="9ce75-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ce75-198">Table</span><span class="sxs-lookup"><span data-stu-id="9ce75-198">Table</span></span></th>
<th><span data-ttu-id="9ce75-199">Description</span><span class="sxs-lookup"><span data-stu-id="9ce75-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-200"><a href="lync-server-2013-locations-table.md">Table Locations dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-201">Pour chaque appel d’urgence, par exemple un appel 9-1-1 amélioré (E9-1-1), stocke les informations d’emplacement relatives à l’appel.</span><span class="sxs-lookup"><span data-stu-id="9ce75-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="9ce75-202">Fait référence à la <a href="lync-server-2013-sessiondetails-table.md">table SessionDetails dans Lync Server 2013</a> pour les appels de début/fin et le code de réponse.</span><span class="sxs-lookup"><span data-stu-id="9ce75-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="9ce75-203">Ce tableau contient uniquement l’objet blob d’emplacement pour l’appel E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="9ce75-203">This table only contains the location blob for the E9-1-1 call.</span></span> <span data-ttu-id="9ce75-204">Fait référence à la table SessionDetails pour obtenir d’autres informations détaillées sur l’appel.</span><span class="sxs-lookup"><span data-stu-id="9ce75-204">Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="9ce75-205">Tableaux pour la résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="9ce75-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ce75-206">Table</span><span class="sxs-lookup"><span data-stu-id="9ce75-206">Table</span></span></th>
<th><span data-ttu-id="9ce75-207">Description</span><span class="sxs-lookup"><span data-stu-id="9ce75-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-208"><a href="lync-server-2013-application-table.md">Table Application dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-209">Stocke les informations relatives à divers processus au sein de Lync Server 2013 qui participent au routage et aux connexions.</span><span class="sxs-lookup"><span data-stu-id="9ce75-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-210"><a href="lync-server-2013-calltype-table.md">Table CallType dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-211">Stocke des informations sur les types de l’appel (par exemple, «audio», «messages instantanés», «audio et vidéo» et «partage d’application»).</span><span class="sxs-lookup"><span data-stu-id="9ce75-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-212"><a href="lync-server-2013-errorcategory-table.md">Table ErrorCategory dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-213">Stocke le nom convivial pour chaque classification de diagnostic Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ce75-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-214"><a href="lync-server-2013-errordef-table.md">Table ErrorDef dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-215">Stocke des informations sur les types d’erreurs et leurs définitions.</span><span class="sxs-lookup"><span data-stu-id="9ce75-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-216"><a href="lync-server-2013-errorreport-table.md">Table ErrorReport dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-217">Stocke les informations sur les erreurs qui se sont produites.</span><span class="sxs-lookup"><span data-stu-id="9ce75-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-218"><a href="lync-server-2013-progressreport-table.md">Table ProgressReport dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ce75-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9ce75-219">Stocke des informations sur les rapports de progression de diverses étapes associées aux processus Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ce75-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9ce75-220">Les tables de la liste suivante sont utilisées en interne par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ce75-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="9ce75-221">Leurs détails ne sont pas décrits dans ce document.</span><span class="sxs-lookup"><span data-stu-id="9ce75-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="9ce75-222">Tables pour une utilisation interne par Lync Server</span><span class="sxs-lookup"><span data-stu-id="9ce75-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ce75-223">Table</span><span class="sxs-lookup"><span data-stu-id="9ce75-223">Table</span></span></th>
<th><span data-ttu-id="9ce75-224">Description</span><span class="sxs-lookup"><span data-stu-id="9ce75-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-225"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-226">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-227"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-228">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-229"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-230">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-231"><strong>Table frontale</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-232">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-233"><strong>Table MSMQProcessing</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-234">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-235"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-236">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-237"><strong>Table syndicators</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-238">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-239"><strong>Table SyndicatorsTenantMap</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-240">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-241"><strong>Tableau de tâches</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-242">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-244">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-246">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-247"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-248">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-249"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-250">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-251"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-252">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-253"><strong>Fuseau</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-254">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-256">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-257"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-258">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce75-259"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-260">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce75-261"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="9ce75-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="9ce75-262">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="9ce75-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

