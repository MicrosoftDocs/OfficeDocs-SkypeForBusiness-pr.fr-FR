---
title: Obtenir le journal d’intégration
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Résumé : Découvrez l’opération d’obtention du journal d’intégration, qui fait partie de l’API de données pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: e1d790f4723eaaf716482143f08c78624db47433
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888803"
---
# <a name="get-integration-log"></a><span data-ttu-id="9e267-104">Obtenir le journal d’intégration</span><span class="sxs-lookup"><span data-stu-id="9e267-104">Get Integration Log</span></span>
 
<span data-ttu-id="9e267-105">**Résumé :** Découvrez l’opération d’obtention du journal d’intégration, qui fait partie de l’API de données pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="9e267-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="9e267-106">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9e267-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9e267-107">L’opération obtenir le journal d’intégration fait partie de l’API de données pour le tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="9e267-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="9e267-108">Obtenir le journal d’intégration</span><span class="sxs-lookup"><span data-stu-id="9e267-108">Get Integration Log</span></span>

<span data-ttu-id="9e267-109">L’opération d’obtention du journal d’intégration renvoie une liste des entrées du journal décrivant les activités du traitement du cube QoE.</span><span class="sxs-lookup"><span data-stu-id="9e267-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="9e267-110">Cette opération est désactivée par défaut pour des raisons de sécurité.</span><span class="sxs-lookup"><span data-stu-id="9e267-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="9e267-111">Lorsqu’elle est désactivée, elle renvoie une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="9e267-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="9e267-112">Pour activer cette opération, les administrateurs doivent configurer le fichier Web. config de l’application Web hôte de l’API de données.</span><span class="sxs-lookup"><span data-stu-id="9e267-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="9e267-113">Méthode</span><span class="sxs-lookup"><span data-stu-id="9e267-113">Method</span></span>|<span data-ttu-id="9e267-114">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="9e267-114">**Request URI**</span></span>|<span data-ttu-id="9e267-115">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="9e267-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9e267-116">Télécharger</span><span class="sxs-lookup"><span data-stu-id="9e267-116">GET</span></span>  <br/> |<span data-ttu-id="9e267-117">https://\<Portal\>/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="9e267-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="9e267-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9e267-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9e267-119">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="9e267-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9e267-120">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="9e267-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9e267-121">Le corps de la **requête** .</span><span class="sxs-lookup"><span data-stu-id="9e267-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="9e267-122">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="9e267-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9e267-123">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="9e267-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="9e267-124">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="9e267-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9e267-125">**Corps** de la réponse : Voici un exemple de structure d’entrées du journal.</span><span class="sxs-lookup"><span data-stu-id="9e267-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


