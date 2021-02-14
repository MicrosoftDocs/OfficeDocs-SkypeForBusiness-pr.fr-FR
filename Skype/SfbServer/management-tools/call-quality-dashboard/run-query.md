---
title: Exécuter la requête
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Résumé : Découvrez l’opération Exécuter une requête, qui fait partie de l’API de données pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: bff24ca5a4d651ba276b4b0d795afabce3c6d0dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803114"
---
# <a name="run-query"></a><span data-ttu-id="37586-104">Exécuter la requête</span><span class="sxs-lookup"><span data-stu-id="37586-104">Run Query</span></span>

<span data-ttu-id="37586-105">**Résumé :** Découvrez l’opération Exécuter une requête, qui fait partie de l’API de données pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="37586-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="37586-106">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="37586-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="37586-107">L’opération Exécuter une requête fait partie de l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="37586-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="37586-108">Exécuter la requête</span><span class="sxs-lookup"><span data-stu-id="37586-108">Run Query</span></span>

<span data-ttu-id="37586-109">L’opération Exécuter une requête permet d’exécuter une requête sur le cube en fonction des dimensions, mesures et filtres spécifiés et de renvoyer les données.</span><span class="sxs-lookup"><span data-stu-id="37586-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="37586-110">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="37586-110">**Method**</span></span>|<span data-ttu-id="37586-111">**URI de demande**</span><span class="sxs-lookup"><span data-stu-id="37586-111">**Request URI**</span></span>|<span data-ttu-id="37586-112">**HTTP Version**</span><span class="sxs-lookup"><span data-stu-id="37586-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="37586-113">POST</span><span class="sxs-lookup"><span data-stu-id="37586-113">POST</span></span>  <br/> |<span data-ttu-id="37586-114">https:// \<portal\> /QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="37586-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="37586-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="37586-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="37586-116">**Paramètres d’URI** - Aucun.</span><span class="sxs-lookup"><span data-stu-id="37586-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="37586-117">**En-têtes de requête** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="37586-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="37586-118">**Corps de la** demande : voici un exemple de charge utile de requête dans JSON.</span><span class="sxs-lookup"><span data-stu-id="37586-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="37586-119">Il contient les dimensions, filtres et mesures requis pour une requête.</span><span class="sxs-lookup"><span data-stu-id="37586-119">It contains dimensions, filters, and measurement required for a query.</span></span>

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

 <span data-ttu-id="37586-120">*Filtres*  : liste des expressions de filtre à appliquer de telle façon que le jeu de données résultant reflète uniquement le sous-ensemble des données qui sont d’intérêt.</span><span class="sxs-lookup"><span data-stu-id="37586-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="37586-121">*Dimensions*  : liste des dimensions qui seront utilisées pour l’agrégation des données.</span><span class="sxs-lookup"><span data-stu-id="37586-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="37586-122">Au moins une dimension est requise, mais plusieurs dimensions peuvent être spécifiées pour obtenir un niveau supplémentaire de sous-agrégations.</span><span class="sxs-lookup"><span data-stu-id="37586-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="37586-123">Mesures : liste de mesures, également appelées faits, qui sont les mesures *souhaitées* à agréger en fonction des dimensions que vous avez spécifiées.</span><span class="sxs-lookup"><span data-stu-id="37586-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="37586-124">*Tendance*  : instructions de contrôle supplémentaires pour personnaliser les données des résultats.</span><span class="sxs-lookup"><span data-stu-id="37586-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="37586-125">**Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="37586-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="37586-126">**Code d’état** : une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="37586-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="37586-127">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="37586-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="37586-128">**Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="37586-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="37586-129">Il contient une table de données qui contient les données, ainsi qu’une métadon données, qui indique la durée d’exécution de la requête et indique si les données sont à partir du cache ou non.</span><span class="sxs-lookup"><span data-stu-id="37586-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

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

 <span data-ttu-id="37586-130">*Durée d’exécution*  : temps total qu’il a fallu au serveur pour renvoyer les données.</span><span class="sxs-lookup"><span data-stu-id="37586-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="37586-131">Cela peut impliquer ou non le cache.</span><span class="sxs-lookup"><span data-stu-id="37586-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="37586-132">*Résultat des*  données : résultat de la requête.</span><span class="sxs-lookup"><span data-stu-id="37586-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="37586-133">Il s’agit d’un tableau à deux dimensions contenant toutes les permutations des membres des dimensions, et chaque élément contenant les noms de membres des dimensions, ainsi que les valeurs agrégées des mesures spécifiées.</span><span class="sxs-lookup"><span data-stu-id="37586-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="37586-134">*Résultat du cache*  : pour les diagnostics.</span><span class="sxs-lookup"><span data-stu-id="37586-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="37586-135">Indique si le résultat est issu du cache ou du cube QoE.</span><span class="sxs-lookup"><span data-stu-id="37586-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
