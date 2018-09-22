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
# <a name="how-should-i-enter-the-phone-numbers"></a>Comment dois-je entrer les numéros de téléphone ?

Lorsque vous procédez au portage numéros de téléphone, vous devez les entrer dans le bon format. 
  
> [!NOTE]
> Chaque numéro de téléphone ou la plage de numéro de téléphone doit être saisie séparément sur chaque ligne. 
  
- Lorsque vous entrez des numéros de téléphone unique :
    
  - Tous les caractères spéciaux doit être ignorées (y compris le tiret «- »). Par exemple :
    
  - Pour un nombre à 10 chiffres : ** &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649** sera corrigé pour **+14255550649**.
    
  - Pour un numéro à 11 chiffres : **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** sera corrigé pour **+14255550649**.
    
  - Toutes les balises seront ignorées s’il y a 10 ou 11 chiffres. Par exemple, ** \<div > 4255551234\</div >** sera **+ 14255551234**.
    
  - «- », l’espace et une parenthèse seront ignorée. Par exemple :
    
  - Pour un nombre à 10 chiffres : **(425) 555-6776** sera corrigé pour **+14255556776**.
    
  - Pour un numéro à 11 chiffres : **555-6776 1(425)** sera corrigé pour **+14255556776**.
    
  - Toutes les lettres sont alors être considérés comme des caractères spéciaux et ignorés s’il existe un numéro de téléphone à 10 ou 11 chiffres. Par exemple :
    
  - Pour un nombre à 10 chiffres : **14jaosia2reoij05jof55506ajfoj49isdjf** sera corrigé pour **+14255550649**.
    
  - Pour un numéro à 11 chiffres : **1ade4jaoda2rfoij05ojof55506dsfoj49if** sera corrigé pour **+14255550649**.
    
  - N’importe quelle combinaison de caractères spéciaux, même dans d’autres langues, sera corrigé. Par exemple : 
    
  - Pour un nombre à 10 chiffres :**中文4中文2ajj5\*() (\*(5()... 551345** sera corrigé pour **+14555551345**.
    
  - Pour un numéro à 11 chiffres :**中文4中文2$ a5\*() (\*(5()... 55 (.1345** sera corrigé pour **+14555551345**.
    
  - Si les numéros contient moins de 10 ou plus de 11 chiffres, ils sont mis en surbrillance de l’utilisateur de manière à corriger :
    
  - \*\*5551245\* \* est mis en surbrillance et doivent être corrigées.
    
  - **1234567891011** est mis en surbrillance et doivent être corrigées.
    
  - Les numéros sont moins de 10 ou plus de 11 chiffres, avec des caractères spéciaux seront mis en surbrillance sans être corrigées automatiquement.
    
  - Pour un nombre à 7 chiffres sans caractères spéciaux qui est atteint : **123456abcdefg7** est mis en surbrillance et doivent être corrigées, mais les lettres ne soient pas ignorées.
    
  - Pour un nombre à 7 chiffres avec des caractères spéciaux qui est atteint : **12345!@#$%^&amp;\*()--@# $% ^&amp;\*() 7** est mise en surbrillance pour être corrigées. Les caractères spéciaux ne sont pas être ignorées.
    
- Lorsque vous entrez une plage de numéros de téléphone.
    
  - Seules deux numéros de téléphone sont autorisées. Le plus petit nombre doit être le premier nombre dans la plage.
    
  - Tous les caractères spéciaux (à l’exception du tiret «- ») sont traitées comme des numéros uniques. Par exemple, **(425) 555 0&amp;\*(123-(1425) 5557899nm** sera corrigé pour **+ 14255550123 - +13202040659**.
    
  - Le «- » est utilisé pour uniquement en séparant les deux nombres. Il n’est pas pris en charge pour inclure plusieurs «- » dans la plage de numéros. Par exemple, **(425) 555-0649-(425) 555-1115** doit être saisie comme **(425) 5550649 - (425) 5551115**.
    
 **Pour obtenir des instructions complètes, voir [transférer des numéros de téléphone vers Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**

 > [!NOTE]
> Si vous devez obtenir davantage de numéros de téléphone, veuillez [contacter le support pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

  
## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](/microsoftteams/transferring-phone-numbers-common-questions)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 