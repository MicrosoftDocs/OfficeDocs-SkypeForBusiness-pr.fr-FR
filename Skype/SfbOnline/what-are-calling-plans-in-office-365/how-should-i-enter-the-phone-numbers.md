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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Découvrez comment configurer des numéros de téléphone lorsque vous les au port Skype pour les entreprises. '
ms.openlocfilehash: 8d214ea7cf21ea713de28763f36b9995160fb395
ms.sourcegitcommit: c5940ef2674a00281604045baf8b2a320c4b189d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2018
ms.locfileid: "24958140"
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="51e42-103">Comment dois-je entrer les numéros de téléphone ?</span><span class="sxs-lookup"><span data-stu-id="51e42-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="51e42-104">Lorsque vous procédez au portage numéros de téléphone, vous devez les entrer dans le bon format.</span><span class="sxs-lookup"><span data-stu-id="51e42-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="51e42-105">Chaque numéro de téléphone ou la plage de numéro de téléphone doit être saisie séparément sur chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="51e42-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="51e42-106">Lorsque vous entrez des numéros de téléphone unique :</span><span class="sxs-lookup"><span data-stu-id="51e42-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="51e42-107">Tous les caractères spéciaux doit être ignorées (y compris le tiret «- »).</span><span class="sxs-lookup"><span data-stu-id="51e42-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="51e42-108">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="51e42-108">For example:</span></span>
    
  - <span data-ttu-id="51e42-109">Pour un nombre à 10 chiffres : \*\* &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649\*\* sera corrigé pour **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="51e42-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="51e42-110">Pour un numéro à 11 chiffres : **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** sera corrigé pour **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="51e42-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="51e42-111">Toutes les balises seront ignorées s’il y a 10 ou 11 chiffres.</span><span class="sxs-lookup"><span data-stu-id="51e42-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="51e42-112">Par exemple, \*\* \<div > 4255551234\</div >\*\* sera **+ 14255551234**.</span><span class="sxs-lookup"><span data-stu-id="51e42-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="51e42-113">«- », l’espace et une parenthèse seront ignorée.</span><span class="sxs-lookup"><span data-stu-id="51e42-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="51e42-114">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="51e42-114">For example:</span></span>
    
  - <span data-ttu-id="51e42-115">Pour un nombre à 10 chiffres : **(425) 555-6776** sera corrigé pour **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="51e42-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="51e42-116">Pour un numéro à 11 chiffres : **555-6776 1(425)** sera corrigé pour **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="51e42-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="51e42-117">Toutes les lettres sont alors être considérés comme des caractères spéciaux et ignorés s’il existe un numéro de téléphone à 10 ou 11 chiffres.</span><span class="sxs-lookup"><span data-stu-id="51e42-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="51e42-118">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="51e42-118">For example:</span></span>
    
  - <span data-ttu-id="51e42-119">Pour un nombre à 10 chiffres : **14jaosia2reoij05jof55506ajfoj49isdjf** sera corrigé pour **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="51e42-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="51e42-120">Pour un numéro à 11 chiffres : **1ade4jaoda2rfoij05ojof55506dsfoj49if** sera corrigé pour **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="51e42-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="51e42-121">N’importe quelle combinaison de caractères spéciaux, même dans d’autres langues, sera corrigé.</span><span class="sxs-lookup"><span data-stu-id="51e42-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="51e42-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="51e42-122">For example:</span></span> 
    
  - <span data-ttu-id="51e42-123">Pour un nombre à 10 chiffres :**中文4中文2ajj5\*() (\*(5()... 551345** sera corrigé pour **+14555551345**.</span><span class="sxs-lookup"><span data-stu-id="51e42-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="51e42-124">Pour un numéro à 11 chiffres :**中文4中文2$ a5\*() (\*(5()... 55 (.1345** sera corrigé pour **+14555551345**.</span><span class="sxs-lookup"><span data-stu-id="51e42-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="51e42-125">Si les numéros contient moins de 10 ou plus de 11 chiffres, ils sont mis en surbrillance de l’utilisateur de manière à corriger :</span><span class="sxs-lookup"><span data-stu-id="51e42-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="51e42-126">\*\*5551245\* \* est mis en surbrillance et doivent être corrigées.</span><span class="sxs-lookup"><span data-stu-id="51e42-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="51e42-127">**1234567891011** est mis en surbrillance et doivent être corrigées.</span><span class="sxs-lookup"><span data-stu-id="51e42-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="51e42-128">Les numéros sont moins de 10 ou plus de 11 chiffres, avec des caractères spéciaux seront mis en surbrillance sans être corrigées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="51e42-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="51e42-129">Pour un nombre à 7 chiffres sans caractères spéciaux qui est atteint : **123456abcdefg7** est mis en surbrillance et doivent être corrigées, mais les lettres ne soient pas ignorées.</span><span class="sxs-lookup"><span data-stu-id="51e42-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="51e42-130">Pour un nombre à 7 chiffres avec des caractères spéciaux qui est atteint : **12345!@#$%^&amp;\*()--@# $% ^&amp;\*() 7** est mise en surbrillance pour être corrigées.</span><span class="sxs-lookup"><span data-stu-id="51e42-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="51e42-131">Les caractères spéciaux ne sont pas être ignorées.</span><span class="sxs-lookup"><span data-stu-id="51e42-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="51e42-132">Lorsque vous entrez une plage de numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="51e42-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="51e42-133">Seules deux numéros de téléphone sont autorisées.</span><span class="sxs-lookup"><span data-stu-id="51e42-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="51e42-134">Le plus petit nombre doit être le premier nombre dans la plage.</span><span class="sxs-lookup"><span data-stu-id="51e42-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="51e42-135">Tous les caractères spéciaux (à l’exception du tiret «- ») sont traitées comme des numéros uniques.</span><span class="sxs-lookup"><span data-stu-id="51e42-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="51e42-136">Par exemple, **(425) 555 0&amp;\*(123-(1425) 5557899nm** sera corrigé pour **+ 14255550123 - +13202040659**.</span><span class="sxs-lookup"><span data-stu-id="51e42-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="51e42-137">Le «- » est utilisé pour uniquement en séparant les deux nombres.</span><span class="sxs-lookup"><span data-stu-id="51e42-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="51e42-138">Il n’est pas pris en charge pour inclure plusieurs «- » dans la plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="51e42-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="51e42-139">Par exemple, **(425) 555-0649-(425) 555-1115** doit être saisie comme **(425) 5550649 - (425) 5551115**.</span><span class="sxs-lookup"><span data-stu-id="51e42-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
 <span data-ttu-id="51e42-140">**Pour obtenir des instructions complètes, voir [transférer des numéros de téléphone vers Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span><span class="sxs-lookup"><span data-stu-id="51e42-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span></span>

 > [!NOTE]
> <span data-ttu-id="51e42-141">Si vous devez obtenir davantage de numéros de téléphone, veuillez [contacter le support pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="51e42-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="51e42-142">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="51e42-142">Related topics</span></span>
[<span data-ttu-id="51e42-143">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="51e42-143">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="51e42-144">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="51e42-144">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="51e42-145">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="51e42-145">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="51e42-146">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="51e42-146">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="51e42-147">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="51e42-147">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 