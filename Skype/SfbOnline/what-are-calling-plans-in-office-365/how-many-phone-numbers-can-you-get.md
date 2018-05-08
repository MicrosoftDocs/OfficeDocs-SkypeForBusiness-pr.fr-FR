---
title: Combien de numéros de téléphone vous pouvez obtenir ?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 61dfb27c-5bfa-4481-a930-9c026e73ff3a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: Lorsque vous recherchez et obtenez des numéros de téléphone pour votre organisation, vous pouvez obtenir plus de numéros de téléphone que de licences affectées. Cela dépend toutefois des types de numéros de téléphone que vous avez achetés et des types de licences que vous avez affectées. Vous pouvez cliquer sur les différents types de numéros de téléphone utilisés pour appeler des Plans pour connaître les numéros de téléphone différents qui sont utilisés dans Skype pour Business en ligne.
ms.openlocfilehash: 5267e22b76aa5a487db77d51cc601a97896b8478
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="how-many-phone-numbers-can-you-get"></a>Combien de numéros de téléphone vous pouvez obtenir ?

Lorsque vous recherchez et obtenez des numéros de téléphone pour votre organisation, vous pouvez obtenir plus de numéros de téléphone que de licences affectées. Cela dépend toutefois des types de numéros de téléphone que vous avez achetés et des types de licences que vous avez affectées. Vous pouvez cliquer sur les [différents types de numéros de téléphone utilisés pour appeler des Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md) pour connaître les numéros de téléphone différents qui sont utilisés dans Skype pour Business en ligne.
  
