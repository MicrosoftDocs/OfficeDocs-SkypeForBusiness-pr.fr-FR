---
title: 'Lync Server 2013 : détails de la table CDR'
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
ms.openlocfilehash: 876fb58c9e9a953e89c02b3b4ef6bd76255c1d65
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="6536a-102">Détails de la table CDR dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-102">CDR table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6536a-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6536a-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6536a-104">Les rubriques suivantes présentent en détail les colonnes de chacune des tables de schéma de la base de données des enregistrements des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="6536a-104">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6536a-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6536a-105">In This Section</span></span>

  - [<span data-ttu-id="6536a-106">Table application dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-106">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="6536a-107">Table table callpriorities dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-107">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="6536a-108">Table CallType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-108">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="6536a-109">Table ClientVersions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-109">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="6536a-110">Table ConferenceJoinTimeThresholds dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-110">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="6536a-111">Table ConferenceMessageCount dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-111">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="6536a-112">Tableau conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-112">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="6536a-113">Table ConferenceSessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-113">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="6536a-114">Table ConferenceUris dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-114">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="6536a-115">Table ContentTypes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-115">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="6536a-116">Table DeRegisterType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-116">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="6536a-117">Table Devices dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-117">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="6536a-118">Table Dialogs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-118">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="6536a-119">Table table edgeservers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-119">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="6536a-120">Table ErrorCategory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-120">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="6536a-121">Table table errordef dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-121">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="6536a-122">Table ErrorReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-122">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="6536a-123">Table FileTransfers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-123">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="6536a-124">Table FocusJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-124">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="6536a-125">Table FrontEnd dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-125">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="6536a-126">Tableau des passerelles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-126">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="6536a-127">Table table hardwareversions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-127">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="6536a-128">Table IMReportSummary dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-128">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="6536a-129">Table locations dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-129">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="6536a-130">Table Manufacturers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-130">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="6536a-131">Table McuJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-131">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="6536a-132">Table MCU dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-132">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="6536a-133">Table Media dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-133">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="6536a-134">Table médial dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-134">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="6536a-135">Table table mediationservers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-135">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="6536a-136">Table table msmqprocessing dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-136">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="6536a-137">Table téléphones dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-137">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="6536a-138">Table pools dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-138">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="6536a-139">Table ProgressReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-139">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="6536a-140">Table PurgeSettings dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-140">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="6536a-141">Table Registration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-141">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="6536a-142">Table Roles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-142">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="6536a-143">Table Servers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-143">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="6536a-144">Table SessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-144">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="6536a-145">Table SIPResponseMetaData dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-145">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="6536a-146">Table table syndicators dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-146">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="6536a-147">Table table syndicatorstenantmap dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-147">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="6536a-148">Table de tâches dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-148">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="6536a-149">Table locataires dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-149">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="6536a-150">Table UriTypes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-150">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="6536a-151">Table users dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-151">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="6536a-152">Table table useragentdef dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-152">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="6536a-153">Table UserStatistics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-153">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="6536a-154">Table VoipDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6536a-154">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

