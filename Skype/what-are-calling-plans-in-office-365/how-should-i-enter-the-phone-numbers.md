---
title: "Comment dois-je entrer les numéros de téléphone ?"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: "Apprenez à configurer des numéros de téléphone lorsque vous les porter à Skype pour les entreprises. "
ms.openlocfilehash: c68a42838021c9f8a564b55dbac078af07d9031b
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="b6c3c-103">Comment dois-je entrer les numéros de téléphone ?</span><span class="sxs-lookup"><span data-stu-id="b6c3c-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="b6c3c-104">Lorsque vous procédez au portage des numéros de téléphone, vous devez les entrer dans le format correct.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b6c3c-105">Chaque numéro de téléphone ou d’une plage de numéro de téléphone doit être entrée séparément sur chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="b6c3c-106">Lorsque vous entrez des numéros de téléphone unique :</span><span class="sxs-lookup"><span data-stu-id="b6c3c-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="b6c3c-107">Tous les caractères spéciaux seront ignorées (y compris le tiret «- »).</span><span class="sxs-lookup"><span data-stu-id="b6c3c-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="b6c3c-108">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b6c3c-108">For example:</span></span>
    
  - <span data-ttu-id="b6c3c-109">Pour un numéro à 10 chiffres : \*\* &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649\*\* sera corrigé pour **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="b6c3c-110">Pour un numéro à 11 chiffres : **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** sera corrigé pour **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="b6c3c-111">Toutes les balises seront ignorés s’il y a 10 ou 11 chiffres.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="b6c3c-112">Par exemple, ** \<div > 4255551234\</div >** sera **+ 14255551234**.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="b6c3c-113">«- », l’espace et une parenthèse seront ignoré.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="b6c3c-114">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b6c3c-114">For example:</span></span>
    
  - <span data-ttu-id="b6c3c-115">Pour un numéro à 10 chiffres : **(425) 555-6776** sera corrigé pour **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="b6c3c-116">Pour un numéro à 11 chiffres : **1(425) 555-6776** sera corrigé pour **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="b6c3c-117">Toutes les lettres seront traités comme des caractères spéciaux et ignorées s’il existe un numéro de téléphone à 10 ou 11 chiffres.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="b6c3c-118">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b6c3c-118">For example:</span></span>
    
  - <span data-ttu-id="b6c3c-119">Pour un numéro à 10 chiffres : **14jaosia2reoij05jof55506ajfoj49isdjf** sera corrigé pour **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="b6c3c-120">Pour un numéro à 11 chiffres : **1ade4jaoda2rfoij05ojof55506dsfoj49if** sera corrigé pour **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="b6c3c-121">N’importe quelle combinaison de caractères spéciaux, même dans d’autres langues est corrigée.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="b6c3c-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b6c3c-122">For example:</span></span> 
    
  - <span data-ttu-id="b6c3c-123">Pour un numéro à 10 chiffres :**中文4中文2ajj5\*() (\*(5()... 551345** sera corrigé pour **+14555551345**.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="b6c3c-124">Pour un numéro à 11 chiffres :**中文4中文2$ a5\*() (\*(5()... 55 (.1345** sera corrigé pour **+14555551345**.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="b6c3c-125">Si les numéros contiennent moins de 10 ou plus de 11 chiffres, ils sont mis en surbrillance à l’utilisateur de corriger :</span><span class="sxs-lookup"><span data-stu-id="b6c3c-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="b6c3c-126">\*\*5551245\* \* est mise en surbrillance et doivent être corrigées.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="b6c3c-127">**1234567891011** est mis en surbrillance et doivent être corrigées.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="b6c3c-128">Les numéros sont les moins de 10 ou plus de 11 chiffres, avec des caractères spéciaux, seront mise en surbrillance sans être corrigé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="b6c3c-129">Un nombre à 7 chiffres sans caractères spéciaux est entré : **123456abcdefg7** est mis en surbrillance et doivent être corrigées, mais les lettres ne soient pas ignorées.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="b6c3c-130">Pour un nombre à 7 chiffres avec des caractères spéciaux qui est entré : **12345!@#$%^&amp;\*() : @# $% ^&amp;\*() 7** est mise en surbrillance pour être corrigée.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="b6c3c-131">Les caractères spéciaux ne sont pas être ignorés.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="b6c3c-132">Lorsque vous entrez une plage de numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="b6c3c-133">Seuls deux numéros de téléphone sont autorisées.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="b6c3c-134">Le plus petit nombre doit être le premier nombre dans la plage.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="b6c3c-135">Tous les caractères spéciaux (à l’exception du tiret «- ») sont traitées comme des nombres unique.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="b6c3c-136">Par exemple, **(425) 555 0&amp;\*(123-(1425) 5557899nm** sera corrigé pour **+14255550123 - +13202040659**.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="b6c3c-137">Le «- » est utilisé pour séparer les deux nombres uniquement.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="b6c3c-138">Il n’est pas pris en charge pour inclure plusieurs «- » dans la plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="b6c3c-139">Par exemple, **(425) 555-0649-(425) 555-1115** doit être indiqué en tant que **(425) 5551115 5550649 - (425)**.</span><span class="sxs-lookup"><span data-stu-id="b6c3c-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
 <span data-ttu-id="b6c3c-140">**Pour des instructions complètes, voir [transfert vers Office 365, les numéros de téléphone](transfer-phone-numbers-to-office-365.md).**</span><span class="sxs-lookup"><span data-stu-id="b6c3c-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).**</span></span>

 > [!NOTE]
> <span data-ttu-id="b6c3c-141">Si vous devez obtenir davantage de numéros de téléphone, veuillez [contacter le support pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="b6c3c-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="b6c3c-142">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="b6c3c-142">Related topics</span></span>
[<span data-ttu-id="b6c3c-143">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="b6c3c-143">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="b6c3c-144">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="b6c3c-144">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="b6c3c-145">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="b6c3c-145">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="b6c3c-146">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="b6c3c-146">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="b6c3c-147">Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="b6c3c-147">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)