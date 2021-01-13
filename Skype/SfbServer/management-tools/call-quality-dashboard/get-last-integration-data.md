---
title: Obtenir les données de la dernière intégration
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
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Résumé : Découvrez l’opération Obtenir les dernières données d’intégration, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: c40041e41e04d2bdc62a9eb9fa1eb699697a5b3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832514"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="8c1c1-104">Obtenir les données de la dernière intégration</span><span class="sxs-lookup"><span data-stu-id="8c1c1-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="8c1c1-105">**Résumé :** Découvrez l’opération Obtenir les dernières données d’intégration, qui fait partie de l’API de données pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="8c1c1-106">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="8c1c1-107">L’opération Obtenir les dernières données d’intégration fait partie de l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="8c1c1-108">Obtenir les données de la dernière intégration</span><span class="sxs-lookup"><span data-stu-id="8c1c1-108">Get Last Integration Data</span></span>

<span data-ttu-id="8c1c1-109">L’opération Obtenir les dernières données d’intégration renvoie la liste des 5 derniers succès/échecs de l’archivage et du traitement du cube.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="8c1c1-110">Cette fonctionnalité est désactivée par défaut et doit être activée en configurant l’API de données.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="8c1c1-111">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="8c1c1-111">**Method**</span></span>|<span data-ttu-id="8c1c1-112">**URI de demande**</span><span class="sxs-lookup"><span data-stu-id="8c1c1-112">**Request URI**</span></span>|<span data-ttu-id="8c1c1-113">**HTTP Version**</span><span class="sxs-lookup"><span data-stu-id="8c1c1-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8c1c1-114">GET</span><span class="sxs-lookup"><span data-stu-id="8c1c1-114">GET</span></span>  <br/> |<span data-ttu-id="8c1c1-115">https:// \<portal\> /QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="8c1c1-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="8c1c1-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="8c1c1-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="8c1c1-117">**Paramètres d’URI** - Aucun.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="8c1c1-118">**En-têtes de requête** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8c1c1-119">**Corps de la** demande - Aucun.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="8c1c1-120">**Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="8c1c1-121">**Code d’état** : une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="8c1c1-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="8c1c1-122">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8c1c1-123">**Corps de la** réponse : voici un exemple d’état du journal.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-123">**Response Body** - Below is a sample log status.</span></span>
  
```json
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
