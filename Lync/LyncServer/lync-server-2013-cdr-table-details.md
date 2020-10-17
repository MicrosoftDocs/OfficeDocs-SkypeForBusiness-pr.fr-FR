---
title: 'Lync Server 2013 : détails de la table CDR'
description: 'Lync Server 2013 : détails de la table CDR.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 331a3dfd4ffccac2ac4a442eeb9ad9171defb41c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544390"
---
# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="8359f-103">Détails de la table CDR dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-103">CDR table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8359f-104">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="8359f-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="8359f-105">Les rubriques suivantes présentent en détail les colonnes de chacune des tables de schéma de la base de données des enregistrements des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="8359f-105">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8359f-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="8359f-106">In This Section</span></span>

  - [<span data-ttu-id="8359f-107">Table application dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-107">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="8359f-108">Table table callpriorities dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-108">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="8359f-109">Table CallType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-109">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="8359f-110">Table ClientVersions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-110">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="8359f-111">Table ConferenceJoinTimeThresholds dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-111">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="8359f-112">Table ConferenceMessageCount dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-112">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="8359f-113">Tableau conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-113">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="8359f-114">Table ConferenceSessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-114">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="8359f-115">Table ConferenceUris dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-115">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="8359f-116">Table ContentTypes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-116">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="8359f-117">Table DeRegisterType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-117">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="8359f-118">Table Devices dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-118">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="8359f-119">Table Dialogs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-119">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="8359f-120">Table table edgeservers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-120">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="8359f-121">Table ErrorCategory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-121">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="8359f-122">Table table errordef dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-122">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="8359f-123">Table ErrorReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-123">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="8359f-124">Table FileTransfers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-124">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="8359f-125">Table FocusJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-125">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="8359f-126">Table FrontEnd dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-126">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="8359f-127">Tableau des passerelles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-127">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="8359f-128">Table table hardwareversions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-128">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="8359f-129">Table IMReportSummary dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-129">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="8359f-130">Table locations dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-130">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="8359f-131">Table Manufacturers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-131">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="8359f-132">Table McuJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-132">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="8359f-133">Table MCU dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-133">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="8359f-134">Table Media dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-134">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="8359f-135">Table médial dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-135">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="8359f-136">Table table mediationservers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-136">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="8359f-137">Table table msmqprocessing dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-137">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="8359f-138">Table téléphones dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-138">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="8359f-139">Table pools dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-139">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="8359f-140">Table ProgressReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-140">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="8359f-141">Table PurgeSettings dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-141">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="8359f-142">Table Registration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-142">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="8359f-143">Table Roles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-143">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="8359f-144">Table Servers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-144">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="8359f-145">Table SessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-145">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="8359f-146">Table SIPResponseMetaData dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-146">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="8359f-147">Table table syndicators dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-147">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="8359f-148">Table table syndicatorstenantmap dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-148">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="8359f-149">Table de tâches dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-149">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="8359f-150">Table locataires dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-150">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="8359f-151">Table UriTypes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-151">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="8359f-152">Table users dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-152">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="8359f-153">Table table useragentdef dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-153">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="8359f-154">Table UserStatistics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-154">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="8359f-155">Table VoipDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8359f-155">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

