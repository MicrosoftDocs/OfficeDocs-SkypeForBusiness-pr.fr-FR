---
title: Obtenir des éléments
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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Résumé : Découvrez l’opération Obtenir des éléments, qui fait partie du service d’élément. Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 7da3ba77e782abe44896a7c1eb51a458d9a7e0b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832534"
---
# <a name="get-items"></a><span data-ttu-id="b6abe-105">Obtenir des éléments</span><span class="sxs-lookup"><span data-stu-id="b6abe-105">Get Items</span></span>
 
<span data-ttu-id="b6abe-106">**Résumé :** Découvrez l’opération Obtenir des éléments, qui fait partie du service d’élément.</span><span class="sxs-lookup"><span data-stu-id="b6abe-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="b6abe-107">Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="b6abe-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="b6abe-108">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b6abe-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b6abe-109">L’opération Obtenir des éléments fait partie du service d’élément dans l’API référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="b6abe-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="b6abe-110">Obtenir des éléments</span><span class="sxs-lookup"><span data-stu-id="b6abe-110">Get Items</span></span>

<span data-ttu-id="b6abe-111">Get Items renvoie tous les éléments du référentiel.</span><span class="sxs-lookup"><span data-stu-id="b6abe-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="b6abe-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="b6abe-112">**Method**</span></span>|<span data-ttu-id="b6abe-113">**URI de demande**</span><span class="sxs-lookup"><span data-stu-id="b6abe-113">**Request URI**</span></span>|<span data-ttu-id="b6abe-114">**HTTP Version**</span><span class="sxs-lookup"><span data-stu-id="b6abe-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b6abe-115">GET</span><span class="sxs-lookup"><span data-stu-id="b6abe-115">GET</span></span>  <br/> |<span data-ttu-id="b6abe-116">https:// \<portal\> /QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="b6abe-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="b6abe-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="b6abe-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="b6abe-118">**Paramètres d’URI** - Aucun.</span><span class="sxs-lookup"><span data-stu-id="b6abe-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="b6abe-119">**En-têtes de requête** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="b6abe-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b6abe-120">**Corps de la** demande - Aucun.</span><span class="sxs-lookup"><span data-stu-id="b6abe-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="b6abe-121">**Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="b6abe-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="b6abe-122">**Code d’état** : une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="b6abe-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="b6abe-123">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="b6abe-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b6abe-124">**Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="b6abe-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6abe-125">Un tableau d’objets Item est renvoyé.</span><span class="sxs-lookup"><span data-stu-id="b6abe-125">An array of Item objects is returned.</span></span> <span data-ttu-id="b6abe-126">Pour plus d’informations sur l’objet Item, voir Get Item.</span><span class="sxs-lookup"><span data-stu-id="b6abe-126">For details about Item object, see Get Item.</span></span> 
  
```json
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
