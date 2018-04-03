---
title: Comment dois-je entrer les numéros de téléphone ?
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
description: 'Apprenez à configurer des numéros de téléphone lorsque vous les porter à Skype pour les entreprises. '
ms.openlocfilehash: 68fe698612c095e657dab56723df7de6eb13b858
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="how-should-i-enter-the-phone-numbers"></a>Comment dois-je entrer les numéros de téléphone ?

Lorsque vous procédez au portage des numéros de téléphone, vous devez les entrer dans le format correct. 
  
> [!NOTE]
> Chaque numéro de téléphone ou d’une plage de numéro de téléphone doit être entrée séparément sur chaque ligne. 
  
- Lorsque vous entrez des numéros de téléphone unique :
    
  - Tous les caractères spéciaux seront ignorées (y compris le tiret «- »). Par exemple :
    
  - Pour un numéro à 10 chiffres : ** &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649** sera corrigé pour **+14255550649**.
    
  - Pour un numéro à 11 chiffres : **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** sera corrigé pour **+14255550649**.
    
  - Toutes les balises seront ignorés s’il y a 10 ou 11 chiffres. Par exemple, ** \<div > 4255551234\</div >** sera **+ 14255551234**.
    
  - «- », l’espace et une parenthèse seront ignoré. Par exemple :
    
  - Pour un numéro à 10 chiffres : **(425) 555-6776** sera corrigé pour **+14255556776**.
    
  - Pour un numéro à 11 chiffres : **1(425) 555-6776** sera corrigé pour **+14255556776**.
    
  - Toutes les lettres seront traités comme des caractères spéciaux et ignorées s’il existe un numéro de téléphone à 10 ou 11 chiffres. Par exemple :
    
  - Pour un numéro à 10 chiffres : **14jaosia2reoij05jof55506ajfoj49isdjf** sera corrigé pour **+14255550649**.
    
  - Pour un numéro à 11 chiffres : **1ade4jaoda2rfoij05ojof55506dsfoj49if** sera corrigé pour **+14255550649**.
    
  - N’importe quelle combinaison de caractères spéciaux, même dans d’autres langues est corrigée. Par exemple : 
    
  - Pour un numéro à 10 chiffres :**中文4中文2ajj5\*() (\*(5()... 551345** sera corrigé pour **+14555551345**.
    
  - Pour un numéro à 11 chiffres :**中文4中文2$ a5\*() (\*(5()... 55 (.1345** sera corrigé pour **+14555551345**.
    
  - Si les numéros contiennent moins de 10 ou plus de 11 chiffres, ils sont mis en surbrillance à l’utilisateur de corriger :
    
  - \*\*5551245\* \* est mise en surbrillance et doivent être corrigées.
    
  - **1234567891011** est mis en surbrillance et doivent être corrigées.
    
  - Les numéros sont les moins de 10 ou plus de 11 chiffres, avec des caractères spéciaux, seront mise en surbrillance sans être corrigé automatiquement.
    
  - Un nombre à 7 chiffres sans caractères spéciaux est entré : **123456abcdefg7** est mis en surbrillance et doivent être corrigées, mais les lettres ne soient pas ignorées.
    
  - Pour un nombre à 7 chiffres avec des caractères spéciaux qui est entré : **12345!@#$%^&amp;\*() : @# $% ^&amp;\*() 7** est mise en surbrillance pour être corrigée. Les caractères spéciaux ne sont pas être ignorés.
    
- Lorsque vous entrez une plage de numéros de téléphone.
    
  - Seuls deux numéros de téléphone sont autorisées. Le plus petit nombre doit être le premier nombre dans la plage.
    
  - Tous les caractères spéciaux (à l’exception du tiret «- ») sont traitées comme des nombres unique. Par exemple, **(425) 555 0&amp;\*(123-(1425) 5557899nm** sera corrigé pour **+14255550123 - +13202040659**.
    
  - Le «- » est utilisé pour séparer les deux nombres uniquement. Il n’est pas pris en charge pour inclure plusieurs «- » dans la plage de numéros. Par exemple, **(425) 555-0649-(425) 555-1115** doit être indiqué en tant que **(425) 5551115 5550649 - (425)**.
    
 **Pour des instructions complètes, voir [transfert vers Office 365, les numéros de téléphone](transfer-phone-numbers-to-office-365.md).**

 > [!NOTE]
> Si vous devez obtenir davantage de numéros de téléphone, veuillez [contacter le support pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

  
## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](transferring-phone-numbers-common-questions.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer des numéros de téléphone pour votre entreprise](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 