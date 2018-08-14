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
# <a name="run-query"></a><span data-ttu-id="1b4b2-104">Exécuter la requête</span><span class="sxs-lookup"><span data-stu-id="1b4b2-104">Run Query</span></span>
 
<span data-ttu-id="1b4b2-105">**Résumé :** Obtenir des informations sur l’opération d’exécuter la requête, qui fait partie de l’API de données pour le tableau de bord qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="1b4b2-106">Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1b4b2-107">L’opération d’exécuter la requête fait partie de l’API de données pour le tableau de bord qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="run-query"></a><span data-ttu-id="1b4b2-108">Exécuter la requête</span><span class="sxs-lookup"><span data-stu-id="1b4b2-108">Run Query</span></span>

<span data-ttu-id="1b4b2-109">Exécuter la requête d’opération offre la possibilité d’exécuter une requête sur le cube basé sur des filtres, des mesures et dimensions spécifiées et renvoyer dans les données.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>
  

|<span data-ttu-id="1b4b2-110">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="1b4b2-110">**Method**</span></span>|<span data-ttu-id="1b4b2-111">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="1b4b2-111">**Request URI**</span></span>|<span data-ttu-id="1b4b2-112">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="1b4b2-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1b4b2-113">Publier</span><span class="sxs-lookup"><span data-stu-id="1b4b2-113">POST</span></span>  <br/> |<span data-ttu-id="1b4b2-114">https://\<portal\>/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="1b4b2-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="1b4b2-115">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1b4b2-116">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1b4b2-117">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1b4b2-118">**Corps de la requête** - ici est une charge utile d’exemple demande au format JSON.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="1b4b2-119">Il contient des dimensions, des filtres et mesure requis pour une requête.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-119">It contains dimensions, filters, and measurement required for a query.</span></span>
  
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

 <span data-ttu-id="1b4b2-120">*Filtres* - une liste d’expressions de filtre à appliquer tels que l’ensemble de données qui en résulte reflète uniquement le sous-ensemble de données qui présentent un intérêt.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>
  
 <span data-ttu-id="1b4b2-121">*Dimensions* - liste des dimensions qui sera utilisé pour regrouper les données.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="1b4b2-122">Au moins une dimension est requise mais plusieurs dimensions peuvent être spécifiées pour obtenir un niveau supplémentaire de sous-sites agrégations.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>
  
 <span data-ttu-id="1b4b2-123">*Des mesures* - une liste de mesures, également appelé faits, qui sont les mesures souhaitées pour être regroupés selon les dimensions que vous avez spécifié.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>
  
 <span data-ttu-id="1b4b2-124">*Tendance* - instructions de contrôle supplémentaire pour personnaliser les données résultantes.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-124">*Trend*  - Additional control instructions to customize the result data.</span></span>
  
 <span data-ttu-id="1b4b2-125">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1b4b2-126">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="1b4b2-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="1b4b2-127">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-127">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1b4b2-128">**Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="1b4b2-129">Elle contient une table de données qui contient les données, il contient également une métadonnées, qui indique la durée d’exécution de requête et ou non les données à partir du cache.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>
  
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

 <span data-ttu-id="1b4b2-130">*Durée d’exécution* : la durée totale que nécessaire pour le serveur renvoyer les données.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="1b4b2-131">Cela peut ou non impliquer du cache.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-131">This may or may not involve cache.</span></span>
  
 <span data-ttu-id="1b4b2-132">*Données* - le résultat de la requête.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="1b4b2-133">Il est un tableau à deux dimensions contenant toutes les permutations de membres des dimensions et chaque élément contenant les noms de membres des dimensions, ainsi que les valeurs agrégées des mesures spécifiés.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>
  
 <span data-ttu-id="1b4b2-134">*Il en résulte du Cache* - diagnostics.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="1b4b2-135">Indique si le résultat provient du cache ou du cube QoE.</span><span class="sxs-lookup"><span data-stu-id="1b4b2-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>