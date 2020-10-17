---
title: 'Lync Server 2013 : détails de la table du serveur de conversation permanente'
description: 'Lync Server 2013 : détails de la table du serveur de conversation permanente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server table details
ms:assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615034(v=OCS.15)
ms:contentKeyID: 48185323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a27feaaccf861d537127f06920cf903be5ae000
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545130"
---
# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="1d648-103">Détails de la table du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-103">Persistent Chat Server table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d648-104">_**Dernière modification de la rubrique :** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="1d648-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="1d648-105">Les rubriques suivantes détaillent les colonnes de chacune des tables de schéma de la base de données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="1d648-105">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1d648-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="1d648-106">In This Section</span></span>

  - [<span data-ttu-id="1d648-107">tblADCookie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-107">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="1d648-108">tblPrincipalMemberDifference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-108">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="1d648-109">tblADUpdates dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-109">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="1d648-110">tblPrincipalMembers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-110">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="1d648-111">tblPrincipalMeta dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-111">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="1d648-112">tblSkippedAffiliations dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-112">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="1d648-113">tblPrincipalType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-113">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="1d648-114">tblPrincipal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-114">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="1d648-115">tblPrincipalAffiliations dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-115">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="1d648-116">tblNode dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-116">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="1d648-117">tblRoleType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-117">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="1d648-118">tblScopePrincipal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-118">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="1d648-119">tblPrincipalRole dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-119">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="1d648-120">tblSiopWhiteList dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-120">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="1d648-121">tblEnumAttribute dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-121">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="1d648-122">tblEnumValue dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-122">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="1d648-123">tblPrincipalInvites dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="1d648-124">tblChat dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-124">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="1d648-125">tblLastInviteId dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-125">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="1d648-126">tblLastChatId dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-126">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="1d648-127">tblPreference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-127">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="1d648-128">tblFileToken dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-128">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="1d648-129">tblServerIdentity dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-129">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="1d648-130">tblAdminLock dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-130">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="1d648-131">tblSystemRevision dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-131">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="1d648-132">tblActivePeers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-132">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="1d648-133">tblConfig dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-133">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="1d648-134">tblComplianceData dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-134">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="1d648-135">tblComplianceFanout dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-135">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="1d648-136">tblComplianceParticipant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-136">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="1d648-137">tblComplianceState dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d648-137">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

