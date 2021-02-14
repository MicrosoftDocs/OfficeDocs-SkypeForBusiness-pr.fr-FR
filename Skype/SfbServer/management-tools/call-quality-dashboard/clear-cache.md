---
title: Vider le cache
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Résumé : Découvrez l’opération Effacer le cache, qui fait partie de l’API de données pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: c9b966bb1e35a5a6255cd75ea6c685daaf220a09
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806414"
---
# <a name="clear-cache"></a><span data-ttu-id="8045a-104">Vider le cache</span><span class="sxs-lookup"><span data-stu-id="8045a-104">Clear Cache</span></span>
 
<span data-ttu-id="8045a-105">**Résumé :** Découvrez l’opération Effacer le cache, qui fait partie de l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="8045a-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="8045a-106">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8045a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="8045a-107">L’opération Effacer le cache fait partie de l’API de données du Tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="8045a-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="8045a-108">Vider le cache</span><span class="sxs-lookup"><span data-stu-id="8045a-108">Clear Cache</span></span>

<span data-ttu-id="8045a-109">L’opération Effacer le cache supprime le cache sur le serveur pour les requêtes et les données.</span><span class="sxs-lookup"><span data-stu-id="8045a-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="8045a-110">Cela réinitialise le cache et nous allons obtenir des données à jour à partir du cube QoE par la suite pour les nouvelles demandes.</span><span class="sxs-lookup"><span data-stu-id="8045a-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="8045a-111">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="8045a-111">**Method**</span></span>|<span data-ttu-id="8045a-112">**URI de demande**</span><span class="sxs-lookup"><span data-stu-id="8045a-112">**Request URI**</span></span>|<span data-ttu-id="8045a-113">**HTTP Version**</span><span class="sxs-lookup"><span data-stu-id="8045a-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8045a-114">POST</span><span class="sxs-lookup"><span data-stu-id="8045a-114">POST</span></span>  <br/> |<span data-ttu-id="8045a-115">https:// \<portal\> /QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="8045a-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="8045a-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="8045a-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="8045a-117">**Paramètres d’URI** - Aucun.</span><span class="sxs-lookup"><span data-stu-id="8045a-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="8045a-118">**En-têtes de requête** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="8045a-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8045a-119">**Corps de la** demande - Aucun.</span><span class="sxs-lookup"><span data-stu-id="8045a-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="8045a-120">**Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="8045a-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="8045a-121">**Code d’état** : une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="8045a-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="8045a-122">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="8045a-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8045a-123">**Corps de la** réponse - Aucun.</span><span class="sxs-lookup"><span data-stu-id="8045a-123">**Response Body** - None.</span></span>
  

