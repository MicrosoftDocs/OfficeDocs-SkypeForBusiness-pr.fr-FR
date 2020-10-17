---
title: 'Lync Server 2013 : table DeRegisterType'
description: 'Lync Server 2013 : table DeRegisterType.'
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
ms.openlocfilehash: afad63c2abeba3e91565e07dac75d0ac6c96ca3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555350"
---
# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="b2c78-103">Table DeRegisterType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2c78-103">DeRegisterType table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2c78-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b2c78-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b2c78-105">La table DeRegisterType est une table statique qui stocke la liste des différents types de désinscriptions liées aux utilisateurs, tels que « initiative du client », « expiration de l’inscription » ou « absence de réponse du client ».</span><span class="sxs-lookup"><span data-stu-id="b2c78-105">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2c78-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="b2c78-106">Column</span></span></th>
<th><span data-ttu-id="b2c78-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="b2c78-107">Data Type</span></span></th>
<th><span data-ttu-id="b2c78-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="b2c78-108">Key/Index</span></span></th>
<th><span data-ttu-id="b2c78-109">Détails</span><span class="sxs-lookup"><span data-stu-id="b2c78-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2c78-110"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="b2c78-110"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2c78-111">entier très petit</span><span class="sxs-lookup"><span data-stu-id="b2c78-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b2c78-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="b2c78-112">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2c78-113"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="b2c78-113"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="b2c78-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b2c78-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2c78-115">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="b2c78-115">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="b2c78-116">0 -- Inconnu</span><span class="sxs-lookup"><span data-stu-id="b2c78-116">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="b2c78-117">1 -- Désinscription à l’initiative du client</span><span class="sxs-lookup"><span data-stu-id="b2c78-117">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="b2c78-118">2 -- Expiration de l’inscription</span><span class="sxs-lookup"><span data-stu-id="b2c78-118">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="b2c78-119">3 – Client bloqué</span><span class="sxs-lookup"><span data-stu-id="b2c78-119">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="b2c78-120">4 -- Modification des attributs de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="b2c78-120">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="b2c78-121">5 – Modification du serveur d’inscriptions préféré</span><span class="sxs-lookup"><span data-stu-id="b2c78-121">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="b2c78-122">6 -- Client hérité en mode survie</span><span class="sxs-lookup"><span data-stu-id="b2c78-122">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

