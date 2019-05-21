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
# <a name="how-should-i-enter-the-phone-numbers"></a>Comment dois-je entrer les numéros de téléphone ?

Lorsque vous transférez des numéros de téléphone, vous devez les entrer au bon format. 
  
> [!NOTE]
> Chaque numéro de téléphone ou plage de numéros de téléphone doit être entré séparément sur chaque ligne. 
  
- Lorsque vous entrez des numéros de téléphone uniques:
    
  - Tous les caractères spéciaux seront ignorés (y compris les tirets «-»). Par exemple :
    
  - Pour un numéro à 10 chiffres: ** &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649** sera corrigé comme suit: **+ 14255550649**.
    
  - Pour un numéro à 11 chiffres: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** sera corrigé comme suit: **+ 14255550649**.
    
  - Toutes les indicateurs seront ignorés s’il existe 10 ou 11 chiffres. Par exemple, ** \<div> 4255551234\</div>** sera **+ 14255551234**.
    
  - «-», l’espace et les parenthèses seront ignorés. Par exemple :
    
  - Pour un numéro à 10 chiffres: **(425) 555-6776** sera corrigé comme suit: **+ 14255556776**.
    
  - Pour un numéro à 11 chiffres: **1 (425) 555-6776** est corrigé comme suit: **+ 14255556776**.
    
  - Toutes les lettres seront considérées comme des caractères spéciaux et ignorées s’il existe un numéro de téléphone à 10 chiffres ou 11 chiffres. Par exemple :
    
  - Pour un numéro à 10 chiffres: **14jaosia2reoij05jof55506ajfoj49isdjf** est corrigé comme suit: **+ 14255550649**.
    
  - Pour un numéro à 11 chiffres: **1ade4jaoda2rfoij05ojof55506dsfoj49if** est corrigé comme suit: **+ 14255550649**.
    
  - Toute combinaison de caractères spéciaux, même dans d’autres langues, sera corrigée. Par exemple : 
    
  - Pour un numéro à 10 chiffres:**中文 4 中文2ajj5\*() (\*(5 ()... 551345** sera corrigé comme étant de **+ 14555551345**.
    
  - Pour un numéro à 11 chiffres:**中文 4 中文 2 $ a5\*() (\*(5 ()... 55 (. 1345** sera corrigé comme étant de **+ 14555551345**.
    
  - Si les nombres comportent moins de 10 chiffres ou plus de 11 chiffres, ils sont mis en surbrillance pour que l’utilisateur les corrige:
    
  - \*\*5551245\* \* est mis en surbrillance et doit être corrigé.
    
  - **1234567891011** est mis en surbrillance et doit être corrigé.
    
  - Tout nombre comportant moins de 10 chiffres ou plus de 11 chiffres, avec des caractères spéciaux, est mis en surbrillance sans être corrigé automatiquement.
    
  - Pour un numéro à 7 chiffres sans caractère spécial qui est entré: **123456abcdefg7** est mis en surbrillance et doit être corrigé, mais les lettres ne sont pas ignorées.
    
  - Pour un numéro à 7 chiffres avec des caractères spéciaux qui est entré **: 12345! @ # $%&amp;\*^ ()--@ # $%&amp;\*^ () 7** est mis en surbrillance pour être corrigé. Les caractères spéciaux ne seront pas ignorés.
    
- Lorsque vous entrez une plage de numéros de téléphone.
    
  - Seuls deux numéros de téléphone sont autorisés. La valeur la plus petite doit être le premier nombre de la plage.
    
  - Les caractères spéciaux (à l’exception du tiret «-») sont traités comme des nombres uniques. Par exemple, **(425) 555 0&amp;\*(123-(1425) 5557899nm** sera corrigé comme **+ 14255550123-+ 13202040659**.
    
  - Le «-» est utilisé pour séparer uniquement les deux nombres. Il n’est pas possible d’inclure plusieurs «-» dans la plage de nombres. Par exemple, **(425) 555-0649-(425) 555-1115** doit être entré en tant que **(425) 5550649-(425) 5551115**.
    
  **Pour obtenir des instructions complètes détaillées, consultez la rubrique [transférer des numéros de téléphone vers Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**

  > [!NOTE]
  > Si vous devez obtenir davantage de numéros de téléphone, veuillez [contacter le support pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

  
## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](/microsoftteams/transferring-phone-numbers-common-questions)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 