---
title: 'Lync Server 2013 : tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eef65e18de609f7e10fed4aaad9283612778070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="696b8-102">tblADCookie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="696b8-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="696b8-103">_**Dernière modification de la rubrique:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="696b8-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="696b8-104">tblADCookie contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actuels.</span><span class="sxs-lookup"><span data-stu-id="696b8-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="696b8-105">Celles</span><span class="sxs-lookup"><span data-stu-id="696b8-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="696b8-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="696b8-106">Column</span></span></th>
<th><span data-ttu-id="696b8-107">Type</span><span class="sxs-lookup"><span data-stu-id="696b8-107">Type</span></span></th>
<th><span data-ttu-id="696b8-108">Description</span><span class="sxs-lookup"><span data-stu-id="696b8-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="696b8-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="696b8-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="696b8-110">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="696b8-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="696b8-111">GUID principal du domaine qui est surveillé.</span><span class="sxs-lookup"><span data-stu-id="696b8-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="696b8-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="696b8-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="696b8-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="696b8-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="696b8-114">Nom de domaine complet (FQDN) du contrôleur de domaine actuel utilisé pour la synchronisation des services de domaine Active Directory (AD DS). A une valeur d’information.</span><span class="sxs-lookup"><span data-stu-id="696b8-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="696b8-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="696b8-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="696b8-116">image (binaire)</span><span class="sxs-lookup"><span data-stu-id="696b8-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="696b8-117">Cookie de synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="696b8-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="696b8-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="696b8-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="696b8-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="696b8-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="696b8-120">Date et heure de la mise à jour de ligne.</span><span class="sxs-lookup"><span data-stu-id="696b8-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="696b8-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="696b8-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="696b8-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="696b8-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="696b8-123">Temps nécessaire au verrouillage de la ligne pour les modifications.</span><span class="sxs-lookup"><span data-stu-id="696b8-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="696b8-124">Il s’agit d’une partie d’un mécanisme de verrouillage de logiciels qui garantit que seul l’un des services de chat effectue la synchronisation Active Directory à la fois.</span><span class="sxs-lookup"><span data-stu-id="696b8-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="696b8-125">Permettent</span><span class="sxs-lookup"><span data-stu-id="696b8-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="696b8-126">Colonne (s)</span><span class="sxs-lookup"><span data-stu-id="696b8-126">Column(s)</span></span></th>
<th><span data-ttu-id="696b8-127">Description</span><span class="sxs-lookup"><span data-stu-id="696b8-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="696b8-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="696b8-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="696b8-129">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="696b8-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="696b8-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="696b8-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="696b8-131">Clé étrangère avec recherche dans la table principale. prinGuid.</span><span class="sxs-lookup"><span data-stu-id="696b8-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

