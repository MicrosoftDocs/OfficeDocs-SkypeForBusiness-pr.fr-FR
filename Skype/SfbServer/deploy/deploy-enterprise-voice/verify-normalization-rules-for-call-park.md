---
title: Vérification des règles de normalisation du parcage d’appel dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Obtenir des informations sur les règles de normalisation pour le parc d’appel dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 4f3651394bbdb5556a83aa34739a86f8d06f1396
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a><span data-ttu-id="eff1e-103">Vérification des règles de normalisation du parcage d’appel dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="eff1e-103">Verify normalization rules for Call Park in Skype for Business 2015</span></span>
 
<span data-ttu-id="eff1e-104">Obtenir des informations sur les règles de normalisation pour le parc d’appel dans Skype pour Business Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="eff1e-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="eff1e-105">Orbites de parc d’appel ne doivent pas être normalisés.</span><span class="sxs-lookup"><span data-stu-id="eff1e-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="eff1e-106">Vérifiez dans vos plans de numérotation que vos numéros orbites ne sont pas normalisés.</span><span class="sxs-lookup"><span data-stu-id="eff1e-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="eff1e-107">Si vous devez créer une règle de normalisation supplémentaires pour éviter que votre orbites en cours de normalisation, suivez la procédure décrite dans [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](dial-plans.md) pour définir une nouvelle règle de normalisation, donc ce **modèle à faire correspondre** identifie la plage d’orbite et **modèle de traduction** est **$1**.</span><span class="sxs-lookup"><span data-stu-id="eff1e-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server 2015](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="eff1e-108">Par exemple, si votre plage d’orbite de parc d’appel est 7999-7000, le **modèle à faire correspondre** est **^ (7\d {3}) $** et **modèle de traduction** est **$1**.</span><span class="sxs-lookup"><span data-stu-id="eff1e-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="eff1e-109">N’oubliez pas que la règle de normalisation par défaut dans vos plans de numérotation ne contient-elle pas **^(\d\*)**.</span><span class="sxs-lookup"><span data-stu-id="eff1e-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="eff1e-110">Dans le cas contraire, votre règle de normalisation de parc d’appel ne s’exécutera jamais.</span><span class="sxs-lookup"><span data-stu-id="eff1e-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eff1e-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eff1e-111">See also</span></span>

#### 

[<span data-ttu-id="eff1e-112">Créer ou modifier un plan de numérotation dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="eff1e-112">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)

