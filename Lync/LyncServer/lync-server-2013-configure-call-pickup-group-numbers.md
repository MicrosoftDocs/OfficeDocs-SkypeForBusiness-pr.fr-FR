---
title: 'Lync Server 2013: configurer les numéros de groupe de capture d’appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure call pickup group numbers
ms:assetid: 5cc67f0b-d70d-446a-8db1-befda8671121
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945631(v=OCS.15)
ms:contentKeyID: 51541479
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd20374a0e2507ff656c547d55b70d31969d821
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-pickup-group-numbers-in-lync-server-2013"></a><span data-ttu-id="361ab-102">Configurer des numéros de groupe de capture d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="361ab-102">Configure call pickup group numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="361ab-103">_**Dernière modification de la rubrique:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="361ab-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="361ab-104">Le prélèvement d’appels de groupe est basé sur l’application de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="361ab-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="361ab-105">Lorsque vous déployez un appel de groupe, vous configurez la table d’orbite du parc d’appels avec des plages de numéros de téléphone désignés comme numéros de groupe de cueillette d’appel.</span><span class="sxs-lookup"><span data-stu-id="361ab-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="361ab-106">Ces numéros de groupe sont les numéros que les utilisateurs composent pour prendre des appels qui sonnent pour un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="361ab-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="361ab-107">Tout comme les numéros d’appels parqués, les numéros de groupe de prise d’appel doivent être des extensions virtuelles auxquelles aucun utilisateur ou téléphone n’est affecté.</span><span class="sxs-lookup"><span data-stu-id="361ab-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="361ab-108">Chaque pool frontal sur lequel vous déployez la capture d’appels de groupe peut avoir une ou plusieurs gammes de numéros de groupe de cueillette d’appel.</span><span class="sxs-lookup"><span data-stu-id="361ab-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="361ab-109">Les plages de numéros de groupe doivent être globalement uniques dans le déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="361ab-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="361ab-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="361ab-110">In This Section</span></span>

[<span data-ttu-id="361ab-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="361ab-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

