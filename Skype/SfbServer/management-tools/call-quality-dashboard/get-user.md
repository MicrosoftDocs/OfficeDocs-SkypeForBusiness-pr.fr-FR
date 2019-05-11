---
title: Obtenir un utilisateur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Résumé : Découvrez l’opération obtenir un utilisateur, qui fait partie du Service de l’utilisateur. Le Service de l’utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: da07290582c6ccd0ca4f8f331d22e1b51e124a6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930664"
---
# <a name="get-user"></a><span data-ttu-id="34a16-105">Obtenir un utilisateur</span><span class="sxs-lookup"><span data-stu-id="34a16-105">Get User</span></span>
 
<span data-ttu-id="34a16-106">**Résumé :** Obtenir des informations sur l’opération obtenir un utilisateur, qui fait partie du Service de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="34a16-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="34a16-107">Le Service de l’utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="34a16-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="34a16-108">Tableau de bord de qualité des appels est un outil de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="34a16-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="34a16-109">L’opération obtenir des utilisateurs fait partie du Service utilisateur dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="34a16-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="34a16-110">Obtenir un utilisateur</span><span class="sxs-lookup"><span data-stu-id="34a16-110">Get User</span></span>

<span data-ttu-id="34a16-111">Obtenez renvoie utilisateur un enregistrement d’utilisateur à partir du référentiel.</span><span class="sxs-lookup"><span data-stu-id="34a16-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="34a16-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="34a16-112">**Method**</span></span>|<span data-ttu-id="34a16-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="34a16-113">**Request URI**</span></span>|<span data-ttu-id="34a16-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="34a16-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="34a16-115">Avoir</span><span class="sxs-lookup"><span data-stu-id="34a16-115">GET</span></span>  <br/> |<span data-ttu-id="34a16-116">https://\<portal\>/QoERepositoryService/référentiel/utilisateur / {userId}</span><span class="sxs-lookup"><span data-stu-id="34a16-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="34a16-117">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="34a16-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="34a16-118">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="34a16-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="34a16-119">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="34a16-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="34a16-120">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="34a16-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="34a16-121">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="34a16-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="34a16-122">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="34a16-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="34a16-123">Si un utilisateur spécifié QU'ID est introuvable, elle renvoie le code d’état 404 (introuvable).</span><span class="sxs-lookup"><span data-stu-id="34a16-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="34a16-124">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="34a16-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="34a16-125">**Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="34a16-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="34a16-126">*userId* - ID de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="34a16-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="34a16-127">*loginName* - identification des utilisateurs externes pour les utilisateurs classiques.</span><span class="sxs-lookup"><span data-stu-id="34a16-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="34a16-128">Si l’authentification Windows est utilisée pour authentifier les utilisateurs, cela peut être un nom de domaine complet de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="34a16-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="34a16-129">*defaultItemId* - ID de l’élément par défaut pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="34a16-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="34a16-130">L’élément par défaut est l’élément de niveau supérieur qui est associé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="34a16-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="34a16-131">Tous les autres éléments qui qu'appartiennent à cet utilisateur peuvent traverser, de l’élément par défaut.</span><span class="sxs-lookup"><span data-stu-id="34a16-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34a16-132">Fournir le `defaultItemId` valeur pour obtenir un élément operation pour récupérer les détails de l’élément par défaut.</span><span class="sxs-lookup"><span data-stu-id="34a16-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

