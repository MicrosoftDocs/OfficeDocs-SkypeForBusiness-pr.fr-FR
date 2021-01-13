---
title: Obtenir un cube
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Résumé : Découvrez l’opération Obtenir un cube, qui fait partie de l’API de données pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: a3527f21bc1751c23bba088ae06c3e6702cb8c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832624"
---
# <a name="get-cube"></a><span data-ttu-id="f3114-104">Obtenir un cube</span><span class="sxs-lookup"><span data-stu-id="f3114-104">Get Cube</span></span>
 
<span data-ttu-id="f3114-105">**Résumé :** Découvrez l’opération Obtenir un cube, qui fait partie de l’API de données pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="f3114-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="f3114-106">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f3114-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="f3114-107">L’opération Obtenir un cube fait partie de l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="f3114-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="f3114-108">Obtenir un cube</span><span class="sxs-lookup"><span data-stu-id="f3114-108">Get Cube</span></span>

<span data-ttu-id="f3114-109">L’opération Obtenir un cube renvoie la liste des dimensions et mesures disponibles.</span><span class="sxs-lookup"><span data-stu-id="f3114-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="f3114-110">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="f3114-110">**Method**</span></span>|<span data-ttu-id="f3114-111">**URI de demande**</span><span class="sxs-lookup"><span data-stu-id="f3114-111">**Request URI**</span></span>|<span data-ttu-id="f3114-112">**HTTP Version**</span><span class="sxs-lookup"><span data-stu-id="f3114-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f3114-113">GET</span><span class="sxs-lookup"><span data-stu-id="f3114-113">GET</span></span>  <br/> |<span data-ttu-id="f3114-114">https:// \<portal\> /QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="f3114-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="f3114-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="f3114-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="f3114-116">**Paramètres d’URI** - Aucun.</span><span class="sxs-lookup"><span data-stu-id="f3114-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="f3114-117">**En-têtes de requête** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="f3114-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f3114-118">**Corps de la** demande - Aucun.</span><span class="sxs-lookup"><span data-stu-id="f3114-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="f3114-119">**Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="f3114-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="f3114-120">**Code d’état** : une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="f3114-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="f3114-121">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="f3114-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f3114-122">**Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="f3114-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f3114-123">Cet exemple montre uniquement les deux premiers éléments de chaque groupe d’éléments Cube.</span><span class="sxs-lookup"><span data-stu-id="f3114-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
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

 <span data-ttu-id="f3114-124">*KPIs*  - Réservé.</span><span class="sxs-lookup"><span data-stu-id="f3114-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="f3114-125">La section Des KPIs d’une charge utile de demande permet à l’opération Exécuter une requête de renvoyer des valeurs pour les KPIs définis dans le cube.</span><span class="sxs-lookup"><span data-stu-id="f3114-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="f3114-126">Il n’existe pas encore d’KPIs dans le cube QoE.</span><span class="sxs-lookup"><span data-stu-id="f3114-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="f3114-127">*Dimensions*  : liste des dimensions qui peuvent être utilisées dans les sections Filtres et dimensions d’une charge utile de requête pour exécuter une requête.</span><span class="sxs-lookup"><span data-stu-id="f3114-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="f3114-128">Pour utiliser une dimension dans une expression de filtre, vous devez spécifier un membre de dimension, qui peut être obtenu à l’aide de l’opération Obtenir les membres de dimension.</span><span class="sxs-lookup"><span data-stu-id="f3114-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="f3114-129">*Mesures :*  liste des mesures qui peuvent être utilisées dans la section Mesures d’une charge utile de demande pour exécuter une opération de requête.</span><span class="sxs-lookup"><span data-stu-id="f3114-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

