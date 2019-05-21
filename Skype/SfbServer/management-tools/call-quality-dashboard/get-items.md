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
description: 'Résumé: en savoir plus sur l’opération obtenir des éléments, qui fait partie du service d’élément. Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: a1e7e8525df77cd5aacafb6d41316a985fbe9694
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274701"
---
# <a name="get-items"></a><span data-ttu-id="134f9-105">Obtenir des éléments</span><span class="sxs-lookup"><span data-stu-id="134f9-105">Get Items</span></span>
 
<span data-ttu-id="134f9-106">**Résumé:** En savoir plus sur l’opération obtenir les éléments, qui fait partie du service d’élément.</span><span class="sxs-lookup"><span data-stu-id="134f9-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="134f9-107">Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="134f9-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="134f9-108">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="134f9-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="134f9-109">L’opération obtenir les éléments fait partie du service d’élément dans l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="134f9-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="134f9-110">Obtenir des éléments</span><span class="sxs-lookup"><span data-stu-id="134f9-110">Get Items</span></span>

<span data-ttu-id="134f9-111">Get renvoie tous les éléments du référentiel.</span><span class="sxs-lookup"><span data-stu-id="134f9-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="134f9-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="134f9-112">**Method**</span></span>|<span data-ttu-id="134f9-113">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="134f9-113">**Request URI**</span></span>|<span data-ttu-id="134f9-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="134f9-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="134f9-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="134f9-115">GET</span></span>  <br/> |<span data-ttu-id="134f9-116">https://\<Portal\>/QoERepositoryService/Repository/Item</span><span class="sxs-lookup"><span data-stu-id="134f9-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="134f9-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="134f9-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="134f9-118">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="134f9-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="134f9-119">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="134f9-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="134f9-120">Le corps de la **requête** .</span><span class="sxs-lookup"><span data-stu-id="134f9-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="134f9-121">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="134f9-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="134f9-122">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="134f9-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="134f9-123">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="134f9-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="134f9-124">Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="134f9-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="134f9-125">Un tableau d’objets Item est retourné.</span><span class="sxs-lookup"><span data-stu-id="134f9-125">An array of Item objects is returned.</span></span> <span data-ttu-id="134f9-126">Pour plus d’informations sur l’objet élément, voir obtenir un élément.</span><span class="sxs-lookup"><span data-stu-id="134f9-126">For details about Item object, see Get Item.</span></span> 
  
```
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
