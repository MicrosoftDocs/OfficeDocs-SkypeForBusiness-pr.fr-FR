---
title: Obtenir le journal d’intégration
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Résumé : Découvrez l’opération Obtenir le journal d’intégration, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 69827fa9f3fd3f56843a41867b029a071799ba66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832594"
---
# <a name="get-integration-log"></a><span data-ttu-id="44f0f-104">Obtenir le journal d’intégration</span><span class="sxs-lookup"><span data-stu-id="44f0f-104">Get Integration Log</span></span>
 
<span data-ttu-id="44f0f-105">**Résumé :** Découvrez l’opération Obtenir le journal d’intégration, qui fait partie de l’API de données pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="44f0f-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="44f0f-106">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="44f0f-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="44f0f-107">L’opération Obtenir le journal d’intégration fait partie de l’API de données du tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="44f0f-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="44f0f-108">Obtenir le journal d’intégration</span><span class="sxs-lookup"><span data-stu-id="44f0f-108">Get Integration Log</span></span>

<span data-ttu-id="44f0f-109">L’opération Obtenir le journal d’intégration renvoie une liste d’entrées de journal décrivant les activités dans le traitement du cube QoE.</span><span class="sxs-lookup"><span data-stu-id="44f0f-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="44f0f-110">Cette opération est désactivée par défaut pour des raisons de sécurité.</span><span class="sxs-lookup"><span data-stu-id="44f0f-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="44f0f-111">Lorsqu’elle est désactivée, elle renvoie une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="44f0f-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="44f0f-112">Pour activer cette opération, les administrateurs doivent configurer le web.config pour l’application web hôte de l’API de données.</span><span class="sxs-lookup"><span data-stu-id="44f0f-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="44f0f-113">Méthode</span><span class="sxs-lookup"><span data-stu-id="44f0f-113">Method</span></span>|<span data-ttu-id="44f0f-114">**URI de demande**</span><span class="sxs-lookup"><span data-stu-id="44f0f-114">**Request URI**</span></span>|<span data-ttu-id="44f0f-115">**HTTP Version**</span><span class="sxs-lookup"><span data-stu-id="44f0f-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="44f0f-116">GET</span><span class="sxs-lookup"><span data-stu-id="44f0f-116">GET</span></span>  <br/> |<span data-ttu-id="44f0f-117">https:// \<portal\> /QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="44f0f-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="44f0f-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="44f0f-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="44f0f-119">**Paramètres d’URI** - Aucun.</span><span class="sxs-lookup"><span data-stu-id="44f0f-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="44f0f-120">**En-têtes de requête** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="44f0f-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="44f0f-121">**Corps de la** demande - Aucun.</span><span class="sxs-lookup"><span data-stu-id="44f0f-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="44f0f-122">**Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="44f0f-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="44f0f-123">**Code d’état** : une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="44f0f-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="44f0f-124">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="44f0f-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="44f0f-125">**Corps de la** réponse : voici un exemple de structure d’entrées de journal.</span><span class="sxs-lookup"><span data-stu-id="44f0f-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


