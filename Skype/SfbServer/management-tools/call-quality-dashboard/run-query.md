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
# <a name="run-query"></a><span data-ttu-id="7b96e-104">Exécuter requête</span><span class="sxs-lookup"><span data-stu-id="7b96e-104">Run Query</span></span>
 
<span data-ttu-id="7b96e-105">**Résumé :** Obtenir des informations sur l’opération d’exécuter la requête, qui fait partie de l’API de données pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="7b96e-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="7b96e-106">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7b96e-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7b96e-107">L’opération d’exécuter la requête fait partie de l’API de données pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="7b96e-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="run-query"></a><span data-ttu-id="7b96e-108">Exécuter requête</span><span class="sxs-lookup"><span data-stu-id="7b96e-108">Run Query</span></span>

<span data-ttu-id="7b96e-109">Exécuter la requête d’opération fournit la possibilité d’exécuter une requête sur le cube basé sur les filtres, les mesures et les dimensions spécifiées et renvoyer de nouveau les données.</span><span class="sxs-lookup"><span data-stu-id="7b96e-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>
  

|<span data-ttu-id="7b96e-110">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="7b96e-110">**Method**</span></span>|<span data-ttu-id="7b96e-111">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="7b96e-111">**Request URI**</span></span>|<span data-ttu-id="7b96e-112">**Version de HTTP**</span><span class="sxs-lookup"><span data-stu-id="7b96e-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7b96e-113">Publier</span><span class="sxs-lookup"><span data-stu-id="7b96e-113">POST</span></span>  <br/> |<span data-ttu-id="7b96e-114">https://\<portal\>/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="7b96e-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="7b96e-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="7b96e-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="7b96e-116">**Les paramètres URI** - None.</span><span class="sxs-lookup"><span data-stu-id="7b96e-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="7b96e-117">**En-têtes de requête** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="7b96e-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7b96e-118">Le **Corps de la demande** - ici est une charge utile de demande exemple au format JSON.</span><span class="sxs-lookup"><span data-stu-id="7b96e-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="7b96e-119">Il contient des dimensions, des filtres et mesure requise pour une requête.</span><span class="sxs-lookup"><span data-stu-id="7b96e-119">It contains dimensions, filters, and measurement required for a query.</span></span>
  
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

 <span data-ttu-id="7b96e-120">*Filtres* : une liste d’expressions de filtre à appliquer tels que le jeu de données obtenu reflète uniquement le sous-ensemble des données qui vous intéressent.</span><span class="sxs-lookup"><span data-stu-id="7b96e-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>
  
 <span data-ttu-id="7b96e-121">*Dimensions* - une liste des dimensions qui sera utilisé pour l’agrégation des données.</span><span class="sxs-lookup"><span data-stu-id="7b96e-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="7b96e-122">Au moins une dimension est obligatoire, mais plusieurs dimensions peuvent être spécifiées pour obtenir un niveau supplémentaire d’agrégations secondaire.</span><span class="sxs-lookup"><span data-stu-id="7b96e-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>
  
 <span data-ttu-id="7b96e-123">*Mesures* - une liste de mesures, également connu sous le nom des faits, que les mesures souhaitées pour être regroupé en agrégats basés sur les dimensions que vous avez spécifié.</span><span class="sxs-lookup"><span data-stu-id="7b96e-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>
  
 <span data-ttu-id="7b96e-124">*Tendance* - instructions de contrôle supplémentaire pour personnaliser les données de résultat.</span><span class="sxs-lookup"><span data-stu-id="7b96e-124">*Trend*  - Additional control instructions to customize the result data.</span></span>
  
 <span data-ttu-id="7b96e-125">**Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="7b96e-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="7b96e-126">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="7b96e-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="7b96e-127">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="7b96e-127">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7b96e-128">**Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="7b96e-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="7b96e-129">Il contient une table de données qui contient les données, il contient également une métadonnées, ce qui indique la durée d’exécution de requête et non les données à partir du cache.</span><span class="sxs-lookup"><span data-stu-id="7b96e-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>
  
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

 <span data-ttu-id="7b96e-130">*Temps d’exécution* : le temps total que nécessaire pour le serveur retourner les données.</span><span class="sxs-lookup"><span data-stu-id="7b96e-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="7b96e-131">Cela peut ou non impliquer la cache.</span><span class="sxs-lookup"><span data-stu-id="7b96e-131">This may or may not involve cache.</span></span>
  
 <span data-ttu-id="7b96e-132">*Résultat des données* - le résultat de la requête.</span><span class="sxs-lookup"><span data-stu-id="7b96e-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="7b96e-133">Il s’agit d’un tableau à deux dimensions contenant toutes les permutations des membres des dimensions et chaque élément contenant les noms des membres des dimensions, ainsi que les valeurs agrégées de mesure spécifié.</span><span class="sxs-lookup"><span data-stu-id="7b96e-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>
  
 <span data-ttu-id="7b96e-134">*Il en résulte du Cache* - pour les tests de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="7b96e-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="7b96e-135">Indique si le résultat est retourné à partir du cache ou du cube QoE.</span><span class="sxs-lookup"><span data-stu-id="7b96e-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
  

