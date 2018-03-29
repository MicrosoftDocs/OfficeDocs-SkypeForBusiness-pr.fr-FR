---
title: Vider le Cache
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Résumé : Découvrez l’opération vider le Cache, ce qui fait partie de l’API de données pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 2356997facfa0057f90ea3d6c8b4cda06add2615
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="clear-cache"></a><span data-ttu-id="6e12e-104">Vider le Cache</span><span class="sxs-lookup"><span data-stu-id="6e12e-104">Clear Cache</span></span>
 
<span data-ttu-id="6e12e-105">**Résumé :** Obtenir des informations sur l’opération vider le Cache, ce qui fait partie de l’API de données pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="6e12e-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="6e12e-106">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6e12e-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6e12e-107">L’opération vider le Cache est la partie de l’API de données pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="6e12e-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="6e12e-108">Vider le Cache</span><span class="sxs-lookup"><span data-stu-id="6e12e-108">Clear Cache</span></span>

<span data-ttu-id="6e12e-109">Opération d’effacement du Cache supprime le cache sur le serveur pour les requêtes et les données.</span><span class="sxs-lookup"><span data-stu-id="6e12e-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="6e12e-110">Cela réinitialisera le cache et nous allons les données actualisées QoE cube par la suite pour les nouvelles demandes.</span><span class="sxs-lookup"><span data-stu-id="6e12e-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="6e12e-111">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="6e12e-111">**Method**</span></span>|<span data-ttu-id="6e12e-112">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="6e12e-112">**Request URI**</span></span>|<span data-ttu-id="6e12e-113">**Version de HTTP**</span><span class="sxs-lookup"><span data-stu-id="6e12e-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6e12e-114">Publier</span><span class="sxs-lookup"><span data-stu-id="6e12e-114">POST</span></span>  <br/> |<span data-ttu-id="6e12e-115">https://\<portal\>/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="6e12e-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="6e12e-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="6e12e-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="6e12e-117">**Les paramètres URI** - None.</span><span class="sxs-lookup"><span data-stu-id="6e12e-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="6e12e-118">**En-têtes de requête** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="6e12e-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6e12e-119">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="6e12e-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="6e12e-120">**Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="6e12e-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="6e12e-121">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="6e12e-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="6e12e-122">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="6e12e-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6e12e-123">**Corps de la réponse** - None.</span><span class="sxs-lookup"><span data-stu-id="6e12e-123">**Response Body** - None.</span></span>
  

