---
title: Obtenir le journal d’intégration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Résumé : Découvrez l’opération obtenir les journaux de l’intégration, qui fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 450122266caa21359b424e3abb76a13476f386c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926099"
---
# <a name="get-integration-log"></a><span data-ttu-id="b574d-104">Obtenir le journal d’intégration</span><span class="sxs-lookup"><span data-stu-id="b574d-104">Get Integration Log</span></span>
 
<span data-ttu-id="b574d-105">**Résumé :** Obtenir des informations sur l’opération obtenir les journaux de l’intégration, qui fait partie de l’API de données pour le tableau de bord qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="b574d-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="b574d-106">Tableau de bord de qualité des appels est un outil de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="b574d-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b574d-107">L’opération obtenir un journal intégration fait partie de l’API de données pour le tableau de bord qualité des appels</span><span class="sxs-lookup"><span data-stu-id="b574d-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="b574d-108">Obtenir le journal d’intégration</span><span class="sxs-lookup"><span data-stu-id="b574d-108">Get Integration Log</span></span>

<span data-ttu-id="b574d-109">Obtenir le journal d’intégration opération retourne une liste d’entrées de journal décrivant les activités dans le QoE Cube.</span><span class="sxs-lookup"><span data-stu-id="b574d-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="b574d-110">Cette opération est désactivée par défaut pour des raisons de sécurité.</span><span class="sxs-lookup"><span data-stu-id="b574d-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="b574d-111">Lorsque désactivée, elle renvoie une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="b574d-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="b574d-112">Pour activer cette opération, les administrateurs doivent configurer le fichier web.config pour l’application web de l’API de données hôte.</span><span class="sxs-lookup"><span data-stu-id="b574d-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="b574d-113">Méthode</span><span class="sxs-lookup"><span data-stu-id="b574d-113">Method</span></span>|<span data-ttu-id="b574d-114">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="b574d-114">**Request URI**</span></span>|<span data-ttu-id="b574d-115">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="b574d-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b574d-116">Avoir</span><span class="sxs-lookup"><span data-stu-id="b574d-116">GET</span></span>  <br/> |<span data-ttu-id="b574d-117">https://\<portal\>/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="b574d-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="b574d-118">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="b574d-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="b574d-119">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="b574d-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="b574d-120">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="b574d-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b574d-121">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="b574d-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="b574d-122">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="b574d-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="b574d-123">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="b574d-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="b574d-124">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="b574d-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b574d-125">**Corps de réponse** - Voici un exemple de structure des entrées du journal.</span><span class="sxs-lookup"><span data-stu-id="b574d-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