Vous pouvez voir le nombre de numéros de téléphone que vous pouvez obtenir dans la page de **numéros de téléphone** dans la Skype entreprise centre d’administration, ou vous pouvez exécuter l’applet de commande [Get-CsOnlineTelephoneNumberAvailableCount](https://technet.microsoft.com/en-us/library/mt634605.aspx) .
  
> [!IMPORTANT]
> Les limites ci-dessous n'incluent pas les numéros transférés vers Microsoft. 
  
## <a name="how-many-phone-numbers-you-can-get"></a>Combien de numéros de téléphone que vous pouvez obtenir ?

||||
|:-----|:-----|:-----|
|**Les types de numéros de téléphone sont les suivants.** <br/> |**Comment obtenir le nombre total de numéros de téléphone ?** <br/> |**Voici un exemple :** <br/> |
|Numéro d'utilisateur (abonné)  <br/> |Le nombre de numéros de téléphone est égal au nombre total de licences **Nationales appelant planifier** et/ou **national et International appelant planifier** multiplié par 1,1 + 10 autres numéros de téléphone. <br/> |Si j’ai 50 utilisateurs de total avec soit un intérieur appelant Plan et/ou nationales et internationales appelant planifier, vous pouvez vous procurer de numéro de téléphone **65** **(50 x 1.1 + 10)**. <br/> |
|Numéro de service payant  <br/> | Le nombre de numéros de téléphone est égal au nombre total de licences **Système téléphonique** et de **Conférence Audio** et utilise les éléments suivants : <br/>  Si **1 à 25 licences** sont affectées, **5** numéros de téléphone sont attribués. <br/>  Si **26 à 49 licences** sont affectées, **10** numéros de téléphone sont attribués. <br/>  S’il y a **des licences de 50 à 99** **20** les numéros de téléphone sont accordées. <br/>  Si **100 à 149 licences** sont affectées, **30** numéros de téléphone sont attribués. <br/>  Si **150 à 199 licences** sont affectées, **40** numéros de téléphone sont attribués. <br/>  Si **200 à 499 licences** sont affectées, **65** numéros de téléphone sont attribués. <br/>  Si **500 à 749 licences** sont affectées, **90** numéros de téléphone sont attribués. <br/>  Si **750 à 999 licences** sont affectées, **110** numéros de téléphone sont attribués. <br/>  Si **1 000 à 1 249 licences** sont affectées, **125** numéros de téléphone sont attribués. <br/>  **1 250-1,499** de licences **135** les numéros de téléphone sont accordées. <br/>  Si **1 500 à 1 999 licences** sont affectées, **160** numéros de téléphone sont attribués. <br/>  Si **2 000 à 2 999 licences** sont affectées, **210** numéros de téléphone sont attribués. <br/>  Si **3 000 à 6 999 licences** sont affectées, **420** numéros de téléphone sont attribués. <br/>  Si **7 000 à 9 999 licences** sont affectées, **500** numéros de téléphone sont attribués. <br/>  Si **10 000 à 14 999 licences** sont affectées, **600** numéros de téléphone sont attribués. <br/>  Si **15 000 à 19 999 licences** sont affectées, **700** numéros de téléphone sont attribués. <br/>  Si **20 000 à 49 999 licences** sont affectées, **1 000** numéros de téléphone sont attribués. <br/>  Si **+ de 50 000 licences** sont affectées, **1 500** numéros de téléphone sont attribués. <br/> |Si vous avez un total de **51** **Système téléphonique** et les licences de **Conférence Audio** , vous pouvez obtenir les **20** – numéros de service. <br/> |
|Numéro de service gratuit  <br/> | Le nombre de numéros de téléphone est égal au nombre total de licences **Système téléphonique** et de **Conférence Audio** et utilise les éléments suivants : <br/>  Si **1 à 25 licences** sont affectées, **5** numéros de téléphone sont attribués. <br/>  Si **26 à 49 licences** sont affectées, **10** numéros de téléphone sont attribués. <br/>  S’il y a **des licences de 50 à 99** **20** les numéros de téléphone sont accordées. <br/>  Si **100 à 149 licences** sont affectées, **30** numéros de téléphone sont attribués. <br/>  Si **150 à 199 licences** sont affectées, **40** numéros de téléphone sont attribués. <br/>  Si **200 à 499 licences** sont affectées, **65** numéros de téléphone sont attribués. <br/>  Si **500 à 749 licences** sont affectées, **90** numéros de téléphone sont attribués. <br/>  Si **750 à 999 licences** sont affectées, **110** numéros de téléphone sont attribués. <br/>  Si **1 000 à 1 249 licences** sont affectées, **125** numéros de téléphone sont attribués. <br/>  **1 250-1,499** de licences **135** les numéros de téléphone sont accordées. <br/>  Si **1 500 à 1 999 licences** sont affectées, **160** numéros de téléphone sont attribués. <br/>  Si **2 000 à 2 999 licences** sont affectées, **210** numéros de téléphone sont attribués. <br/>  Si **3 000 à 6 999 licences** sont affectées, **420** numéros de téléphone sont attribués. <br/>  Si **7 000 à 9 999 licences** sont affectées, **500** numéros de téléphone sont attribués. <br/>  Si **10 000 à 14 999 licences** sont affectées, **600** numéros de téléphone sont attribués. <br/>  Si **15 000 à 19 999 licences** sont affectées, **700** numéros de téléphone sont attribués. <br/>  Si **20 000 à 49 999 licences** sont affectées, **1 000** numéros de téléphone sont attribués. <br/>  Si **+ de 50 000 licences** sont affectées, **1 500** numéros de téléphone sont attribués. <br/> |Si vous avez un total de **1001** **Système téléphonique** et les licences de **Conférence Audio** , vous pouvez obtenir les numéros de service gratuit **125** . <br/> <br/> **Important :** [Communications crédits facturation](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md) est requis pour réserver et utiliser les numéros de téléphone.          |
   
> [!NOTE]
> Si vous devez obtenir davantage de numéros de téléphone, veuillez [contacter le support pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
  
## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](transferring-phone-numbers-common-questions.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer les numéros de téléphone de votre organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
[Conditions générales relatives aux appels d'urgence](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 