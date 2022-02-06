---
title: Exécuter la requête
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Résumé : Découvrez l’opération Exécuter une requête, qui fait partie de l’API de données pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
---

# <a name="run-query"></a>Exécuter la requête

**Résumé :** Découvrez l’opération Exécuter une requête, qui fait partie de l’API de données pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.

L’opération Exécuter une requête fait partie de l’API de données du tableau de bord de qualité des appels.

## <a name="run-query"></a>Exécuter la requête

L’opération Exécuter une requête permet d’exécuter une requête sur le cube en fonction des dimensions, mesures et filtres spécifiés et de renvoyer les données.


|**Méthode**|**URI de demande**|**HTTP Version**|
|:-----|:-----|:-----|
|POST  <br/> |\<portal\>https:///QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **Paramètres d’URI** - Aucun.

 **En-têtes de requête** : aucun en-tête supplémentaire.

 **Corps de la** demande : voici un exemple de charge utile de requête dans JSON. Il contient les dimensions, filtres et mesures requis pour une requête.

```json
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

 *Filtres*  : liste des expressions de filtre à appliquer de telle façon que le jeu de données résultant reflète uniquement le sous-ensemble des données qui sont d’intérêt.

 *Dimensions*  : liste des dimensions qui seront utilisées pour l’agrégation des données. Au moins une dimension est requise, mais plusieurs dimensions peuvent être spécifiées pour obtenir un niveau supplémentaire de sous-agrégations.

 *Mesures :*  liste de mesures, également appelées faits, qui sont les mesures souhaitées à agréger en fonction des dimensions que vous avez spécifiées.

 *Tendance*  : instructions de contrôle supplémentaires pour personnaliser les données des résultats.

 **Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.

 **Code d’état** : une opération réussie renvoie le code d’état 200 (OK).

 **En-têtes de réponse** : aucun en-tête supplémentaire.

 **Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON. Il contient une table de données qui contient les données, ainsi qu’une métadon données, qui indique la durée d’exécution de la requête et indique si les données sont à partir du cache ou non.

```json
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

 *Durée d’exécution*  : temps total qu’il a fallu au serveur pour renvoyer les données. Cela peut impliquer ou non le cache.

 *Résultat des*  données : résultat de la requête. Il s’agit d’un tableau à deux dimensions contenant toutes les permutations des membres des dimensions, et chaque élément contenant les noms de membres des dimensions, ainsi que les valeurs agrégées des mesures spécifiées.

 *Résultat du cache*  : pour les diagnostics. Indique si le résultat est issu du cache ou du cube QoE.
