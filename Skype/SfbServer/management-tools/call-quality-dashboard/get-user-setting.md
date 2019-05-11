---
title: Obtention d’un paramètre utilisateur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Résumé : Découvrez l’opération obtenir les paramètres utilisateur, qui fait partie du Service de paramètres utilisateur. Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 91f8c60a33c6126f61901c4d73e4a6f2c5b5e1f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930727"
---
# <a name="get-user-setting"></a>Obtention d’un paramètre utilisateur
 
**Résumé :** Obtenir des informations sur l’opération obtenir les paramètres utilisateur, qui fait partie du Service de paramètres utilisateur. Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.
  
L’opération obtenir le paramètre utilisateur fait partie du Service de paramètres utilisateur de l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="get-user-setting"></a>Obtention d’un paramètre utilisateur

Obtenir le paramètre utilisateur renvoie un paramètre d’utilisateur unique.
  

|**Méthode**|**URI de la demande**|**Version HTTP**|
|:-----|:-----|:-----|
|Avoir  <br/> |https://\<portal\>/QoERepositoryService/référentiel/utilisateur / {userId} /setting/ {clé}  <br/> |HTTP/1.1.  <br/> |
   
 **Paramètres d’URI** - None.
  
 **En-têtes de demande** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId* - ID de l’utilisateur.
  
 *clé* - clé du paramètre.
  
 *valeur* : valeur du paramètre.
  

