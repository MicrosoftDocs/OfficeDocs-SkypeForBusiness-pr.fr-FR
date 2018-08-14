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
description: 'Résumé : Découvrez l’opération obtenir des utilisateurs, qui fait partie du Service de l’utilisateur. Le Service de l’utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 4d4de424776514479ed2204eeb0a5315a7323662
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569697"
---
# <a name="get-users"></a><span data-ttu-id="9c2a1-105">Obtenir les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9c2a1-105">Get Users</span></span>
 
<span data-ttu-id="9c2a1-106">**Résumé :** Obtenir des informations sur l’opération obtenir des utilisateurs, qui fait partie du Service de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="9c2a1-107">Le Service de l’utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9c2a1-108">Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9c2a1-109">L’opération obtenir des utilisateurs fait partie du Service utilisateur dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="9c2a1-110">Obtenir les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9c2a1-110">Get Users</span></span>

<span data-ttu-id="9c2a1-111">Obtenir la liste des utilisateurs renvoie les utilisateurs dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="9c2a1-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="9c2a1-112">**Method**</span></span>|<span data-ttu-id="9c2a1-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="9c2a1-113">**Request URI**</span></span>|<span data-ttu-id="9c2a1-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="9c2a1-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9c2a1-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="9c2a1-115">GET</span></span>  <br/> |<span data-ttu-id="9c2a1-116">https://\<portal\>/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="9c2a1-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="9c2a1-117">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9c2a1-118">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9c2a1-119">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9c2a1-120">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="9c2a1-121">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9c2a1-122">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="9c2a1-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="9c2a1-123">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9c2a1-124">**Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9c2a1-125">Un tableau d’objets de l’utilisateur est renvoyé.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-125">An array of User objects is returned.</span></span> <span data-ttu-id="9c2a1-126">Pour plus d’informations sur l’objet utilisateur, voir User obtenir.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-126">For details about the User object, see Get User.</span></span> 
  
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


