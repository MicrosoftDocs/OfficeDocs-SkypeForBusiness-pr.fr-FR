---
title: Obtenir un utilisateur
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Résumé : Découvrez l’opération Obtenir un utilisateur, qui fait partie du service utilisateur. Le service utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: dd2bb5e46ddbe3e65faf441a11e39cbc5429e473
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832414"
---
# <a name="get-user"></a><span data-ttu-id="282f5-105">Obtenir un utilisateur</span><span class="sxs-lookup"><span data-stu-id="282f5-105">Get User</span></span>
 
<span data-ttu-id="282f5-106">**Résumé :** Découvrez l’opération Obtenir un utilisateur, qui fait partie du service utilisateur.</span><span class="sxs-lookup"><span data-stu-id="282f5-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="282f5-107">Le service utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="282f5-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="282f5-108">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="282f5-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="282f5-109">L’opération Obtenir des utilisateurs fait partie du service utilisateur dans l’API référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="282f5-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="282f5-110">Obtenir un utilisateur</span><span class="sxs-lookup"><span data-stu-id="282f5-110">Get User</span></span>

<span data-ttu-id="282f5-111">Get User renvoie un enregistrement utilisateur à partir du référentiel.</span><span class="sxs-lookup"><span data-stu-id="282f5-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="282f5-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="282f5-112">**Method**</span></span>|<span data-ttu-id="282f5-113">**URI de demande**</span><span class="sxs-lookup"><span data-stu-id="282f5-113">**Request URI**</span></span>|<span data-ttu-id="282f5-114">**HTTP Version**</span><span class="sxs-lookup"><span data-stu-id="282f5-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="282f5-115">GET</span><span class="sxs-lookup"><span data-stu-id="282f5-115">GET</span></span>  <br/> |<span data-ttu-id="282f5-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}</span><span class="sxs-lookup"><span data-stu-id="282f5-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="282f5-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="282f5-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="282f5-118">**Paramètres d’URI** - Aucun.</span><span class="sxs-lookup"><span data-stu-id="282f5-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="282f5-119">**En-têtes de requête** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="282f5-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="282f5-120">**Corps de la** demande - Aucun.</span><span class="sxs-lookup"><span data-stu-id="282f5-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="282f5-121">**Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="282f5-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="282f5-122">**Code d’état** : une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="282f5-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="282f5-123">Si un ID utilisateur spécifié est in trouvé, il renvoie le code d’état 404 (In trouvé).</span><span class="sxs-lookup"><span data-stu-id="282f5-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="282f5-124">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="282f5-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="282f5-125">**Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="282f5-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="282f5-126">*userId*  : ID de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="282f5-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="282f5-127">*loginName*  : identification des utilisateurs externes pour les utilisateurs réguliers.</span><span class="sxs-lookup"><span data-stu-id="282f5-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="282f5-128">Si l’authentification Windows est utilisée pour authentifier les utilisateurs, il peut s’agit d’un nom de sujet de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="282f5-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="282f5-129">*defaultItemId*  - ID de l’élément par défaut pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="282f5-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="282f5-130">L’élément par défaut est l’élément le plus haut associé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="282f5-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="282f5-131">Tous les autres éléments dont cet utilisateur est propriétaire peuvent être accédés à partir de l’élément par défaut.</span><span class="sxs-lookup"><span data-stu-id="282f5-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="282f5-132">Fournissez  `defaultItemId` la valeur de l’opération Obtenir un élément pour récupérer les détails de l’élément par défaut.</span><span class="sxs-lookup"><span data-stu-id="282f5-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

