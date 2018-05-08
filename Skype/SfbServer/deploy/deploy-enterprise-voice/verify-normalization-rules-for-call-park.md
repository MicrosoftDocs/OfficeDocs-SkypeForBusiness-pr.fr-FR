---
title: Vérification des règles de normalisation du parcage d’appel dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Découvrez les règles de normalisation de parcage d’appel dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: c637240d4c193bbec05228d167d77f7bd18c0d04
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a>Vérification des règles de normalisation du parcage d’appel dans Skype Entreprise 2015
 
Découvrez les règles de normalisation de parcage d’appel dans Skype pour Business Server Enterprise Voice.
  
Orbites de parcage d’appel ne doivent pas être normalisées. Vérifiez dans vos plans de numérotation que vos numéros orbites ne sont pas normalisés. Si vous devez créer une règle de normalisation supplémentaire pour empêcher que votre orbites en cours de normalisation, suivez la procédure décrite dans [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](dial-plans.md) pour définir une nouvelle règle de normalisation, donc ce **modèle pour la correspondance** identifie la plage d’orbites et **modèle de traduction** est **$1**. Par exemple, si votre plage d’orbites de parcage d’appel est 7999-7000, le **modèle pour la correspondance** est **^(7\d{3})$** et **modèle de traduction** est **$1**.
  
> [!IMPORTANT]
> N’oubliez pas que la règle de normalisation par défaut dans vos plans de numérotation ne contient pas **^(\d\*)**. Dans le cas contraire, votre règle de normalisation de parcage d’appel ne s’exécutera jamais.
  
## <a name="see-also"></a>Voir aussi

#### 

[Créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](dial-plans.md)

