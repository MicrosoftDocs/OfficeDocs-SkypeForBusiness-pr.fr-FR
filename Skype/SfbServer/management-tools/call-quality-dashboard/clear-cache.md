---
title: Vider le Cache
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
ms.openlocfilehash: 745fdff57843c42ebf55c1caee011d4b7f4ed250
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531287"
---
# <a name="clear-cache"></a><span data-ttu-id="bf462-104">Vider le Cache</span><span class="sxs-lookup"><span data-stu-id="bf462-104">Clear Cache</span></span>
 
<span data-ttu-id="bf462-105">**Résumé :** Obtenir des informations sur l’opération de vider le Cache, ce qui fait partie de l’API de données pour le tableau de bord qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="bf462-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="bf462-106">Tableau de bord de qualité des appels est un outil de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="bf462-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="bf462-107">L’opération de vider le Cache fait partie de l’API de données pour le tableau de bord qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="bf462-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="bf462-108">Vider le Cache</span><span class="sxs-lookup"><span data-stu-id="bf462-108">Clear Cache</span></span>

<span data-ttu-id="bf462-109">Opération de Cache Clear supprime le cache sur le serveur pour les requêtes et les données.</span><span class="sxs-lookup"><span data-stu-id="bf462-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="bf462-110">Le cache seront réinitialisés et nous allons les données du cube QoE ultérieurement pour de nouvelles demandes.</span><span class="sxs-lookup"><span data-stu-id="bf462-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="bf462-111">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="bf462-111">**Method**</span></span>|<span data-ttu-id="bf462-112">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="bf462-112">**Request URI**</span></span>|<span data-ttu-id="bf462-113">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="bf462-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf462-114">Publier</span><span class="sxs-lookup"><span data-stu-id="bf462-114">POST</span></span>  <br/> |<span data-ttu-id="bf462-115">https://\<portal\>/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="bf462-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="bf462-116">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="bf462-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="bf462-117">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="bf462-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="bf462-118">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="bf462-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bf462-119">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="bf462-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="bf462-120">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="bf462-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="bf462-121">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="bf462-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="bf462-122">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="bf462-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bf462-123">**Corps de réponse** - None.</span><span class="sxs-lookup"><span data-stu-id="bf462-123">**Response Body** - None.</span></span>
  

