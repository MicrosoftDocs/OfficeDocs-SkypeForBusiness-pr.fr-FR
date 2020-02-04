---
title: 'Lync Server 2013 : Informations sur la table des enregistrements des détails des appels'
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
ms.openlocfilehash: 650caa5244eaf796c066f1388f2fcbb5d3b0703a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="f6eed-102">Informations sur la table des enregistrements des détails des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-102">CDR table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6eed-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="f6eed-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="f6eed-104">Les rubriques suivantes décrivent en détail les colonnes dans chaque table de schéma de la base de données d’enregistrements des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="f6eed-104">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f6eed-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f6eed-105">In This Section</span></span>

  - [<span data-ttu-id="f6eed-106">Table Application dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-106">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="f6eed-107">Table CallPriorities dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-107">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="f6eed-108">Table CallType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-108">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="f6eed-109">Table ClientVersions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-109">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="f6eed-110">Table ConferenceJoinTimeThresholds dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-110">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="f6eed-111">Table ConferenceMessageCount dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-111">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="f6eed-112">Table Conferences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-112">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="f6eed-113">Table ConferenceSessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-113">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="f6eed-114">Table ConferenceUris dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-114">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="f6eed-115">Table ContentTypes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-115">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="f6eed-116">Table DeRegisterType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-116">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="f6eed-117">Table Devices dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-117">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="f6eed-118">Table Dialogs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-118">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="f6eed-119">Table EdgeServers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-119">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="f6eed-120">Table ErrorCategory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-120">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="f6eed-121">Table ErrorDef dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-121">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="f6eed-122">Table ErrorReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-122">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="f6eed-123">Table FileTransfers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-123">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="f6eed-124">Table FocusJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-124">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="f6eed-125">Table frontale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-125">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="f6eed-126">Table Gateways dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-126">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="f6eed-127">Table HardwareVersions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-127">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="f6eed-128">Table IMReportSummary dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-128">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="f6eed-129">Table Locations dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-129">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="f6eed-130">Table Manufacturers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-130">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="f6eed-131">Table McuJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-131">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="f6eed-132">Table Mcus dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-132">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="f6eed-133">Table Media dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-133">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="f6eed-134">Table MediaList dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-134">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="f6eed-135">Table MediationServers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-135">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="f6eed-136">Table MSMQProcessing dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-136">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="f6eed-137">Table !Phones dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-137">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="f6eed-138">Table Pools dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-138">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="f6eed-139">Table ProgressReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-139">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="f6eed-140">Table PurgeSettings dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-140">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="f6eed-141">Table Registration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-141">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="f6eed-142">Table Roles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-142">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="f6eed-143">Table Servers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-143">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="f6eed-144">Table SessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-144">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="f6eed-145">Table SIPResponseMetaData dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-145">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="f6eed-146">Table syndicators dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-146">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="f6eed-147">Table SyndicatorsTenantMap dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-147">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="f6eed-148">Tableau de tâches dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-148">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="f6eed-149">Table Tenants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-149">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="f6eed-150">Table UriTypes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-150">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="f6eed-151">Table Users dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-151">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="f6eed-152">Table UserAgentDef dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-152">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="f6eed-153">Table UserStatistics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-153">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="f6eed-154">Table VoipDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eed-154">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

