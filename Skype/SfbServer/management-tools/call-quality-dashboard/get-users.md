---
title: Obtenir les utilisateurs
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Résumé : Découvrez l’opération obtenir des utilisateurs, qui fait partie du Service de l’utilisateur. Le Service de l’utilisateur est la partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: ed26614c0fd4b443e9c5d698d1db9467291ca3d0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-users"></a><span data-ttu-id="9a89e-105">Obtenir les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9a89e-105">Get Users</span></span>
 
<span data-ttu-id="9a89e-106">**Résumé :** Obtenir des informations sur l’opération obtenir des utilisateurs, qui fait partie du Service de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9a89e-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="9a89e-107">Le Service de l’utilisateur est la partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="9a89e-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9a89e-108">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9a89e-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9a89e-109">L’opération obtenir des utilisateurs fait partie du Service utilisateur dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="9a89e-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="9a89e-110">Obtenir les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9a89e-110">Get Users</span></span>

<span data-ttu-id="9a89e-111">Obtenir la liste des utilisateurs renvoie des utilisateurs dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="9a89e-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="9a89e-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="9a89e-112">**Method**</span></span>|<span data-ttu-id="9a89e-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="9a89e-113">**Request URI**</span></span>|<span data-ttu-id="9a89e-114">**Version de HTTP**</span><span class="sxs-lookup"><span data-stu-id="9a89e-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9a89e-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="9a89e-115">GET</span></span>  <br/> |<span data-ttu-id="9a89e-116">https://\<portal\>/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="9a89e-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="9a89e-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9a89e-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9a89e-118">**Les paramètres URI** - None.</span><span class="sxs-lookup"><span data-stu-id="9a89e-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9a89e-119">**En-têtes de requête** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="9a89e-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9a89e-120">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="9a89e-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="9a89e-121">**Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="9a89e-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9a89e-122">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="9a89e-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="9a89e-123">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="9a89e-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9a89e-124">**Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="9a89e-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9a89e-125">Un tableau d’objets utilisateur est retourné.</span><span class="sxs-lookup"><span data-stu-id="9a89e-125">An array of User objects is returned.</span></span> <span data-ttu-id="9a89e-126">Pour plus d’informations sur l’objet utilisateur, consultez obtenir de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9a89e-126">For details about the User object, see Get User.</span></span> 
  
```
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]

```


