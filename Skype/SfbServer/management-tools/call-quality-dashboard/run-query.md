---
title: Exécuter la requête
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Résumé : Découvrez l’opération exécuter une requête, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 8d31ea4c597ea3353fdd5da3e863938aababe819
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991399"
---
# <a name="run-query"></a>Exécuter la requête

**Résumé :** Apprenez-en davantage sur l’opération exécuter une requête, qui fait partie de l’API de données pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.

L’opération exécuter la requête fait partie de l’API de données du tableau de bord de qualité des appels.

## <a name="run-query"></a>Exécuter la requête

L’opération exécuter une requête permet d’exécuter une requête sur le cube en fonction de dimensions, mesures et filtres spécifiés, puis de renvoyer les données.


|**Méthode**|**URI de la requête**|**Version HTTP**|
|:-----|:-----|:-----|
|Publier  <br/> |https://\<Portal\>/QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **Paramètres d’URI** -aucun.

 **En-têtes de requête** -aucun en-tête supplémentaire.

 Le corps de la **requête** est un exemple de charge utile de requête dans JSON. Il contient des dimensions, des filtres et des mesures nécessaires pour une requête.

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

 *Filtres* : liste des expressions de filtre à appliquer de telle sorte que le jeu de données qui en résulte reflète uniquement le sous-ensemble des données qui vous intéressent.

 *Dimensions* : liste des dimensions qui seront utilisées pour l’agrégation des données. Au moins une dimension est requise, mais plusieurs dimensions doivent être spécifiées pour obtenir un niveau supplémentaire de sous-agrégations.

 *Mesures* : liste des mesures, également appelées faits, qui sont les mesures souhaitées pour être agrégées en fonction des dimensions que vous avez spécifiées.

 *Tendance* -instructions de contrôle supplémentaires permettant de personnaliser les données de résultat.

 **Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.

 **Code d’État** -une opération réussie renvoie le code d’état 200 (OK).

 **En-têtes de réponse** : aucun en-tête supplémentaire.

 Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON. Elle contient une table de données qui contient les données, elle contient également une méta-données, qui indique le temps d’exécution des requêtes et si les données proviennent du cache.

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

 *Durée d’exécution* : temps total nécessaire au serveur pour renvoyer les données. Cela risque de ne pas impliquer le cache.

 *Résultat* de la requête : résultat de la requête. Il s’agit d’un tableau à deux dimensions contenant toutes les permutations des membres des dimensions et chaque élément contenant les noms de membres des dimensions, ainsi que les valeurs agrégées des mesures spécifiées.

 Le *résultat provient du cache* -pour les Diagnostics. Indique si le résultat provient du cache ou du cube QoE.
