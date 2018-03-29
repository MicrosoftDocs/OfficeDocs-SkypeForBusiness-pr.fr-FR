---
title: Obtenir l’utilisateur
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Résumé : Découvrez l’opération obtenir l’utilisateur, qui fait partie du Service de l’utilisateur. Le Service de l’utilisateur est la partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: e3863819ea15a1039a3a02b1a35cfc7326af7e1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-user"></a><span data-ttu-id="0c634-105">Obtenir l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="0c634-105">Get User</span></span>
 
<span data-ttu-id="0c634-106">**Résumé :** Obtenir des informations sur l’opération de l’utilisateur d’obtenir, qui fait partie du Service de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0c634-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="0c634-107">Le Service de l’utilisateur est la partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="0c634-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="0c634-108">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0c634-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0c634-109">L’opération obtenir des utilisateurs fait partie du Service utilisateur dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="0c634-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="0c634-110">Obtenir l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="0c634-110">Get User</span></span>

<span data-ttu-id="0c634-111">Obtenir les retours utilisateur un enregistrement d’utilisateur à partir du référentiel.</span><span class="sxs-lookup"><span data-stu-id="0c634-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="0c634-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="0c634-112">**Method**</span></span>|<span data-ttu-id="0c634-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="0c634-113">**Request URI**</span></span>|<span data-ttu-id="0c634-114">**Version de HTTP**</span><span class="sxs-lookup"><span data-stu-id="0c634-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0c634-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="0c634-115">GET</span></span>  <br/> |<span data-ttu-id="0c634-116">https://\<portal\>{/QoERepositoryService/repository/utilisateur/ID utilisateur}</span><span class="sxs-lookup"><span data-stu-id="0c634-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="0c634-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="0c634-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0c634-118">**Les paramètres URI** - None.</span><span class="sxs-lookup"><span data-stu-id="0c634-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0c634-119">**En-têtes de requête** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="0c634-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0c634-120">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="0c634-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="0c634-121">**Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="0c634-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0c634-122">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="0c634-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="0c634-123">Si un utilisateur spécifié QU'ID n’est pas trouvé, il renvoie le code d’état 404 (introuvable).</span><span class="sxs-lookup"><span data-stu-id="0c634-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="0c634-124">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="0c634-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0c634-125">**Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="0c634-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}

```

 <span data-ttu-id="0c634-126">*pseudo* - ID de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0c634-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="0c634-127">*loginName* - identification de l’utilisateur externe pour les utilisateurs normaux.</span><span class="sxs-lookup"><span data-stu-id="0c634-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="0c634-128">Si l’authentification Windows est utilisée pour authentifier les utilisateurs, cela peut être un nom de domaine complet de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0c634-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="0c634-129">*defaultItemId* - ID de l’élément par défaut pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0c634-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="0c634-130">L’élément par défaut est l’élément supérieur qui est associée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0c634-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="0c634-131">Tous les autres éléments que cet utilisateur peuvent être parcourus à partir de l’élément par défaut.</span><span class="sxs-lookup"><span data-stu-id="0c634-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c634-132">Fournir le `defaultItemId` valeur à opération obtenir l’élément à récupérer les détails de l’élément par défaut.</span><span class="sxs-lookup"><span data-stu-id="0c634-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

