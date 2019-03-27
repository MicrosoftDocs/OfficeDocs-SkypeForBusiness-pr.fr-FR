---
title: Vider le cache
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Résumé : Découvrez l’opération vider le Cache, qui fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: c2371a7f99eb37e8e01be919bf6c31b0c9a452cb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889237"
---
# <a name="clear-cache"></a><span data-ttu-id="000f2-104">Vider le cache</span><span class="sxs-lookup"><span data-stu-id="000f2-104">Clear Cache</span></span>
 
<span data-ttu-id="000f2-105">**Résumé :** Obtenir des informations sur l’opération de vider le Cache, ce qui fait partie de l’API de données pour le tableau de bord qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="000f2-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="000f2-106">Tableau de bord de qualité des appels est un outil de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="000f2-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="000f2-107">L’opération de vider le Cache fait partie de l’API de données pour le tableau de bord qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="000f2-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="000f2-108">Vider le cache</span><span class="sxs-lookup"><span data-stu-id="000f2-108">Clear Cache</span></span>

<span data-ttu-id="000f2-109">Opération de Cache Clear supprime le cache sur le serveur pour les requêtes et les données.</span><span class="sxs-lookup"><span data-stu-id="000f2-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="000f2-110">Le cache seront réinitialisés et nous allons les données du cube QoE ultérieurement pour de nouvelles demandes.</span><span class="sxs-lookup"><span data-stu-id="000f2-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="000f2-111">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="000f2-111">**Method**</span></span>|<span data-ttu-id="000f2-112">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="000f2-112">**Request URI**</span></span>|<span data-ttu-id="000f2-113">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="000f2-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="000f2-114">Publier</span><span class="sxs-lookup"><span data-stu-id="000f2-114">POST</span></span>  <br/> |<span data-ttu-id="000f2-115">https://\<portal\>/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="000f2-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="000f2-116">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="000f2-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="000f2-117">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="000f2-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="000f2-118">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="000f2-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="000f2-119">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="000f2-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="000f2-120">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="000f2-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="000f2-121">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="000f2-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="000f2-122">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="000f2-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="000f2-123">**Corps de réponse** - None.</span><span class="sxs-lookup"><span data-stu-id="000f2-123">**Response Body** - None.</span></span>
  

