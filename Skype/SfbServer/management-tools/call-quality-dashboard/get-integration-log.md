---
title: Obtenir le journal d’intégration
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Résumé : Découvrez l’opération obtenir journal d’intégration, qui fait partie de l’API de données pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 8ccd4fc299cbf5310a5974d55b181aa1f42255ce
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-integration-log"></a><span data-ttu-id="ee51f-104">Obtenir le journal d’intégration</span><span class="sxs-lookup"><span data-stu-id="ee51f-104">Get Integration Log</span></span>
 
<span data-ttu-id="ee51f-105">**Résumé :** Obtenir des informations sur l’opération obtenir journal d’intégration, qui fait partie de l’API de données pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="ee51f-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="ee51f-106">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ee51f-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ee51f-107">L’opération obtenir le journal intégration fait partie de l’API de données pour appeler le tableau de bord qualité</span><span class="sxs-lookup"><span data-stu-id="ee51f-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="ee51f-108">Obtenir le journal d’intégration</span><span class="sxs-lookup"><span data-stu-id="ee51f-108">Get Integration Log</span></span>

<span data-ttu-id="ee51f-109">Obtenir le journal d’intégration opération retourne une liste d’entrées de journal décrivant les activités QoE cube de traitement.</span><span class="sxs-lookup"><span data-stu-id="ee51f-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="ee51f-110">Cette opération est désactivée par défaut pour des raisons de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ee51f-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="ee51f-111">Lorsque désactivé, il retourne une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="ee51f-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="ee51f-112">Pour activer cette opération, les administrateurs doivent configurer le fichier web.config pour l’application de l’API de données hôte web.</span><span class="sxs-lookup"><span data-stu-id="ee51f-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="ee51f-113">Méthode</span><span class="sxs-lookup"><span data-stu-id="ee51f-113">Method</span></span>|<span data-ttu-id="ee51f-114">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="ee51f-114">**Request URI**</span></span>|<span data-ttu-id="ee51f-115">**Version de HTTP**</span><span class="sxs-lookup"><span data-stu-id="ee51f-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ee51f-116">Télécharger</span><span class="sxs-lookup"><span data-stu-id="ee51f-116">GET</span></span>  <br/> |<span data-ttu-id="ee51f-117">https://\<portal\>/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="ee51f-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="ee51f-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="ee51f-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="ee51f-119">**Les paramètres URI** - None.</span><span class="sxs-lookup"><span data-stu-id="ee51f-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="ee51f-120">**En-têtes de requête** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="ee51f-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ee51f-121">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="ee51f-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="ee51f-122">**Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="ee51f-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="ee51f-123">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="ee51f-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="ee51f-124">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="ee51f-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ee51f-125">**Corps de la réponse** - vous trouverez ci-dessous un exemple de structure d’entrées de journal.</span><span class="sxs-lookup"><span data-stu-id="ee51f-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]

```


