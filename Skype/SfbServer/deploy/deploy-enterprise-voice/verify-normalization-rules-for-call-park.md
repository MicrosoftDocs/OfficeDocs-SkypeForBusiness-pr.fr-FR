---
title: Vérifier les règles de normalisation pour le parcier d’appel dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: En savoir plus sur les règles de normalisation pour le parcier d’appel dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: d1bcd6817b1f59f73a8c4ef1562e90253a99bd30
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830574"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="26541-103">Vérifier les règles de normalisation pour le parcier d’appel dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="26541-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="26541-104">En savoir plus sur les règles de normalisation pour le parcier d’appel dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="26541-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="26541-105">Les orbites de parcier d’appel ne doivent pas être normalisées.</span><span class="sxs-lookup"><span data-stu-id="26541-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="26541-106">Vérifiez vos plans de numérotation pour vous assurer que vos numéros d’orbite ne sont pas normalisés.</span><span class="sxs-lookup"><span data-stu-id="26541-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="26541-107">Si vous devez créer une règle de normalisation supplémentaire pour empêcher la normalisation de vos orbites, suivez la procédure de création ou de modification d’un plan de numérotation dans Skype Entreprise [Server](dial-plans.md) pour définir une nouvelle règle de normalisation, afin que le modèle à suivre **identifie** la plage d’orbites et que le modèle de traduction soit **de 1 $**. </span><span class="sxs-lookup"><span data-stu-id="26541-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="26541-108">Par exemple, si votre plage d’orbites de parc automatique est  de 7 000 à  7 999, le modèle à suivre est **^(7\d {3} )$** et le modèle de traduction est **de 1 $**.</span><span class="sxs-lookup"><span data-stu-id="26541-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="26541-109">Assurez-vous que la règle de normalisation par défaut dans vos plans de numérotation ne contient **pas ^(\d \* )**.</span><span class="sxs-lookup"><span data-stu-id="26541-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="26541-110">Dans le cas contraire, votre règle de normalisation du parc d’appel ne s’exécutera jamais.</span><span class="sxs-lookup"><span data-stu-id="26541-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="26541-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26541-111">See also</span></span>

[<span data-ttu-id="26541-112">Créer ou modifier un plan de numérotation dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="26541-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

