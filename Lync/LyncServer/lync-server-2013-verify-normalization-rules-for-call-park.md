---
title: 'Lync Server 2013 : vérifier les règles de normalisation pour le parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fcde0adac292b8773a81c759c72765f832ce745
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="e9ad2-102">Vérifier les règles de normalisation pour le parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9ad2-102">Verify normalization rules for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9ad2-103">_**Dernière modification de la rubrique :** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="e9ad2-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="e9ad2-104">Les orbites de parcage d’appel ne doivent pas être normalisées.</span><span class="sxs-lookup"><span data-stu-id="e9ad2-104">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="e9ad2-105">Vérifiez vos plans de numérotation pour vous assurer que les numéros d’orbite ne sont pas normalisés.</span><span class="sxs-lookup"><span data-stu-id="e9ad2-105">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="e9ad2-106">Si vous devez créer une règle de normalisation supplémentaire pour empêcher la normalisation de vos orbites, suivez la procédure décrite dans [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a New Normalization Rule, de sorte que le **modèle de correspondance** identifie la plage d’orbites et le **modèle de traduction** est **$1**.</span><span class="sxs-lookup"><span data-stu-id="e9ad2-106">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="e9ad2-107">Par exemple, si votre plage d’orbites de parcage d’appel est 7000 – 7999, le **modèle de correspondance** est **\\^ (7 d{3}) $** et le modèle de **traduction** est **$1**.</span><span class="sxs-lookup"><span data-stu-id="e9ad2-107">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e9ad2-108">Assurez-vous que la règle de normalisation par défaut de vos plans de numérotation ne contient pas <STRONG>^ (\d \*)</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e9ad2-108">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="e9ad2-109">Dans le cas contraire, votre règle de normalisation de parcage d’appel ne s’exécutera jamais.</span><span class="sxs-lookup"><span data-stu-id="e9ad2-109">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e9ad2-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e9ad2-110">See Also</span></span>


[<span data-ttu-id="e9ad2-111">Création d’un plan de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9ad2-111">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

