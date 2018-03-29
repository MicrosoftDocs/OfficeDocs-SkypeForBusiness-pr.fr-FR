---
title: Exécuter requête
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
description: 'Résumé : Découvrez l’opération d’exécuter la requête, qui fait partie de l’API de données pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 6e294625e173854382e39abc098a0480871586ac
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="run-query"></a>Exécuter requête
 
**Résumé :** Obtenir des informations sur l’opération d’exécuter la requête, qui fait partie de l’API de données pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
L’opération d’exécuter la requête fait partie de l’API de données pour appeler le tableau de bord qualité.
  
## <a name="run-query"></a>Exécuter requête

Exécuter la requête d’opération fournit la possibilité d’exécuter une requête sur le cube basé sur les filtres, les mesures et les dimensions spécifiées et renvoyer de nouveau les données.
  

|**Méthode**|**URI de la demande**|**Version de HTTP**|
|:-----|:-----|:-----|
|Publier  <br/> |https://\<portal\>/QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |
   
 **Les paramètres URI** - None.
  
 **En-têtes de requête** - aucun en-tête supplémentaire.
  
 Le **Corps de la demande** - ici est une charge utile de demande exemple au format JSON. Il contient des dimensions, des filtres et mesure requise pour une requête.
  
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

 *Filtres* : une liste d’expressions de filtre à appliquer tels que le jeu de données obtenu reflète uniquement le sous-ensemble des données qui vous intéressent.
  
 *Dimensions* - une liste des dimensions qui sera utilisé pour l’agrégation des données. Au moins une dimension est obligatoire, mais plusieurs dimensions peuvent être spécifiées pour obtenir un niveau supplémentaire d’agrégations secondaire.
  
 *Mesures* - une liste de mesures, également connu sous le nom des faits, que les mesures souhaitées pour être regroupé en agrégats basés sur les dimensions que vous avez spécifié.
  
 *Tendance* - instructions de contrôle supplémentaire pour personnaliser les données de résultat.
  
 **Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON. Il contient une table de données qui contient les données, il contient également une métadonnées, ce qui indique la durée d’exécution de requête et non les données à partir du cache.
  
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

 *Temps d’exécution* : le temps total que nécessaire pour le serveur retourner les données. Cela peut ou non impliquer la cache.
  
 *Résultat des données* - le résultat de la requête. Il s’agit d’un tableau à deux dimensions contenant toutes les permutations des membres des dimensions et chaque élément contenant les noms des membres des dimensions, ainsi que les valeurs agrégées de mesure spécifié.
  
 *Il en résulte du Cache* - pour les tests de diagnostic. Indique si le résultat est retourné à partir du cache ou du cube QoE.
  

