---
title: Exécuter la requête
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Résumé : Découvrez l’opération d’exécuter la requête, qui fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 3720ce118537963e5093741c4f05315e887bd60d
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569746"
---
# <a name="run-query"></a>Exécuter la requête
 
**Résumé :** Obtenir des informations sur l’opération d’exécuter la requête, qui fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.
  
L’opération d’exécuter la requête fait partie de l’API de données pour le tableau de bord qualité des appels.
  
## <a name="run-query"></a>Exécuter la requête

Exécuter la requête d’opération offre la possibilité d’exécuter une requête sur le cube basé sur des filtres, des mesures et dimensions spécifiées et renvoyer dans les données.
  

|**Méthode**|**URI de la demande**|**Version HTTP**|
|:-----|:-----|:-----|
|Publier  <br/> |https://\<portal\>/QoEDataService/RunQuery  <br/> |HTTP/1.1.  <br/> |
   
 **Paramètres d’URI** - None.
  
 **En-têtes de demande** - aucun en-tête supplémentaire.
  
 **Corps de la requête** - ici est une charge utile d’exemple demande au format JSON. Il contient des dimensions, des filtres et mesure requis pour une requête.
  
```
{
"Filters": [{
"DataModelName": "[StartDate].[Month]",
"Caption": "July 2013",
"Value": "[2015-03-01T00:00:00]",
"Operand": 0,
"UnionGroup": ""
}],
"Dimensions": [{
"DataModelName": "[StartDate].[Month]"
}],
"Measurements": [{
"DataModelName": "[Measures].[Audio Good Streams Count]"
},
{
"DataModelName": "[Measures].[Audio UnClassified Streams Count]"
},
{
"DataModelName": "[Measures].[Audio Poor Streams Count]"
},
{
"DataModelName": "[Measures].[AudioPoorPercentage]"
}],
"Trend": {
"EnableTrend": true,
"SpanCount": 7,
"TrendDate": "2015-3",
"Type": 0
}
}
```

 *Filtres* - une liste d’expressions de filtre à appliquer tels que l’ensemble de données qui en résulte reflète uniquement le sous-ensemble de données qui présentent un intérêt.
  
 *Dimensions* - liste des dimensions qui sera utilisé pour regrouper les données. Au moins une dimension est requise mais plusieurs dimensions peuvent être spécifiées pour obtenir un niveau supplémentaire de sous-sites agrégations.
  
 *Des mesures* - une liste de mesures, également appelé faits, qui sont les mesures souhaitées pour être regroupés selon les dimensions que vous avez spécifié.
  
 *Tendance* - instructions de contrôle supplémentaire pour personnaliser les données résultantes.
  
 **Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON. Elle contient une table de données qui contient les données, il contient également une métadonnées, qui indique la durée d’exécution de requête et ou non les données à partir du cache.
  
```
{
"ExecutionTime": "00:00:00.2102630",
"DataResult": [["September 2014",
        1792,
        34,
        78,
        4.171],
        ["October 2014",
        37017,
        1731,
        3305,
        8.197],
        ["November 2014",
        79184,
        3033,
        5556,
        6.557],
        ["December 2014",
        122253,
        4050,
        5444,
        4.263],
        ["January 2015",
        31246,
        1069,
        1342,
        4.118]],
"ResultIsFromCache": false,
"ErrorType": 0
}

```

 *Durée d’exécution* : la durée totale que nécessaire pour le serveur renvoyer les données. Cela peut ou non impliquer du cache.
  
 *Données* - le résultat de la requête. Il est un tableau à deux dimensions contenant toutes les permutations de membres des dimensions et chaque élément contenant les noms de membres des dimensions, ainsi que les valeurs agrégées des mesures spécifiés.
  
 *Il en résulte du Cache* - diagnostics. Indique si le résultat provient du cache ou du cube QoE.