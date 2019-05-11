---
title: Obtenir les ancêtres d’élément
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Résumé : Découvrez l’opération obtenir des ancêtres élément, qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 22672146ec9ab071041c85c31a466d766ffe31b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930636"
---
# <a name="get-item-ancestors"></a>Obtenir les ancêtres d’élément
 
**Résumé :** Obtenir des informations sur l’opération obtenir des ancêtres élément, qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.
  
L’opération obtenir des ancêtres élément fait partie du Service d’élément dans l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="get-item-ancestors"></a>Obtenir les ancêtres d’élément

Get élément ancêtres renvoie une ancêtres des éléments spécifiques à partir du référentiel.
  

|**Méthode**|**URI de la demande**|**Version HTTP**|
|:-----|:-----|:-----|
|Avoir  <br/> |https://\<portal\>/QoERepositoryService/référentiel/itemAncestors / {itemId}  <br/> |HTTP/1.1.  <br/> |
   
 **Paramètres d’URI** - None.
  
 **En-têtes de demande** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK). Si un utilisateur spécifié QU'ID est introuvable, elle renvoie le code d’état 404 (introuvable).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.
  
```
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 *Item1* - ID de l’élément.
  
 *Item2* - profondeur est la distance à partir de l’élément. 0 est le parent immédiat.
  
 *Item3* - titre de l’élément.
  

