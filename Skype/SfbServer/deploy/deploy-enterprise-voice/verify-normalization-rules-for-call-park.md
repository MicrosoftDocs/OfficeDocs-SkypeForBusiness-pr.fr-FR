---
title: Vérification des règles de normalisation du parcage d’appel dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Obtenir des informations sur les règles de normalisation pour le parc d’appel dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 4f3651394bbdb5556a83aa34739a86f8d06f1396
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a>Vérification des règles de normalisation du parcage d’appel dans Skype Entreprise 2015
 
Obtenir des informations sur les règles de normalisation pour le parc d’appel dans Skype pour Business Server Voix Entreprise.
  
Orbites de parc d’appel ne doivent pas être normalisés. Vérifiez dans vos plans de numérotation que vos numéros orbites ne sont pas normalisés. Si vous devez créer une règle de normalisation supplémentaires pour éviter que votre orbites en cours de normalisation, suivez la procédure décrite dans [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](dial-plans.md) pour définir une nouvelle règle de normalisation, donc ce **modèle à faire correspondre** identifie la plage d’orbite et **modèle de traduction** est **$1**. Par exemple, si votre plage d’orbite de parc d’appel est 7999-7000, le **modèle à faire correspondre** est **^ (7\d {3}) $** et **modèle de traduction** est **$1**.
  
> [!IMPORTANT]
> N’oubliez pas que la règle de normalisation par défaut dans vos plans de numérotation ne contient-elle pas **^(\d\*)**. Dans le cas contraire, votre règle de normalisation de parc d’appel ne s’exécutera jamais.
  
## <a name="see-also"></a>Voir aussi

#### 

[Créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](dial-plans.md)

