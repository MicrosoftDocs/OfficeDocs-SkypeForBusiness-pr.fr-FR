---
title: Obtenir des données de l’intégration de la dernières
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Résumé : Découvrez l’opération obtenir les données de l’intégration de la dernière, qui fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: a5b6ee83cab333ebbacbd4986d6550b60dfa65dd
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296364"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="130ca-104">Obtenir des données de l’intégration de la dernières</span><span class="sxs-lookup"><span data-stu-id="130ca-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="130ca-105">**Résumé :** Obtenir des informations sur l’opération obtenir les données de l’intégration de la dernière, qui fait partie de l’API de données pour le tableau de bord qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="130ca-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="130ca-106">Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="130ca-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="130ca-107">L’opération obtenir les données de l’intégration de la dernière fait partie de l’API de données pour le tableau de bord qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="130ca-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="130ca-108">Obtenir des données de l’intégration de la dernières</span><span class="sxs-lookup"><span data-stu-id="130ca-108">Get Last Integration Data</span></span>

<span data-ttu-id="130ca-109">Obtenir les données de l’intégration de la dernière opération renvoie la liste des derniers 5 réussite/échec de l’archivage et le traitement du cube.</span><span class="sxs-lookup"><span data-stu-id="130ca-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="130ca-110">Cette fonctionnalité est désactivée par défaut et il doit être activé en configurant l’API de données.</span><span class="sxs-lookup"><span data-stu-id="130ca-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="130ca-111">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="130ca-111">**Method**</span></span>|<span data-ttu-id="130ca-112">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="130ca-112">**Request URI**</span></span>|<span data-ttu-id="130ca-113">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="130ca-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="130ca-114">Télécharger</span><span class="sxs-lookup"><span data-stu-id="130ca-114">GET</span></span>  <br/> |<span data-ttu-id="130ca-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="130ca-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="130ca-116">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="130ca-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="130ca-117">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="130ca-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="130ca-118">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="130ca-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="130ca-119">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="130ca-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="130ca-120">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="130ca-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="130ca-121">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="130ca-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="130ca-122">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="130ca-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="130ca-123">**Corps de réponse** - Voici un état de journal exemple.</span><span class="sxs-lookup"><span data-stu-id="130ca-123">**Response Body** - Below is a sample log status.</span></span>
  
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