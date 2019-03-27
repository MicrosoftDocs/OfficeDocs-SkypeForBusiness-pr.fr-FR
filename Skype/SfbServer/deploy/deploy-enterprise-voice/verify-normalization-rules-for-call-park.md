---
title: Vérifier les règles de normalisation pour le parcage d’appel dans Skype pour les entreprises
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Découvrez les règles de normalisation de parcage d’appel dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 794d64efcefbc4b36fac84e6356df46df76dc5a2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877275"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Vérifier les règles de normalisation pour le parcage d’appel dans Skype pour les entreprises
 
Découvrez les règles de normalisation de parcage d’appel dans Skype pour Business Server Enterprise Voice.
  
Orbites de parcage d’appel ne doivent pas être normalisées. Vérifiez dans vos plans de numérotation que vos numéros orbites ne sont pas normalisés. Si vous devez créer une règle de normalisation supplémentaire pour empêcher que votre orbites en cours de normalisation, suivez la procédure décrite dans [créer ou modifier un plan de numérotation dans Skype pour Business Server](dial-plans.md) pour définir une nouvelle règle de normalisation, donc ce **modèle pour la correspondance** identifie la plage d’orbites et **modèle de traduction** est **$1**. Par exemple, si votre plage d’orbites de parcage d’appel est 7999-7000, le **modèle pour la correspondance** est **^(7\d{3})$** et **modèle de traduction** est **$1**.
  
> [!IMPORTANT]
> N’oubliez pas que la règle de normalisation par défaut dans vos plans de numérotation ne contient pas **^(\d\*)**. Dans le cas contraire, votre règle de normalisation de parcage d’appel ne s’exécutera jamais.
  
## <a name="see-also"></a>Voir aussi

[Créer ou modifier un plan de numérotation dans Skype pour Business Server](dial-plans.md)

