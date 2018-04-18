---
title: Le nombre de numéros de téléphone vous pouvez obtenir ?
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: Lorsque vous recherchez et obtenez des numéros de téléphone pour votre organisation, vous pouvez obtenir plus de numéros de téléphone que de licences affectées. Cela dépend toutefois des types de numéros de téléphone que vous avez achetés et des types de licences que vous avez affectées. Vous pouvez cliquer sur les différents types de numéros de téléphone utilisés pour les Plans d’appel pour savoir comment les numéros de téléphone utilisés dans Skype pour l’activité en ligne.
ms.openlocfilehash: c128708611405b8c3f4da25a0be38801ad3b38f9
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="how-many-phone-numbers-can-you-get"></a>Le nombre de numéros de téléphone vous pouvez obtenir ?

Lorsque vous recherchez et obtenez des numéros de téléphone pour votre organisation, vous pouvez obtenir plus de numéros de téléphone que de licences affectées. Cela dépend toutefois des types de numéros de téléphone que vous avez achetés et des types de licences que vous avez affectées. Vous pouvez cliquer sur les [différents types de numéros de téléphone utilisés pour les Plans d’appel](different-kinds-of-phone-numbers-used-for-calling-plans.md) pour savoir comment les numéros de téléphone utilisés dans Skype pour l’activité en ligne.
  
Vous pouvez voir le nombre de numéros de téléphone que vous pouvez obtenir sur la page de **numéros de téléphone** dans le Skype pour le centre d’administration commerciale, ou vous pouvez exécuter l’applet de commande [Get-CsOnlineTelephoneNumberAvailableCount](https://technet.microsoft.com/en-us/library/mt634605.aspx) .
  
> [!IMPORTANT]
> Les limites ci-dessous n'incluent pas les numéros transférés vers Microsoft. 
  
## <a name="how-many-phone-numbers-you-can-get"></a>Le nombre de numéros de téléphone que vous pouvez obtenir ?

||||
|:-----|:-----|:-----|
|**Les types de numéros de téléphone sont les suivants.** <br/> |**Comment obtenir le nombre total de numéros de téléphone ?** <br/> |**Voici un exemple :** <br/> |
|Numéro d'utilisateur (abonné)  <br/> |Le nombre de numéros de téléphone est égal au nombre total de licences **Intérieures appelant Plan** et/ou **national et International appelant Plan** multiplié par 1,1 + 10 autres numéros de téléphone. <br/> |Si j’ai 50 utilisateurs dans total avec soit un intérieur appelant Plan et/ou national et International appel de Plan, vous pouvez acquérir de numéro de téléphone **65** **(50 x 1.1 + 10)**. <br/> |
|Numéro de service payant  <br/> | Le nombre de numéros de téléphone est égal au nombre total de licences **Système téléphonique** et **Audioconférence** et utilise les éléments suivants : <br/>  Si **1 à 25 licences** sont affectées, **5** numéros de téléphone sont attribués. <br/>  Si **26 à 49 licences** sont affectées, **10** numéros de téléphone sont attribués. <br/>  S’il existe des **licences de 50-99** **20** les numéros de téléphone sont données. <br/>  Si **100 à 149 licences** sont affectées, **30** numéros de téléphone sont attribués. <br/>  Si **150 à 199 licences** sont affectées, **40** numéros de téléphone sont attribués. <br/>  Si **200 à 499 licences** sont affectées, **65** numéros de téléphone sont attribués. <br/>  Si **500 à 749 licences** sont affectées, **90** numéros de téléphone sont attribués. <br/>  Si **750 à 999 licences** sont affectées, **110** numéros de téléphone sont attribués. <br/>  Si **1 000 à 1 249 licences** sont affectées, **125** numéros de téléphone sont attribués. <br/>  S’il existe des **licences de 1,499-1 250** **135** les numéros de téléphone sont donnés. <br/>  Si **1 500 à 1 999 licences** sont affectées, **160** numéros de téléphone sont attribués. <br/>  Si **2 000 à 2 999 licences** sont affectées, **210** numéros de téléphone sont attribués. <br/>  Si **3 000 à 6 999 licences** sont affectées, **420** numéros de téléphone sont attribués. <br/>  Si **7 000 à 9 999 licences** sont affectées, **500** numéros de téléphone sont attribués. <br/>  Si **10 000 à 14 999 licences** sont affectées, **600** numéros de téléphone sont attribués. <br/>  Si **15 000 à 19 999 licences** sont affectées, **700** numéros de téléphone sont attribués. <br/>  Si **20 000 à 49 999 licences** sont affectées, **1 000** numéros de téléphone sont attribués. <br/>  Si **+ de 50 000 licences** sont affectées, **1 500** numéros de téléphone sont attribués. <br/> |Si vous avez un total de **51** du **Système téléphonique** et **Audioconférence** licences, vous pouvez obtenir **20** – numéros de service. <br/> |
|Numéro de service gratuit  <br/> | Le nombre de numéros de téléphone est égal au nombre total de licences **Système téléphonique** et **Audioconférence** et utilise les éléments suivants : <br/>  Si **1 à 25 licences** sont affectées, **5** numéros de téléphone sont attribués. <br/>  Si **26 à 49 licences** sont affectées, **10** numéros de téléphone sont attribués. <br/>  S’il existe des **licences de 50-99** **20** les numéros de téléphone sont données. <br/>  Si **100 à 149 licences** sont affectées, **30** numéros de téléphone sont attribués. <br/>  Si **150 à 199 licences** sont affectées, **40** numéros de téléphone sont attribués. <br/>  Si **200 à 499 licences** sont affectées, **65** numéros de téléphone sont attribués. <br/>  Si **500 à 749 licences** sont affectées, **90** numéros de téléphone sont attribués. <br/>  Si **750 à 999 licences** sont affectées, **110** numéros de téléphone sont attribués. <br/>  Si **1 000 à 1 249 licences** sont affectées, **125** numéros de téléphone sont attribués. <br/>  S’il existe des **licences de 1,499-1 250** **135** les numéros de téléphone sont donnés. <br/>  Si **1 500 à 1 999 licences** sont affectées, **160** numéros de téléphone sont attribués. <br/>  Si **2 000 à 2 999 licences** sont affectées, **210** numéros de téléphone sont attribués. <br/>  Si **3 000 à 6 999 licences** sont affectées, **420** numéros de téléphone sont attribués. <br/>  Si **7 000 à 9 999 licences** sont affectées, **500** numéros de téléphone sont attribués. <br/>  Si **10 000 à 14 999 licences** sont affectées, **600** numéros de téléphone sont attribués. <br/>  Si **15 000 à 19 999 licences** sont affectées, **700** numéros de téléphone sont attribués. <br/>  Si **20 000 à 49 999 licences** sont affectées, **1 000** numéros de téléphone sont attribués. <br/>  Si **+ de 50 000 licences** sont affectées, **1 500** numéros de téléphone sont attribués. <br/> |Si vous avez un total de **1001** **Système téléphonique** et **Audioconférence** licences, vous pouvez obtenir les numéros de service gratuit de **125** . <br/> <br/> **Important :** [Facturation des communications crédits](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md) est nécessaire de réserver et d’utiliser des numéros de téléphone.          |
   
> [!NOTE]
> Si vous devez obtenir davantage de numéros de téléphone, veuillez [contacter le support pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
  
## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](transferring-phone-numbers-common-questions.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer les numéros de téléphone de votre organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 