---
title: Obtention d’un paramètre utilisateur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Résumé: en savoir plus sur l’opération Get User Setting, qui fait partie du service de paramètres utilisateur. Le service de paramètres utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 295e12405eb6a7ebbf45b87e3a06f3a745b90bad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274652"
---
# <a name="get-user-setting"></a><span data-ttu-id="007af-105">Obtention d’un paramètre utilisateur</span><span class="sxs-lookup"><span data-stu-id="007af-105">Get User Setting</span></span>
 
<span data-ttu-id="007af-106">**Résumé:** Apprenez-en davantage sur l’opération Get User Setting, qui fait partie du service de paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="007af-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="007af-107">Le service de paramètres utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="007af-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="007af-108">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="007af-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="007af-109">L’opération Get User Setting fait partie du service de paramètres utilisateur de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="007af-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="007af-110">Obtention d’un paramètre utilisateur</span><span class="sxs-lookup"><span data-stu-id="007af-110">Get User Setting</span></span>

<span data-ttu-id="007af-111">Le paramètre Get est un paramètre utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="007af-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="007af-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="007af-112">**Method**</span></span>|<span data-ttu-id="007af-113">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="007af-113">**Request URI**</span></span>|<span data-ttu-id="007af-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="007af-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="007af-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="007af-115">GET</span></span>  <br/> |<span data-ttu-id="007af-116">https://\<Portal\>/QoERepositoryService/Repository/User/{userid}/Setting/{Key}</span><span class="sxs-lookup"><span data-stu-id="007af-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="007af-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="007af-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="007af-118">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="007af-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="007af-119">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="007af-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="007af-120">Le corps de la **requête** .</span><span class="sxs-lookup"><span data-stu-id="007af-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="007af-121">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="007af-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="007af-122">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="007af-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="007af-123">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="007af-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="007af-124">Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="007af-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="007af-125">\*\* ID de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="007af-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="007af-126">\*\* clé du paramètre.</span><span class="sxs-lookup"><span data-stu-id="007af-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="007af-127">valeur *valeur* du paramètre.</span><span class="sxs-lookup"><span data-stu-id="007af-127">*value*  - Value of the setting.</span></span>
  

