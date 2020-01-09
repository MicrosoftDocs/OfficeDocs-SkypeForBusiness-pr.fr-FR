---
title: Obtenir un utilisateur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Résumé : Découvrez la procédure d’obtention d’un utilisateur, qui fait partie du service utilisateur. Le service d’utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 09dcbbaeaae98ed7b01f3d710cfda23aa5fa986f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992621"
---
# <a name="get-user"></a><span data-ttu-id="defd5-105">Obtenir un utilisateur</span><span class="sxs-lookup"><span data-stu-id="defd5-105">Get User</span></span>
 
<span data-ttu-id="defd5-106">**Résumé :** En savoir plus sur l’opération obtenir l’utilisateur, qui fait partie du service utilisateur.</span><span class="sxs-lookup"><span data-stu-id="defd5-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="defd5-107">Le service d’utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="defd5-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="defd5-108">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="defd5-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="defd5-109">L’opération obtenir les utilisateurs fait partie du service utilisateur dans l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="defd5-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="defd5-110">Obtenir un utilisateur</span><span class="sxs-lookup"><span data-stu-id="defd5-110">Get User</span></span>

<span data-ttu-id="defd5-111">Obtenir renvoie un enregistrement utilisateur du référentiel.</span><span class="sxs-lookup"><span data-stu-id="defd5-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="defd5-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="defd5-112">**Method**</span></span>|<span data-ttu-id="defd5-113">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="defd5-113">**Request URI**</span></span>|<span data-ttu-id="defd5-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="defd5-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="defd5-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="defd5-115">GET</span></span>  <br/> |<span data-ttu-id="defd5-116">https://\<Portal\>/QoERepositoryService/Repository/User/{userid}</span><span class="sxs-lookup"><span data-stu-id="defd5-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="defd5-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="defd5-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="defd5-118">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="defd5-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="defd5-119">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="defd5-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="defd5-120">Le corps de la **requête** .</span><span class="sxs-lookup"><span data-stu-id="defd5-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="defd5-121">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="defd5-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="defd5-122">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="defd5-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="defd5-123">Si vous n’avez pas trouvé d’ID utilisateur spécifié, le code d’État 404 (introuvable) est renvoyé.</span><span class="sxs-lookup"><span data-stu-id="defd5-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="defd5-124">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="defd5-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="defd5-125">Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="defd5-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="defd5-126">*ID de* l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="defd5-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="defd5-127">*LoginName* -identification de l’utilisateur externe pour les utilisateurs normaux.</span><span class="sxs-lookup"><span data-stu-id="defd5-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="defd5-128">Si l’authentification Windows est utilisée pour authentifier les utilisateurs, il peut s’agir d’un nom de domaine complet (FQDN) de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="defd5-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="defd5-129">*defaultItemId* -ID de l’élément par défaut de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="defd5-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="defd5-130">L’élément par défaut est l’élément le plus élevé qui est associé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="defd5-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="defd5-131">Pour accéder à l’élément par défaut, vous pouvez accéder à tous les autres éléments de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="defd5-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="defd5-132">Fournissez `defaultItemId` la valeur pour obtenir l’opération d’élément permettant de récupérer les détails de l’élément par défaut.</span><span class="sxs-lookup"><span data-stu-id="defd5-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

