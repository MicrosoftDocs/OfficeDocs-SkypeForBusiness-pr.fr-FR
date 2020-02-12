---
title: Obtenir un cube
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Résumé : Découvrez l’opération obtenir le cube, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 1d8327439d79e7d02182dc7195bc0052bf6c923c
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888823"
---
# <a name="get-cube"></a><span data-ttu-id="07230-104">Obtenir un cube</span><span class="sxs-lookup"><span data-stu-id="07230-104">Get Cube</span></span>
 
<span data-ttu-id="07230-105">**Résumé :** Apprenez-en davantage sur l’opération obtenir le cube, qui fait partie de l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="07230-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="07230-106">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="07230-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="07230-107">L’opération obtenir le cube fait partie de l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="07230-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="07230-108">Obtenir un cube</span><span class="sxs-lookup"><span data-stu-id="07230-108">Get Cube</span></span>

<span data-ttu-id="07230-109">L’opération obtenir un cube renvoie la liste des dimensions et mesures disponibles.</span><span class="sxs-lookup"><span data-stu-id="07230-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="07230-110">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="07230-110">**Method**</span></span>|<span data-ttu-id="07230-111">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="07230-111">**Request URI**</span></span>|<span data-ttu-id="07230-112">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="07230-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07230-113">Télécharger</span><span class="sxs-lookup"><span data-stu-id="07230-113">GET</span></span>  <br/> |<span data-ttu-id="07230-114">https://\<Portal\>/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="07230-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="07230-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="07230-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="07230-116">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="07230-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="07230-117">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="07230-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="07230-118">Le corps de la **requête** .</span><span class="sxs-lookup"><span data-stu-id="07230-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="07230-119">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="07230-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="07230-120">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="07230-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="07230-121">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="07230-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="07230-122">Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="07230-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="07230-123">Cet exemple n’affiche que les deux premiers éléments de chaque groupe d’éléments cube.</span><span class="sxs-lookup"><span data-stu-id="07230-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
```json
{
"Kpis": [{
"FriendlyName": "Poor Trend Month",
"DataModelName": "[KPIValue].Poor Trend Month",
"Description": null
},
{
"FriendlyName": "Poor Rate Trend Month",
"DataModelName": "[KPIValue].Poor Rate Trend Month",
"Description": null
}],
"Dimensions": [{
"Category": "Access Location Pair",
"Attributes": [{
"FriendlyName": "Location Pair",
"DataModelName": "[Access Location Pair].[Location Pair]",
"Description": "Description of Location Pair"
}]
},
{
"Category": "Audio Bandwidth Est",
"Attributes": [{
"FriendlyName": "Metric",
"DataModelName": "[Audio Bandwidth Est].[Metric]",
"Description": "Description of Metric"
}]
}],
"Measurements": [{
"FriendlyName": "Audio Streams Count",
"DataModelName": "[Measures].[Audio Streams Count]",
"Description": "Description of Audio Streams Count"
},
{
"FriendlyName": "Audio Good Streams JPDR Count",
"DataModelName": "[Measures].[Audio Good Streams JPDR Count]",
"Description": "Description of Audio Good Streams JPDR Count"
}]
}
```

 <span data-ttu-id="07230-124">*KPI* -réservé.</span><span class="sxs-lookup"><span data-stu-id="07230-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="07230-125">La section KPI d’une charge utile de requête permet d’exécuter une requête afin de renvoyer des valeurs pour les indicateurs de performance clés définis dans le cube.</span><span class="sxs-lookup"><span data-stu-id="07230-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="07230-126">Aucun KPI n’existe encore dans le cube QoE.</span><span class="sxs-lookup"><span data-stu-id="07230-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="07230-127">*Dimensions* : liste des dimensions pouvant être utilisées dans les sections filtres et axes d’une charge utile de requête pour une opération d’exécution de requête.</span><span class="sxs-lookup"><span data-stu-id="07230-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="07230-128">Pour utiliser une dimension dans une expression de filtre, vous devez spécifier un membre de dimension, qui peut être obtenu à l’aide de l’opération obtenir les membres de la dimension.</span><span class="sxs-lookup"><span data-stu-id="07230-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="07230-129">*Mesures* : liste des mesures qui pourraient être utilisées dans la section mesures d’une charge utile de requête pour une opération d’exécution de requête.</span><span class="sxs-lookup"><span data-stu-id="07230-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

