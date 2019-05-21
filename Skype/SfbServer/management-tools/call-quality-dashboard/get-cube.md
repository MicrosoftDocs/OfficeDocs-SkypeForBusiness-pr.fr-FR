---
title: Obtenir un cube
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Résumé: Découvrez l’opération obtenir le cube, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 970187ce9f95700185ab09bd7aadf9045575b393
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274771"
---
# <a name="get-cube"></a><span data-ttu-id="e6725-104">Obtenir un cube</span><span class="sxs-lookup"><span data-stu-id="e6725-104">Get Cube</span></span>
 
<span data-ttu-id="e6725-105">**Résumé:** Apprenez-en davantage sur l’opération obtenir le cube, qui fait partie de l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="e6725-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="e6725-106">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e6725-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="e6725-107">L’opération obtenir le cube fait partie de l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="e6725-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="e6725-108">Obtenir un cube</span><span class="sxs-lookup"><span data-stu-id="e6725-108">Get Cube</span></span>

<span data-ttu-id="e6725-109">L’opération obtenir un cube renvoie la liste des dimensions et mesures disponibles.</span><span class="sxs-lookup"><span data-stu-id="e6725-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="e6725-110">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="e6725-110">**Method**</span></span>|<span data-ttu-id="e6725-111">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="e6725-111">**Request URI**</span></span>|<span data-ttu-id="e6725-112">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="e6725-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e6725-113">Télécharger</span><span class="sxs-lookup"><span data-stu-id="e6725-113">GET</span></span>  <br/> |<span data-ttu-id="e6725-114">https://\<Portal\>/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="e6725-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="e6725-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="e6725-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="e6725-116">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="e6725-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="e6725-117">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="e6725-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e6725-118">Le corps de la **requête** .</span><span class="sxs-lookup"><span data-stu-id="e6725-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="e6725-119">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="e6725-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="e6725-120">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="e6725-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="e6725-121">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="e6725-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e6725-122">Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="e6725-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e6725-123">Cet exemple n’affiche que les deux premiers éléments de chaque groupe d’éléments cube.</span><span class="sxs-lookup"><span data-stu-id="e6725-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
```
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

 <span data-ttu-id="e6725-124">*KPI* -réservé.</span><span class="sxs-lookup"><span data-stu-id="e6725-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="e6725-125">La section KPI d’une charge utile de requête permet d’exécuter une requête afin de renvoyer des valeurs pour les indicateurs de performance clés définis dans le cube.</span><span class="sxs-lookup"><span data-stu-id="e6725-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="e6725-126">Aucun KPI n’existe encore dans le cube QoE.</span><span class="sxs-lookup"><span data-stu-id="e6725-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="e6725-127">*Dimensions* : liste des dimensions pouvant être utilisées dans les sections filtres et axes d’une charge utile de requête pour une opération d’exécution de requête.</span><span class="sxs-lookup"><span data-stu-id="e6725-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="e6725-128">Pour utiliser une dimension dans une expression de filtre, vous devez spécifier un membre de dimension, qui peut être obtenu à l’aide de l’opération obtenir les membres de la dimension.</span><span class="sxs-lookup"><span data-stu-id="e6725-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="e6725-129">*Mesures* : liste des mesures qui pourraient être utilisées dans la section mesures d’une charge utile de requête pour une opération d’exécution de requête.</span><span class="sxs-lookup"><span data-stu-id="e6725-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

