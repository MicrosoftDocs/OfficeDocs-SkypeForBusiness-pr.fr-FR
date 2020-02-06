---
title: Obtenir les données de la dernière intégration
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
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Résumé : Découvrez l’opération obtenir les dernières données d’intégration, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: a3b66114f457e48b169419baddbaa4e4dc8c0764
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816773"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="4e387-104">Obtenir les données de la dernière intégration</span><span class="sxs-lookup"><span data-stu-id="4e387-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="4e387-105">**Résumé :** Apprenez-en davantage sur la dernière opération d’obtention des données d’intégration, qui fait partie de l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="4e387-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="4e387-106">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="4e387-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4e387-107">L’opération Get Last Data Integration fait partie de l’API de données pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="4e387-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="4e387-108">Obtenir les données de la dernière intégration</span><span class="sxs-lookup"><span data-stu-id="4e387-108">Get Last Integration Data</span></span>

<span data-ttu-id="4e387-109">Obtenir la dernière opération d’intégration de données renvoie la liste des 5 dernières réussites ou échecs d’archivage et de traitement du cube.</span><span class="sxs-lookup"><span data-stu-id="4e387-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="4e387-110">Cette fonctionnalité est désactivée par défaut et doit être activée en configurant l’API de données.</span><span class="sxs-lookup"><span data-stu-id="4e387-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="4e387-111">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="4e387-111">**Method**</span></span>|<span data-ttu-id="4e387-112">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="4e387-112">**Request URI**</span></span>|<span data-ttu-id="4e387-113">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="4e387-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4e387-114">Télécharger</span><span class="sxs-lookup"><span data-stu-id="4e387-114">GET</span></span>  <br/> |<span data-ttu-id="4e387-115">https://\<Portal\>/QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="4e387-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="4e387-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="4e387-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="4e387-117">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="4e387-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="4e387-118">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="4e387-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4e387-119">Le corps de la **requête** .</span><span class="sxs-lookup"><span data-stu-id="4e387-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="4e387-120">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="4e387-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="4e387-121">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="4e387-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="4e387-122">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="4e387-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4e387-123">Le corps de la réponse : Voici un exemple d’état **du** journal.</span><span class="sxs-lookup"><span data-stu-id="4e387-123">**Response Body** - Below is a sample log status.</span></span>
  
```
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
