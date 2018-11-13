---
title: Obtenir les paramètres utilisateur
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Résumé : Découvrez l’opération obtenir les paramètres utilisateur, qui fait partie du Service de paramètres utilisateur. Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: a839045197e8b72f72a99fd5fb6e3cf0a724b342
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296088"
---
# <a name="get-user-setting"></a><span data-ttu-id="70559-105">Obtenir les paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="70559-105">Get User Setting</span></span>
 
<span data-ttu-id="70559-106">**Résumé :** Obtenir des informations sur l’opération obtenir les paramètres utilisateur, qui fait partie du Service de paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="70559-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="70559-107">Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="70559-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="70559-108">Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="70559-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="70559-109">L’opération obtenir le paramètre utilisateur fait partie du Service de paramètres utilisateur de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="70559-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="70559-110">Obtenir les paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="70559-110">Get User Setting</span></span>

<span data-ttu-id="70559-111">Obtenir le paramètre utilisateur renvoie un paramètre d’utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="70559-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="70559-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="70559-112">**Method**</span></span>|<span data-ttu-id="70559-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="70559-113">**Request URI**</span></span>|<span data-ttu-id="70559-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="70559-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="70559-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="70559-115">GET</span></span>  <br/> |<span data-ttu-id="70559-116">https://\<portal\>/QoERepositoryService/référentiel/utilisateur / {userId} /setting/ {clé}</span><span class="sxs-lookup"><span data-stu-id="70559-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="70559-117">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="70559-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="70559-118">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="70559-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="70559-119">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="70559-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="70559-120">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="70559-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="70559-121">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="70559-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="70559-122">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="70559-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="70559-123">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="70559-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="70559-124">**Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="70559-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="70559-125">*userId* - ID de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="70559-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="70559-126">*clé* - clé du paramètre.</span><span class="sxs-lookup"><span data-stu-id="70559-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="70559-127">*valeur* : valeur du paramètre.</span><span class="sxs-lookup"><span data-stu-id="70559-127">*value*  - Value of the setting.</span></span>
  

