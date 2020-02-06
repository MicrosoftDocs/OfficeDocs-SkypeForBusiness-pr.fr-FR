---
title: Vider le cache
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Résumé : Découvrez l’opération effacer le cache, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 821b02f204c98f5acefe69df1c848c31cd2205b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816883"
---
# <a name="clear-cache"></a><span data-ttu-id="d40be-104">Vider le cache</span><span class="sxs-lookup"><span data-stu-id="d40be-104">Clear Cache</span></span>
 
<span data-ttu-id="d40be-105">**Résumé :** Apprenez-en davantage sur l’opération d’effacement du cache, qui fait partie de l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="d40be-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="d40be-106">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d40be-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d40be-107">L’opération d’effacement du cache fait partie de l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="d40be-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="d40be-108">Vider le cache</span><span class="sxs-lookup"><span data-stu-id="d40be-108">Clear Cache</span></span>

<span data-ttu-id="d40be-109">L’opération d’effacement du cache supprime le cache du serveur pour les requêtes et les données.</span><span class="sxs-lookup"><span data-stu-id="d40be-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="d40be-110">Cette opération a pour réinitialisation le cache et nous obtiendrons de nouvelles données du cube QoE par la suite pour de nouvelles demandes.</span><span class="sxs-lookup"><span data-stu-id="d40be-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="d40be-111">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="d40be-111">**Method**</span></span>|<span data-ttu-id="d40be-112">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="d40be-112">**Request URI**</span></span>|<span data-ttu-id="d40be-113">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="d40be-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d40be-114">Publier</span><span class="sxs-lookup"><span data-stu-id="d40be-114">POST</span></span>  <br/> |<span data-ttu-id="d40be-115">https://\<Portal\>/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="d40be-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="d40be-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="d40be-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="d40be-117">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="d40be-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="d40be-118">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="d40be-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d40be-119">Le corps de la **requête** .</span><span class="sxs-lookup"><span data-stu-id="d40be-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="d40be-120">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="d40be-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="d40be-121">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="d40be-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="d40be-122">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="d40be-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d40be-123">**Corps** de la réponse : aucun.</span><span class="sxs-lookup"><span data-stu-id="d40be-123">**Response Body** - None.</span></span>
  

