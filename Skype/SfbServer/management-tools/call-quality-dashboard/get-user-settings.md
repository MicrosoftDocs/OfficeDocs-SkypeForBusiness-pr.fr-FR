---
title: Obtention des paramètres utilisateur
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Résumé : Découvrez l’opération obtenir les paramètres utilisateur, qui fait partie du Service de paramètres utilisateur. Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 3c94f02f305ee2f779b6a31ef78bea875d462cbf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889020"
---
# <a name="get-user-settings"></a><span data-ttu-id="49cd3-105">Obtention des paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="49cd3-105">Get User Settings</span></span>
 
<span data-ttu-id="49cd3-106">**Résumé :** Obtenir des informations sur l’opération obtenir les paramètres utilisateur, qui fait partie du Service de paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="49cd3-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="49cd3-107">Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="49cd3-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="49cd3-108">Tableau de bord de qualité des appels est un outil de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="49cd3-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="49cd3-109">L’opération obtenir les paramètres utilisateur fait partie du Service de paramètres utilisateur de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="49cd3-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="49cd3-110">Obtention des paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="49cd3-110">Get User Settings</span></span>

<span data-ttu-id="49cd3-111">Obtenir les paramètres utilisateur renvoie une liste des paramètres pour un utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="49cd3-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="49cd3-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="49cd3-112">**Method**</span></span>|<span data-ttu-id="49cd3-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="49cd3-113">**Request URI**</span></span>|<span data-ttu-id="49cd3-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="49cd3-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="49cd3-115">Avoir</span><span class="sxs-lookup"><span data-stu-id="49cd3-115">GET</span></span>  <br/> |<span data-ttu-id="49cd3-116">https://\<portal\>/QoERepositoryService/référentiel/utilisateur / {userId} / définition</span><span class="sxs-lookup"><span data-stu-id="49cd3-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="49cd3-117">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="49cd3-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="49cd3-118">**Paramètres de l’URI**</span><span class="sxs-lookup"><span data-stu-id="49cd3-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="49cd3-119">*efficace* : facultatif.</span><span class="sxs-lookup"><span data-stu-id="49cd3-119">*effective*  - Optional.</span></span> <span data-ttu-id="49cd3-120">Ce paramètre s’applique uniquement lorsque la valeur par défaut des ID utilisateur spécial est utilisé.</span><span class="sxs-lookup"><span data-stu-id="49cd3-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="49cd3-121">Dans les autres cas, il sera ignoré.</span><span class="sxs-lookup"><span data-stu-id="49cd3-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="49cd3-122">`True`Renvoie les paramètres utilisateur efficaces et `false` renvoie uniquement les paramètres utilisateur (par défaut).</span><span class="sxs-lookup"><span data-stu-id="49cd3-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="49cd3-123">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="49cd3-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="49cd3-124">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="49cd3-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="49cd3-125">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="49cd3-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="49cd3-126">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="49cd3-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="49cd3-127">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="49cd3-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="49cd3-128">**Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="49cd3-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
