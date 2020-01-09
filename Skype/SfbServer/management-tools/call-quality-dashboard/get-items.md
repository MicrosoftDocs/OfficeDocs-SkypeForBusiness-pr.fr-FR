---
title: Obtenir des éléments
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Résumé : en savoir plus sur l’opération obtenir des éléments, qui fait partie du service d’élément. Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: be93e16750c1a977a6bc3cfc9651e78a043ef563
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992661"
---
# <a name="get-items"></a><span data-ttu-id="57b93-105">Obtenir des éléments</span><span class="sxs-lookup"><span data-stu-id="57b93-105">Get Items</span></span>
 
<span data-ttu-id="57b93-106">**Résumé :** En savoir plus sur l’opération obtenir les éléments, qui fait partie du service d’élément.</span><span class="sxs-lookup"><span data-stu-id="57b93-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="57b93-107">Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="57b93-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="57b93-108">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="57b93-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="57b93-109">L’opération obtenir les éléments fait partie du service d’élément dans l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="57b93-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="57b93-110">Obtenir des éléments</span><span class="sxs-lookup"><span data-stu-id="57b93-110">Get Items</span></span>

<span data-ttu-id="57b93-111">Get renvoie tous les éléments du référentiel.</span><span class="sxs-lookup"><span data-stu-id="57b93-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="57b93-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="57b93-112">**Method**</span></span>|<span data-ttu-id="57b93-113">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="57b93-113">**Request URI**</span></span>|<span data-ttu-id="57b93-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="57b93-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="57b93-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="57b93-115">GET</span></span>  <br/> |<span data-ttu-id="57b93-116">https://\<Portal\>/QoERepositoryService/Repository/Item</span><span class="sxs-lookup"><span data-stu-id="57b93-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="57b93-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="57b93-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="57b93-118">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="57b93-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="57b93-119">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="57b93-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="57b93-120">Le corps de la **requête** .</span><span class="sxs-lookup"><span data-stu-id="57b93-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="57b93-121">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="57b93-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="57b93-122">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="57b93-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="57b93-123">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="57b93-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="57b93-124">Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="57b93-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="57b93-125">Un tableau d’objets Item est retourné.</span><span class="sxs-lookup"><span data-stu-id="57b93-125">An array of Item objects is returned.</span></span> <span data-ttu-id="57b93-126">Pour plus d’informations sur l’objet élément, voir obtenir un élément.</span><span class="sxs-lookup"><span data-stu-id="57b93-126">For details about Item object, see Get Item.</span></span> 
  
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
