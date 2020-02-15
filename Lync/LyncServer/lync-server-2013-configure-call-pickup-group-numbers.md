---
title: 'Lync Server 2013 : configurer les numéros de groupe de prise d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call pickup group numbers
ms:assetid: 5cc67f0b-d70d-446a-8db1-befda8671121
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945631(v=OCS.15)
ms:contentKeyID: 51541479
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42023f82240e99695678bc25f1f38b7a20234d37
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-pickup-group-numbers-in-lync-server-2013"></a><span data-ttu-id="82a5c-102">Configurer les numéros de groupe de prise d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82a5c-102">Configure call pickup group numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82a5c-103">_**Dernière modification de la rubrique :** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="82a5c-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="82a5c-104">La prise d’appel de groupe est basée sur l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="82a5c-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="82a5c-105">Lorsque vous déployez la prise d’appel de groupe, vous configurez la table d’orbites de parcage d’appel avec des plages de numéros de téléphone qui sont désignées comme numéros de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="82a5c-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="82a5c-106">Ces numéros de groupe correspondent aux numéros que les utilisateurs composent pour effectuer des appels qui sonnent pour un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="82a5c-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="82a5c-107">Comme les numéros d’orbite de parcage d’appel, les numéros de groupe de prise d’appel doivent être des extensions virtuelles auxquelles aucun utilisateur ou téléphone n’est affecté.</span><span class="sxs-lookup"><span data-stu-id="82a5c-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="82a5c-108">Chaque pool frontal où vous déployez la prise d’appel de groupe peut avoir une ou plusieurs plages de numéros de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="82a5c-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="82a5c-109">Les plages de numéros de groupe doivent être uniques au niveau global dans le déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82a5c-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="82a5c-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="82a5c-110">In This Section</span></span>

[<span data-ttu-id="82a5c-111">Création ou modification d’une plage de numéros de prise d’appel de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82a5c-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

