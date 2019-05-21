---
title: Comment dois-je entrer les numéros de téléphone ?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Découvrez comment configurer les numéros de téléphone lorsque vous les transférez vers Skype entreprise. '
ms.openlocfilehash: df9d82a6e785954a95a455f0e43aa0e077f40bcf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280529"
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="a4a07-103">Comment dois-je entrer les numéros de téléphone ?</span><span class="sxs-lookup"><span data-stu-id="a4a07-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="a4a07-104">Lorsque vous transférez des numéros de téléphone, vous devez les entrer au bon format.</span><span class="sxs-lookup"><span data-stu-id="a4a07-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a4a07-105">Chaque numéro de téléphone ou plage de numéros de téléphone doit être entré séparément sur chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="a4a07-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="a4a07-106">Lorsque vous entrez des numéros de téléphone uniques:</span><span class="sxs-lookup"><span data-stu-id="a4a07-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="a4a07-107">Tous les caractères spéciaux seront ignorés (y compris les tirets «-»).</span><span class="sxs-lookup"><span data-stu-id="a4a07-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="a4a07-108">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a4a07-108">For example:</span></span>
    
  - <span data-ttu-id="a4a07-109">Pour un numéro à 10 chiffres: \*\* &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649\*\* sera corrigé comme suit: **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="a4a07-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="a4a07-110">Pour un numéro à 11 chiffres: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** sera corrigé comme suit: **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="a4a07-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="a4a07-111">Toutes les indicateurs seront ignorés s’il existe 10 ou 11 chiffres.</span><span class="sxs-lookup"><span data-stu-id="a4a07-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="a4a07-112">Par exemple, \*\* \<div> 4255551234\</div>\*\* sera **+ 14255551234**.</span><span class="sxs-lookup"><span data-stu-id="a4a07-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="a4a07-113">«-», l’espace et les parenthèses seront ignorés.</span><span class="sxs-lookup"><span data-stu-id="a4a07-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="a4a07-114">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a4a07-114">For example:</span></span>
    
  - <span data-ttu-id="a4a07-115">Pour un numéro à 10 chiffres: **(425) 555-6776** sera corrigé comme suit: **+ 14255556776**.</span><span class="sxs-lookup"><span data-stu-id="a4a07-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="a4a07-116">Pour un numéro à 11 chiffres: **1 (425) 555-6776** est corrigé comme suit: **+ 14255556776**.</span><span class="sxs-lookup"><span data-stu-id="a4a07-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="a4a07-117">Toutes les lettres seront considérées comme des caractères spéciaux et ignorées s’il existe un numéro de téléphone à 10 chiffres ou 11 chiffres.</span><span class="sxs-lookup"><span data-stu-id="a4a07-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="a4a07-118">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a4a07-118">For example:</span></span>
    
  - <span data-ttu-id="a4a07-119">Pour un numéro à 10 chiffres: **14jaosia2reoij05jof55506ajfoj49isdjf** est corrigé comme suit: **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="a4a07-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="a4a07-120">Pour un numéro à 11 chiffres: **1ade4jaoda2rfoij05ojof55506dsfoj49if** est corrigé comme suit: **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="a4a07-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="a4a07-121">Toute combinaison de caractères spéciaux, même dans d’autres langues, sera corrigée.</span><span class="sxs-lookup"><span data-stu-id="a4a07-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="a4a07-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a4a07-122">For example:</span></span> 
    
  - <span data-ttu-id="a4a07-123">Pour un numéro à 10 chiffres:**中文 4 中文2ajj5\*() (\*(5 ()... 551345** sera corrigé comme étant de **+ 14555551345**.</span><span class="sxs-lookup"><span data-stu-id="a4a07-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="a4a07-124">Pour un numéro à 11 chiffres:**中文 4 中文 2 $ a5\*() (\*(5 ()... 55 (. 1345** sera corrigé comme étant de **+ 14555551345**.</span><span class="sxs-lookup"><span data-stu-id="a4a07-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="a4a07-125">Si les nombres comportent moins de 10 chiffres ou plus de 11 chiffres, ils sont mis en surbrillance pour que l’utilisateur les corrige:</span><span class="sxs-lookup"><span data-stu-id="a4a07-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="a4a07-126">\*\*5551245\* \* est mis en surbrillance et doit être corrigé.</span><span class="sxs-lookup"><span data-stu-id="a4a07-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="a4a07-127">**1234567891011** est mis en surbrillance et doit être corrigé.</span><span class="sxs-lookup"><span data-stu-id="a4a07-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="a4a07-128">Tout nombre comportant moins de 10 chiffres ou plus de 11 chiffres, avec des caractères spéciaux, est mis en surbrillance sans être corrigé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="a4a07-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="a4a07-129">Pour un numéro à 7 chiffres sans caractère spécial qui est entré: **123456abcdefg7** est mis en surbrillance et doit être corrigé, mais les lettres ne sont pas ignorées.</span><span class="sxs-lookup"><span data-stu-id="a4a07-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="a4a07-130">Pour un numéro à 7 chiffres avec des caractères spéciaux qui est entré **: 12345! @ # $%&amp;\*^ ()--@ # $%&amp;\*^ () 7** est mis en surbrillance pour être corrigé.</span><span class="sxs-lookup"><span data-stu-id="a4a07-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="a4a07-131">Les caractères spéciaux ne seront pas ignorés.</span><span class="sxs-lookup"><span data-stu-id="a4a07-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="a4a07-132">Lorsque vous entrez une plage de numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="a4a07-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="a4a07-133">Seuls deux numéros de téléphone sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="a4a07-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="a4a07-134">La valeur la plus petite doit être le premier nombre de la plage.</span><span class="sxs-lookup"><span data-stu-id="a4a07-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="a4a07-135">Les caractères spéciaux (à l’exception du tiret «-») sont traités comme des nombres uniques.</span><span class="sxs-lookup"><span data-stu-id="a4a07-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="a4a07-136">Par exemple, **(425) 555 0&amp;\*(123-(1425) 5557899nm** sera corrigé comme **+ 14255550123-+ 13202040659**.</span><span class="sxs-lookup"><span data-stu-id="a4a07-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="a4a07-137">Le «-» est utilisé pour séparer uniquement les deux nombres.</span><span class="sxs-lookup"><span data-stu-id="a4a07-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="a4a07-138">Il n’est pas possible d’inclure plusieurs «-» dans la plage de nombres.</span><span class="sxs-lookup"><span data-stu-id="a4a07-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="a4a07-139">Par exemple, **(425) 555-0649-(425) 555-1115** doit être entré en tant que **(425) 5550649-(425) 5551115**.</span><span class="sxs-lookup"><span data-stu-id="a4a07-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
  <span data-ttu-id="a4a07-140">**Pour obtenir des instructions complètes détaillées, consultez la rubrique [transférer des numéros de téléphone vers Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span><span class="sxs-lookup"><span data-stu-id="a4a07-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span></span>

  > [!NOTE]
  > <span data-ttu-id="a4a07-141">Si vous devez obtenir davantage de numéros de téléphone, veuillez [contacter le support pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="a4a07-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="a4a07-142">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="a4a07-142">Related topics</span></span>
[<span data-ttu-id="a4a07-143">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="a4a07-143">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="a4a07-144">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="a4a07-144">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="a4a07-145">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="a4a07-145">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="a4a07-146">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="a4a07-146">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="a4a07-147">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="a4a07-147">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 