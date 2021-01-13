---
title: Obtention d’un paramètre utilisateur
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Résumé : Découvrez l’opération Obtenir les paramètres utilisateur, qui fait partie du service paramètres utilisateur. Le service paramètres utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832484"
---
# <a name="get-user-setting"></a><span data-ttu-id="2b2a7-105">Obtention d’un paramètre utilisateur</span><span class="sxs-lookup"><span data-stu-id="2b2a7-105">Get User Setting</span></span>
 
<span data-ttu-id="2b2a7-106">**Résumé :** Découvrez l’opération Obtenir les paramètres utilisateur, qui fait partie du service paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2b2a7-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="2b2a7-107">Le service paramètres utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="2b2a7-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="2b2a7-108">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2b2a7-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="2b2a7-109">L’opération Obtenir les paramètres utilisateur fait partie du service paramètres utilisateur dans l’API référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="2b2a7-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="2b2a7-110">Obtention d’un paramètre utilisateur</span><span class="sxs-lookup"><span data-stu-id="2b2a7-110">Get User Setting</span></span>

<span data-ttu-id="2b2a7-111">Obtenir le paramètre utilisateur renvoie un paramètre utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="2b2a7-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="2b2a7-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="2b2a7-112">**Method**</span></span>|<span data-ttu-id="2b2a7-113">**URI de demande**</span><span class="sxs-lookup"><span data-stu-id="2b2a7-113">**Request URI**</span></span>|<span data-ttu-id="2b2a7-114">**HTTP Version**</span><span class="sxs-lookup"><span data-stu-id="2b2a7-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2b2a7-115">GET</span><span class="sxs-lookup"><span data-stu-id="2b2a7-115">GET</span></span>  <br/> |<span data-ttu-id="2b2a7-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}</span><span class="sxs-lookup"><span data-stu-id="2b2a7-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="2b2a7-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="2b2a7-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="2b2a7-118">**Paramètres d’URI** - Aucun.</span><span class="sxs-lookup"><span data-stu-id="2b2a7-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="2b2a7-119">**En-têtes de requête** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="2b2a7-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="2b2a7-120">**Corps de la** demande - Aucun.</span><span class="sxs-lookup"><span data-stu-id="2b2a7-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="2b2a7-121">**Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="2b2a7-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="2b2a7-122">**Code d’état** : une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="2b2a7-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="2b2a7-123">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="2b2a7-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="2b2a7-124">**Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="2b2a7-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="2b2a7-125">*userId*  : ID de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2b2a7-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="2b2a7-126">*key*  - Clé du paramètre.</span><span class="sxs-lookup"><span data-stu-id="2b2a7-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="2b2a7-127">*valeur*  - Valeur du paramètre.</span><span class="sxs-lookup"><span data-stu-id="2b2a7-127">*value*  - Value of the setting.</span></span>
  

