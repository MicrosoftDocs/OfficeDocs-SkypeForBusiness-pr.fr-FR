---
title: 'Lync Server 2013 : tblADCookie'
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
ms.openlocfilehash: 1f733397483693ad4c18418f3e82b9f99cfa640f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="2bd1c-102">tblADCookie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bd1c-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bd1c-103">_**Dernière modification de la rubrique :** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="2bd1c-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="2bd1c-104">tblADCookie contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actifs.</span><span class="sxs-lookup"><span data-stu-id="2bd1c-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="2bd1c-105">Columns</span><span class="sxs-lookup"><span data-stu-id="2bd1c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2bd1c-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="2bd1c-106">Column</span></span></th>
<th><span data-ttu-id="2bd1c-107">Type</span><span class="sxs-lookup"><span data-stu-id="2bd1c-107">Type</span></span></th>
<th><span data-ttu-id="2bd1c-108">Description</span><span class="sxs-lookup"><span data-stu-id="2bd1c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2bd1c-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2bd1c-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="2bd1c-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="2bd1c-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="2bd1c-111">GUID principal du domaine en cours de surveillance.</span><span class="sxs-lookup"><span data-stu-id="2bd1c-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bd1c-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="2bd1c-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="2bd1c-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="2bd1c-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="2bd1c-114">Nom de domaine complet (FQDN) du contrôleur de domaine actuel utilisé pour la synchronisation des services de domaine Active Directory. A une valeur informatif.</span><span class="sxs-lookup"><span data-stu-id="2bd1c-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2bd1c-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="2bd1c-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="2bd1c-116">image (binaire)</span><span class="sxs-lookup"><span data-stu-id="2bd1c-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="2bd1c-117">Cookie de synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2bd1c-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bd1c-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="2bd1c-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="2bd1c-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2bd1c-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="2bd1c-120">Horodatage avec l’heure de mise à jour de ligne.</span><span class="sxs-lookup"><span data-stu-id="2bd1c-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2bd1c-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="2bd1c-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="2bd1c-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2bd1c-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="2bd1c-p101">Heure jusqu’à laquelle la ligne est verrouillée pour modification. Il s’agit d’une partie d’un mécanisme de verrouillage logiciel qui garantit que la synchronisation Active Directory est effectuée par un seul des services de conversation à la fois.</span><span class="sxs-lookup"><span data-stu-id="2bd1c-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="2bd1c-125">Keys</span><span class="sxs-lookup"><span data-stu-id="2bd1c-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2bd1c-126">Colonne (s)</span><span class="sxs-lookup"><span data-stu-id="2bd1c-126">Column(s)</span></span></th>
<th><span data-ttu-id="2bd1c-127">Description</span><span class="sxs-lookup"><span data-stu-id="2bd1c-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2bd1c-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2bd1c-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="2bd1c-129">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="2bd1c-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bd1c-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2bd1c-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="2bd1c-131">Clé étrangère avec recherche dans la table Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="2bd1c-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

