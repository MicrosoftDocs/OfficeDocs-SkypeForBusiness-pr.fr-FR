---
title: 'Lync Server 2013 : tblADCookie'
description: 'Lync Server 2013 : tblADCookie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c3dde3730ede07b204a473c7fe0a5ab68054d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573720"
---
# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="7ebe6-103">tblADCookie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ebe6-103">tblADCookie in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ebe6-104">_**Dernière modification de la rubrique :** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="7ebe6-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="7ebe6-105">tblADCookie contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actifs.</span><span class="sxs-lookup"><span data-stu-id="7ebe6-105">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="7ebe6-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="7ebe6-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ebe6-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="7ebe6-107">Column</span></span></th>
<th><span data-ttu-id="7ebe6-108">Type</span><span class="sxs-lookup"><span data-stu-id="7ebe6-108">Type</span></span></th>
<th><span data-ttu-id="7ebe6-109">Description</span><span class="sxs-lookup"><span data-stu-id="7ebe6-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ebe6-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="7ebe6-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="7ebe6-111">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="7ebe6-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="7ebe6-112">GUID principal du domaine en cours de surveillance.</span><span class="sxs-lookup"><span data-stu-id="7ebe6-112">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ebe6-113">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="7ebe6-113">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="7ebe6-114">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="7ebe6-114">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="7ebe6-115">Nom de domaine complet (FQDN) du contrôleur de domaine actuel utilisé pour la synchronisation des services de domaine Active Directory. A une valeur informatif.</span><span class="sxs-lookup"><span data-stu-id="7ebe6-115">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ebe6-116">adcContent</span><span class="sxs-lookup"><span data-stu-id="7ebe6-116">adcContent</span></span></p></td>
<td><p><span data-ttu-id="7ebe6-117">image (binaire)</span><span class="sxs-lookup"><span data-stu-id="7ebe6-117">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="7ebe6-118">Cookie de synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7ebe6-118">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ebe6-119">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="7ebe6-119">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="7ebe6-120">DateHeure</span><span class="sxs-lookup"><span data-stu-id="7ebe6-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="7ebe6-121">Horodatage avec l’heure de mise à jour de ligne.</span><span class="sxs-lookup"><span data-stu-id="7ebe6-121">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ebe6-122">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="7ebe6-122">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="7ebe6-123">DateHeure</span><span class="sxs-lookup"><span data-stu-id="7ebe6-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="7ebe6-p101">Heure jusqu’à laquelle la ligne est verrouillée pour modification. Il s’agit d’une partie d’un mécanisme de verrouillage logiciel qui garantit que la synchronisation Active Directory est effectuée par un seul des services de conversation à la fois.</span><span class="sxs-lookup"><span data-stu-id="7ebe6-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="7ebe6-126">Keys</span><span class="sxs-lookup"><span data-stu-id="7ebe6-126">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ebe6-127">Colonne (s)</span><span class="sxs-lookup"><span data-stu-id="7ebe6-127">Column(s)</span></span></th>
<th><span data-ttu-id="7ebe6-128">Description</span><span class="sxs-lookup"><span data-stu-id="7ebe6-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ebe6-129">prinGuid</span><span class="sxs-lookup"><span data-stu-id="7ebe6-129">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="7ebe6-130">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="7ebe6-130">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ebe6-131">prinGuid</span><span class="sxs-lookup"><span data-stu-id="7ebe6-131">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="7ebe6-132">Clé étrangère avec recherche dans la table Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="7ebe6-132">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

