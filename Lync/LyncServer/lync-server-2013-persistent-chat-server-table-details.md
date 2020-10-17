---
title: 'Lync Server 2013 : détails de la table du serveur de conversation permanente'
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
ms.openlocfilehash: cde75ceb141a81af1b6a093742edd23b4adf1716
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524221"
---
# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="671d0-102">Détails de la table du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-102">Persistent Chat Server table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="671d0-103">_**Dernière modification de la rubrique :** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="671d0-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="671d0-104">Les rubriques suivantes détaillent les colonnes de chacune des tables de schéma de la base de données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="671d0-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="671d0-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="671d0-105">In This Section</span></span>

  - [<span data-ttu-id="671d0-106">tblADCookie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-106">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="671d0-107">tblPrincipalMemberDifference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-107">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="671d0-108">tblADUpdates dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-108">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="671d0-109">tblPrincipalMembers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-109">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="671d0-110">tblPrincipalMeta dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-110">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="671d0-111">tblSkippedAffiliations dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-111">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="671d0-112">tblPrincipalType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-112">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="671d0-113">tblPrincipal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-113">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="671d0-114">tblPrincipalAffiliations dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-114">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="671d0-115">tblNode dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-115">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="671d0-116">tblRoleType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-116">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="671d0-117">tblScopePrincipal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-117">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="671d0-118">tblPrincipalRole dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-118">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="671d0-119">tblSiopWhiteList dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-119">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="671d0-120">tblEnumAttribute dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-120">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="671d0-121">tblEnumValue dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-121">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="671d0-122">tblPrincipalInvites dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-122">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="671d0-123">tblChat dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="671d0-124">tblLastInviteId dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-124">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="671d0-125">tblLastChatId dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-125">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="671d0-126">tblPreference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-126">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="671d0-127">tblFileToken dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-127">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="671d0-128">tblServerIdentity dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-128">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="671d0-129">tblAdminLock dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-129">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="671d0-130">tblSystemRevision dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-130">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="671d0-131">tblActivePeers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-131">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="671d0-132">tblConfig dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-132">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="671d0-133">tblComplianceData dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-133">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="671d0-134">tblComplianceFanout dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-134">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="671d0-135">tblComplianceParticipant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-135">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="671d0-136">tblComplianceState dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671d0-136">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

