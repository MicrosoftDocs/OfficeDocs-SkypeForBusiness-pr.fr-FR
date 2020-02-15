---
title: 'Lync Server 2013 : table DeRegisterType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 915a5d0a2c5c4a5f38063b56dc133d2558aa65ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="6f00a-102">Table DeRegisterType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f00a-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f00a-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6f00a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6f00a-104">La table DeRegisterType est une table statique qui stocke la liste des différents types de désinscriptions liées aux utilisateurs, tels que « initiative du client », « expiration de l’inscription » ou « absence de réponse du client ».</span><span class="sxs-lookup"><span data-stu-id="6f00a-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f00a-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="6f00a-105">Column</span></span></th>
<th><span data-ttu-id="6f00a-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="6f00a-106">Data Type</span></span></th>
<th><span data-ttu-id="6f00a-107">Clé/index</span><span class="sxs-lookup"><span data-stu-id="6f00a-107">Key/Index</span></span></th>
<th><span data-ttu-id="6f00a-108">Détails</span><span class="sxs-lookup"><span data-stu-id="6f00a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f00a-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="6f00a-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="6f00a-110">entier très petit</span><span class="sxs-lookup"><span data-stu-id="6f00a-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6f00a-111">Primaire</span><span class="sxs-lookup"><span data-stu-id="6f00a-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f00a-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="6f00a-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="6f00a-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6f00a-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f00a-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="6f00a-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="6f00a-115">0 -- Inconnu</span><span class="sxs-lookup"><span data-stu-id="6f00a-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="6f00a-116">1 -- Désinscription à l’initiative du client</span><span class="sxs-lookup"><span data-stu-id="6f00a-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="6f00a-117">2 -- Expiration de l’inscription</span><span class="sxs-lookup"><span data-stu-id="6f00a-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="6f00a-118">3 – Client bloqué</span><span class="sxs-lookup"><span data-stu-id="6f00a-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="6f00a-119">4 -- Modification des attributs de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="6f00a-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="6f00a-120">5 – Modification du serveur d’inscriptions préféré</span><span class="sxs-lookup"><span data-stu-id="6f00a-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="6f00a-121">6 -- Client hérité en mode survie</span><span class="sxs-lookup"><span data-stu-id="6f00a-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

