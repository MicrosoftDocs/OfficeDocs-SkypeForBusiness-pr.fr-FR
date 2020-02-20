---
title: 'Lync Server 2013 : table clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47c447d18589f8e0cd86c007df74a21287be949f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="a4035-102">Table locataires dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4035-102">Tenants table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4035-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a4035-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a4035-p101">La table Tenants est une table de prise en charge qui stocke une liste des différents clients. Chaque enregistrement de la table représente un client.</span><span class="sxs-lookup"><span data-stu-id="a4035-p101">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a4035-106">Dans les déploiement sur site, CDR utilise l’ID de client intégré pour indiquer différents types d’authentification, tels que la connectivité de messagerie instantanée publique, l’authentification fédérée et l’authentification anonyme.</span><span class="sxs-lookup"><span data-stu-id="a4035-106">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4035-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="a4035-107">Column</span></span></th>
<th><span data-ttu-id="a4035-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="a4035-108">Data Type</span></span></th>
<th><span data-ttu-id="a4035-109">Clé/index</span><span class="sxs-lookup"><span data-stu-id="a4035-109">Key/Index</span></span></th>
<th><span data-ttu-id="a4035-110">Détails</span><span class="sxs-lookup"><span data-stu-id="a4035-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4035-111"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="a4035-111"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4035-112">int</span><span class="sxs-lookup"><span data-stu-id="a4035-112">int</span></span></p></td>
<td><p><span data-ttu-id="a4035-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="a4035-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a4035-114">Numéro unique identifiant cet ID de client.</span><span class="sxs-lookup"><span data-stu-id="a4035-114">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4035-115"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="a4035-115"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a4035-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a4035-116">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4035-117">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="a4035-117">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="a4035-118">00000000-0000-0000-0000-000000000000 (entreprise)</span><span class="sxs-lookup"><span data-stu-id="a4035-118">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="a4035-119">00000000-0000-0000-0000-000000000001 (fédéré)</span><span class="sxs-lookup"><span data-stu-id="a4035-119">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="a4035-120">00000000-0000-0000-0000-000000000002 (anonyme)</span><span class="sxs-lookup"><span data-stu-id="a4035-120">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="a4035-121">00000000-0000-0000-0000-000000000003 (connectivité PIC)</span><span class="sxs-lookup"><span data-stu-id="a4035-121">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

