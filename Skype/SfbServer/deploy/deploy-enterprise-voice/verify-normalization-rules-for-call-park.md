---
title: Vérification des règles de normalisation du parcage d’appel dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Découvrez les règles de normalisation de parcage d’appel dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: c637240d4c193bbec05228d167d77f7bd18c0d04
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a><span data-ttu-id="9515f-103">Vérification des règles de normalisation du parcage d’appel dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="9515f-103">Verify normalization rules for Call Park in Skype for Business 2015</span></span>
 
<span data-ttu-id="9515f-104">Découvrez les règles de normalisation de parcage d’appel dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9515f-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="9515f-105">Orbites de parcage d’appel ne doivent pas être normalisées.</span><span class="sxs-lookup"><span data-stu-id="9515f-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="9515f-106">Vérifiez dans vos plans de numérotation que vos numéros orbites ne sont pas normalisés.</span><span class="sxs-lookup"><span data-stu-id="9515f-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="9515f-107">Si vous devez créer une règle de normalisation supplémentaire pour empêcher que votre orbites en cours de normalisation, suivez la procédure décrite dans [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](dial-plans.md) pour définir une nouvelle règle de normalisation, donc ce **modèle pour la correspondance** identifie la plage d’orbites et **modèle de traduction** est **$1**.</span><span class="sxs-lookup"><span data-stu-id="9515f-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server 2015](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="9515f-108">Par exemple, si votre plage d’orbites de parcage d’appel est 7999-7000, le **modèle pour la correspondance** est **^(7\d{3})$** et **modèle de traduction** est **$1**.</span><span class="sxs-lookup"><span data-stu-id="9515f-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9515f-109">N’oubliez pas que la règle de normalisation par défaut dans vos plans de numérotation ne contient pas **^(\d\*)**.</span><span class="sxs-lookup"><span data-stu-id="9515f-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="9515f-110">Dans le cas contraire, votre règle de normalisation de parcage d’appel ne s’exécutera jamais.</span><span class="sxs-lookup"><span data-stu-id="9515f-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9515f-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9515f-111">See also</span></span>

#### 

[<span data-ttu-id="9515f-112">Créer ou modifier un plan de numérotation dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9515f-112">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)

