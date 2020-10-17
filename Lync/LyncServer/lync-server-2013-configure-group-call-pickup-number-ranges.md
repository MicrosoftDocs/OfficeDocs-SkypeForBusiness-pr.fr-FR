---
title: 'Lync Server 2013 : configuration des plages de numéros de prise d’appel de groupe'
description: 'Lync Server 2013 : configurez les plages de numéros de prise d’appel de groupe.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Group Call Pickup number ranges
ms:assetid: f15f75f6-f965-4558-b612-f40cecdd5d8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945657(v=OCS.15)
ms:contentKeyID: 51541529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f0594bd681a157b8ff479846b2f6f1964a09cad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553280"
---
# <a name="configure-group-call-pickup-number-ranges-in-lync-server-2013"></a><span data-ttu-id="efb54-103">Configuration des plages de numéros de prise d’appel de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efb54-103">Configure Group Call Pickup number ranges in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efb54-104">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="efb54-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="efb54-105">La prise d’appel de groupe est basée sur l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="efb54-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="efb54-106">Lorsque vous déployez la prise d’appel de groupe, vous configurez la table d’orbites de parcage d’appel avec des plages de numéros de téléphone qui sont désignées comme numéros de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="efb54-106">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="efb54-107">Ces numéros de groupe correspondent aux numéros que les utilisateurs composent pour effectuer des appels qui sonnent pour un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="efb54-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="efb54-108">Comme les numéros d’orbite de parcage d’appel, les numéros de groupe de prise d’appel doivent être des extensions virtuelles auxquelles aucun utilisateur ou téléphone n’est affecté.</span><span class="sxs-lookup"><span data-stu-id="efb54-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="efb54-109">Chaque pool frontal où vous déployez la prise d’appel de groupe peut avoir une ou plusieurs plages de numéros de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="efb54-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="efb54-110">Les plages de numéros de groupe doivent être uniques au niveau global dans le déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="efb54-110">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="efb54-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="efb54-111">In This Section</span></span>

  - [<span data-ttu-id="efb54-112">Création ou modification d’une plage de numéros de prise d’appel de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efb54-112">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

  - [<span data-ttu-id="efb54-113">Supprimer une plage de numéros de prise d’appel de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efb54-113">Delete a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-delete-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

