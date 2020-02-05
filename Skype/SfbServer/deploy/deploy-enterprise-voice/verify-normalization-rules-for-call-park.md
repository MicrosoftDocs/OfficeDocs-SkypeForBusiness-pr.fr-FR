---
title: Vérifier les règles de normalisation du parc d’appels dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: En savoir plus sur les règles de normalisation du parc d’appels dans Skype entreprise Server Voice.
ms.openlocfilehash: 769d9f9becccf4df24a33a11e8814350cfb091e8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766887"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="b9e0d-103">Vérifier les règles de normalisation du parc d’appels dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="b9e0d-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="b9e0d-104">En savoir plus sur les règles de normalisation du parc d’appels dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="b9e0d-105">Le parking des orbites ne doit pas être normalisé.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="b9e0d-106">Vérifiez dans vos plans de numérotation que vos numéros orbites ne sont pas normalisés.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="b9e0d-107">Si vous devez créer une règle de normalisation supplémentaire pour empêcher la normalisation de vos orbites, suivez la procédure décrite dans la rubrique [créer ou modifier un plan de numérotation dans Skype entreprise Server](dial-plans.md) pour définir une nouvelle règle de normalisation, de sorte que le **modèle à faire correspondre** identifie la plage d’orbite et le **modèle de translation** est **$1**.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="b9e0d-108">Par exemple, si la plage de votre stationnement d’appels est 7000-7999, le **modèle à faire correspondre** est **^ ({3}7 \ d) $** et le **modèle de traduction** est **$1**.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b9e0d-109">Vérifiez que la règle de normalisation par défaut de vos plans de numérotation ne contient pas **^\*(\d)**.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="b9e0d-110">Dans le cas contraire, votre règle de normalisation de parc d’appels ne sera jamais exécutée.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b9e0d-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9e0d-111">See also</span></span>

[<span data-ttu-id="b9e0d-112">Création ou modification d’un plan de numérotation dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b9e0d-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

