---
title: "Comment entrer les numéros de téléphone ?"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/13/2017
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- ms.lync.lac.PortOrderNumbers
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
description: "Learn how to set up phone numbers when you port them to Skype for Business. "
---

# Comment entrer les numéros de téléphone ?

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](28aa24b4-8c81-4327-9752-989ea7540db2.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/28aa24b4-8c81-4327-9752-989ea7540db2). 
  
Lorsque vous porter des numéros de téléphone, vous devez les entrer dans le format correct.
  
> [!NOTE]
> Chaque numéro de téléphone ou plage de numéros de téléphone doit être entré(e) séparément sur chaque ligne. 
  
- Lorsque vous entrez des numéros de téléphone uniques :
    
  - Tous les caractères spéciaux sont ignorés (y compris le tiret « - »). Par exemple :
    
  - Pour un numéro à 10 chiffres : **&amp;*(425*()(*&amp;4&amp;*())(*250649** est corrigé comme suit : **+14255550649**.
    
  - Pour un numéro à 11 chiffres : **1*()(*&amp;42&amp;*()(*&amp;55550649** est corrigé comme suit : **+14255550649**.
    
  - Toutes les balises sont ignorées si le numéro comporte 10 ou 11 chiffres. Par exemple, **<div> 4255551234</div>** devient **+14255551234**.
    
  - Le signe « - », les espaces et les parenthèses sont ignorés. Par exemple :
    
  - Pour un numéro à 10 chiffres : **(425) 555-6776** est corrigé comme suit : **+14255556776**.
    
  - Pour un numéro à 11 chiffres : **1(425) 555-6776** est corrigé comme suit : **+14255556776**.
    
  - Toutes les lettres sont traités comme des caractères spéciaux et ignorées s'il existe un numéro de téléphone à 10 ou 11 chiffres. Par exemple :
    
  - Pour un numéro à 10 chiffres : **14jaosia2reoij05jof55506ajfoj49isdjf** est corrigé comme suit : **+14255550649**.
    
  - Pour un numéro à 11 chiffres : **1ade4jaoda2rfoij05ojof55506dsfoj49if** est corrigé comme suit : **+14255550649**.
    
  - Toutes les combinaisons de caractères spéciaux, même dans d'autres langues, sont corrigées. Par exemple : 
    
  - Pour un numéro à 10 chiffres : **中文4中文2ajj5*（）（*（5()...551345** est corrigé comme suit : **+14555551345**.
    
  - Pour un numéro à 11 chiffres : **中文4中文2$a5*（）（*（5()...55(.1345** est corrigé comme suit : **+14555551345**.
    
  - Si les nombres contiennent moins de 10 ou plus de 11 chiffres, ils sont mis en surbrillance pour l'utilisateur à corriger :
    
  - ** 5551245** est mis en surbrillance et doit être corrigé.
    
  - **1234567891011** est mis en surbrillance et doit être corrigé.
    
  - Les nombres qui sont moins de 10 ou plus de 11 chiffres, avec tous les caractères spéciaux, est mise en surbrillance sans en cours de correction automatique.
    
  - Pour un nombre de chiffres 7 sans caractères spéciaux est entré : **123456abcdefg7** est mise en surbrillance et que vous devez être corrigée, mais les lettres ne soient pas ignorées.
    
  - Pour un nombre de chiffres 7 avec des caractères spéciaux est entré : **12345!@#$%^ &amp; * ()--@# $% ^ &amp; * (7)** est mise en surbrillance pour être corrigé. Les caractères spéciaux ne soient pas ignorées.
    
- Lorsque vous entrez une plage de numéros de téléphone :
    
  - Seuls deux numéros de téléphone sont autorisés. Le numéro de téléphone le plus court doit être le premier numéro dans la plage.
    
  - Tous les caractères spéciaux (à l'exception du tiret «- ») sont traitées comme nombres unique. Par exemple, **(425) 555 0 &amp; * (123-(1425) 5557899nm** sera corrigé à **+14255550123 - +13202040659**.
    
  - Le «- » est utilisé pour séparer uniquement les deux nombres. Il n'est pas pris en charge pour inclure plusieurs «- » dans la plage de nombres. Par exemple :, **(425) 555-0649-(425) 555-1115** doit être entrée sous forme **(425) 5550649 - (425) 5551115**.
    
 **Pour obtenir des instructions étape par étape terminées, voir [Transférer des numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).**
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  
## Voir aussi
<a name="MT_Footer"> </a>

#### 

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)
  
[Période de sortant gratuit de audio conférence](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)

