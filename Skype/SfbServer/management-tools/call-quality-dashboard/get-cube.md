---
title: Obtenir le Cube
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Résumé : Découvrez l’opération obtenir un Cube, qui fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 228ebd8f9bcb6db919f418ef9809bce1b3eb7f90
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532466"
---
# <a name="get-cube"></a><span data-ttu-id="9705f-104">Obtenir le Cube</span><span class="sxs-lookup"><span data-stu-id="9705f-104">Get Cube</span></span>
 
<span data-ttu-id="9705f-105">**Résumé :** Obtenir des informations sur l’opération obtenir un Cube, qui fait partie de l’API de données pour le tableau de bord qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="9705f-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="9705f-106">Tableau de bord de qualité des appels est un outil de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="9705f-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9705f-107">L’opération obtenir le Cube fait partie de l’API de données pour le tableau de bord qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="9705f-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="9705f-108">Obtenir le Cube</span><span class="sxs-lookup"><span data-stu-id="9705f-108">Get Cube</span></span>

<span data-ttu-id="9705f-109">Opération de Cube Get renvoie la liste des dimensions disponibles et des mesures.</span><span class="sxs-lookup"><span data-stu-id="9705f-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="9705f-110">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="9705f-110">**Method**</span></span>|<span data-ttu-id="9705f-111">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="9705f-111">**Request URI**</span></span>|<span data-ttu-id="9705f-112">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="9705f-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9705f-113">Télécharger</span><span class="sxs-lookup"><span data-stu-id="9705f-113">GET</span></span>  <br/> |<span data-ttu-id="9705f-114">https://\<portal\>/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="9705f-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="9705f-115">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="9705f-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9705f-116">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="9705f-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9705f-117">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="9705f-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9705f-118">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="9705f-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="9705f-119">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="9705f-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9705f-120">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="9705f-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="9705f-121">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="9705f-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9705f-122">**Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="9705f-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9705f-123">Cet exemple affiche uniquement les deux premiers éléments de chaque groupes d’éléments de Cube.</span><span class="sxs-lookup"><span data-stu-id="9705f-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
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

 <span data-ttu-id="9705f-124">*Indicateurs de performance clés* - en réservé.</span><span class="sxs-lookup"><span data-stu-id="9705f-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="9705f-125">La section des indicateurs de performance clés d’une charge utile de demande permet exécuter la requête renvoyer des valeurs pour les indicateurs de performance clés définis dans le cube.</span><span class="sxs-lookup"><span data-stu-id="9705f-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="9705f-126">Aucun indicateurs de performance clés n’existent encore dans le QoE Cube.</span><span class="sxs-lookup"><span data-stu-id="9705f-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="9705f-127">*Dimensions* - la liste des dimensions qui peut être utilisé dans les sections de filtres et les Dimensions d’une charge utile de demande pour l’opération d’exécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="9705f-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="9705f-128">Pour utiliser une dimension dans une expression de filtre, vous devez spécifier un membre de dimension, qui peut être obtenu à l’aide d’opération obtenir les membres de Dimension.</span><span class="sxs-lookup"><span data-stu-id="9705f-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="9705f-129">*Des mesures* - la liste des mesures pouvant être utilisées dans la section mesures d’une charge utile de demande pour l’opération d’exécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="9705f-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

