---
title: Combien de numéros de téléphone vous pouvez obtenir ?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.assetid: 61dfb27c-5bfa-4481-a930-9c026e73ff3a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.quantity
- seo-marvel-mar2020
description: En savoir plus sur le nombre de numéros de téléphone que vous pouvez obtenir Microsoft Teams en fonction du type de numéro et du nombre de licences que vous avez.
ms.openlocfilehash: 8ee72f7af039fae5fc5f0a9b4983cc7d7691b2ce
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598528"
---
# <a name="how-many-phone-numbers-can-you-get"></a>Combien de numéros de téléphone vous pouvez obtenir ?

Lorsque vous recherchez et obtenez des numéros de téléphone pour votre organisation, vous pouvez obtenir plus de numéros de téléphone que de licences affectées. Cela dépend toutefois des types de numéros de téléphone que vous avez achetés et des types de licences que vous avez affectées. Vous pouvez cliquer [sur Différents types](different-kinds-of-phone-numbers-used-for-calling-plans.md) de numéros de téléphone utilisés pour les plans d’appel pour connaître les différents numéros de téléphone utilisés dans Microsoft Teams.
  
Vous pouvez consulter le nombre de numéros de téléphone que vous pouvez obtenir sur la **page** Obtenir des numéros de téléphone dans le Centre d’administration Microsoft Teams ou exécuter l’cmdlet [Get-CsOnlineTelephoneNumberAvailableCount.](/powershell/module/skype/Get-CsOnlineTelephoneNumberAvailableCount)
  
> [!IMPORTANT]
> Les limites ci-dessous n'incluent pas les numéros transférés vers Microsoft. 
  
## <a name="how-many-phone-numbers-you-can-get"></a>Combien de numéros de téléphone vous pouvez obtenir ?

||||
|:-----|:-----|:-----|
|**Les types de numéros de téléphone sont les suivants.** <br/> |**Comment obtenir le nombre total de numéros de téléphone ?** <br/> |**Voici un exemple :** <br/> |
|Numéro d'utilisateur (abonné)  <br/> |Le nombre de numéros de téléphone  est égal au  nombre total de licences Plan d’appels nationaux et/ou Plans d’appels nationaux et internationaux multiplié par 1,1 + 10 numéros de téléphone supplémentaires. <br/> |Si le total est de 50 utilisateurs avec un plan d’appels nationaux et/ou nationaux et internationaux, vous pouvez acquérir **65** numéros de téléphone **(50 x 1,1 + 10).** <br/> |
|Numéro de service payant  <br/> | Le nombre de numéros de téléphone est égal au nombre total de licences **de** Système téléphonique et **d’audioconférence** et utilise les services suivants : <br/>  Si **1 à 25 licences** sont affectées, **5** numéros de téléphone sont attribués. <br/>  Si **26 à 49 licences** sont affectées, **10** numéros de téléphone sont attribués. <br/>  Si de **50 à 99 licences sont attribués,** **20** numéros de téléphone sont attribués. <br/>  Si **100 à 149 licences** sont affectées, **30** numéros de téléphone sont attribués. <br/>  Si **150 à 199 licences** sont affectées, **40** numéros de téléphone sont attribués. <br/>  Si **200 à 499 licences** sont affectées, **65** numéros de téléphone sont attribués. <br/>  Si **500 à 749 licences** sont affectées, **90** numéros de téléphone sont attribués. <br/>  Si **750 à 999 licences** sont affectées, **110** numéros de téléphone sont attribués. <br/>  Si **1 000 à 1 249 licences** sont affectées, **125** numéros de téléphone sont attribués. <br/>  Si **1 250 à 1 499 licences sont attribués,** **135** numéros de téléphone sont attribués. <br/>  Si **1 500 à 1 999 licences** sont affectées, **160** numéros de téléphone sont attribués. <br/>  Si **2 000 à 2 999 licences** sont affectées, **210** numéros de téléphone sont attribués. <br/>  Si **3 000 à 6 999 licences** sont affectées, **420** numéros de téléphone sont attribués. <br/>  Si **7 000 à 9 999 licences** sont affectées, **500** numéros de téléphone sont attribués. <br/>  Si **10 000 à 14 999 licences** sont affectées, **600** numéros de téléphone sont attribués. <br/>  Si **15 000 à 19 999 licences** sont affectées, **700** numéros de téléphone sont attribués. <br/>  Si **20 000 à 49 999 licences** sont affectées, **1 000** numéros de téléphone sont attribués. <br/>  Si **+ de 50 000 licences** sont affectées, **1 500** numéros de téléphone sont attribués. <br/> |Si vous avez un total de **51 licences** **Système téléphonique** et Audioconférence, vous pouvez obtenir **20** numéros de service gratuits.  <br/> |
|Numéro de service gratuit  <br/> | Le nombre de numéros de téléphone est égal au nombre total de licences **de** Système téléphonique et **d’audioconférence** et utilise les services suivants : <br/>  Si **1 à 25 licences** sont affectées, **5** numéros de téléphone sont attribués. <br/>  Si **26 à 49 licences** sont affectées, **10** numéros de téléphone sont attribués. <br/>  Si de **50 à 99 licences sont attribués,** **20** numéros de téléphone sont attribués. <br/>  Si **100 à 149 licences** sont affectées, **30** numéros de téléphone sont attribués. <br/>  Si **150 à 199 licences** sont affectées, **40** numéros de téléphone sont attribués. <br/>  Si **200 à 499 licences** sont affectées, **65** numéros de téléphone sont attribués. <br/>  Si **500 à 749 licences** sont affectées, **90** numéros de téléphone sont attribués. <br/>  Si **750 à 999 licences** sont affectées, **110** numéros de téléphone sont attribués. <br/>  Si **1 000 à 1 249 licences** sont affectées, **125** numéros de téléphone sont attribués. <br/>  Si **1 250 à 1 499 licences sont attribués,** **135** numéros de téléphone sont attribués. <br/>  Si **1 500 à 1 999 licences** sont affectées, **160** numéros de téléphone sont attribués. <br/>  Si **2 000 à 2 999 licences** sont affectées, **210** numéros de téléphone sont attribués. <br/>  Si **3 000 à 6 999 licences** sont affectées, **420** numéros de téléphone sont attribués. <br/>  Si **7 000 à 9 999 licences** sont affectées, **500** numéros de téléphone sont attribués. <br/>  Si **10 000 à 14 999 licences** sont affectées, **600** numéros de téléphone sont attribués. <br/>  Si **15 000 à 19 999 licences** sont affectées, **700** numéros de téléphone sont attribués. <br/>  Si **20 000 à 49 999 licences** sont affectées, **1 000** numéros de téléphone sont attribués. <br/>  Si **+ de 50 000 licences** sont affectées, **1 500** numéros de téléphone sont attribués. <br/> |Si vous avez un total de **1 001**  licences de Système téléphonique et **d’audioconférence,** vous pouvez obtenir **125** numéros de service gratuits. <br/> <br/> **Important : la** [facturation des crédits de communication](set-up-communications-credits-for-your-organization.md) est requise pour réserver et utiliser des numéros de téléphone gratuits.          |
   
> [!NOTE]
> Si vous devez obtenir davantage de numéros de téléphone, veuillez [contacter le support pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
  
## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](./phone-number-calling-plans/port-order-overview.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer des numéros de téléphone pour votre entreprise](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

[Étiquette d’exclusion de responsabilité d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
