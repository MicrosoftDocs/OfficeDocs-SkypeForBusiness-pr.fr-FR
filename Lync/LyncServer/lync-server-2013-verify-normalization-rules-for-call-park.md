---
title: 'Lync Server 2013 : vérifier les règles de normalisation du parc d’appels'
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
ms.openlocfilehash: 2041b807ad16f1e91a83da39739d0ea058a5fba5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="28d80-102">Vérifier les règles de normalisation du parc d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28d80-102">Verify normalization rules for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28d80-103">_**Dernière modification de la rubrique :** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="28d80-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="28d80-104">Le parking des orbites ne doit pas être normalisé.</span><span class="sxs-lookup"><span data-stu-id="28d80-104">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="28d80-105">Vérifiez dans vos plans de numérotation que vos numéros orbites ne sont pas normalisés.</span><span class="sxs-lookup"><span data-stu-id="28d80-105">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="28d80-106">Si vous devez créer une règle de normalisation supplémentaire pour empêcher la normalisation de vos orbites, suivez la procédure décrite dans la rubrique [créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md) pour définir une nouvelle règle de normalisation, afin que le **modèle correspondant** identifie la plage d’orbite et le **modèle de traduction** est **$1**.</span><span class="sxs-lookup"><span data-stu-id="28d80-106">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="28d80-107">Par exemple, si la plage de votre stationnement d’appels est 7000 – 7999, le **modèle à faire correspondre** est **\\^{3}(7 d) $** et le **modèle de traduction** est **$1**.</span><span class="sxs-lookup"><span data-stu-id="28d80-107">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="28d80-108">Vérifiez que la règle de normalisation par défaut de vos plans de numérotation ne contient pas l’élément <STRONG>^(\d\*)</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="28d80-108">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="28d80-109">Dans le cas contraire, votre règle de normalisation de parc d’appels ne sera jamais exécutée.</span><span class="sxs-lookup"><span data-stu-id="28d80-109">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="28d80-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28d80-110">See Also</span></span>


[<span data-ttu-id="28d80-111">Créer un plan de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28d80-111">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

