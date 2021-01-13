---
title: Obtenir les utilisateurs
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Résumé : Découvrez l’opération Obtenir des utilisateurs, qui fait partie du service utilisateur. Le service utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: a830663fc97d8fda727d1ebb008d97407796cc7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832424"
---
# <a name="get-users"></a><span data-ttu-id="e7c4c-105">Obtenir les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="e7c4c-105">Get Users</span></span>
 
<span data-ttu-id="e7c4c-106">**Résumé :** Découvrez l’opération Obtenir des utilisateurs, qui fait partie du service utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e7c4c-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="e7c4c-107">Le service utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="e7c4c-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="e7c4c-108">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e7c4c-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="e7c4c-109">L’opération Obtenir des utilisateurs fait partie du service utilisateur dans l’API référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="e7c4c-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="e7c4c-110">Obtenir les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="e7c4c-110">Get Users</span></span>

<span data-ttu-id="e7c4c-111">Obtenir les utilisateurs renvoie une liste d’utilisateurs dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="e7c4c-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="e7c4c-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="e7c4c-112">**Method**</span></span>|<span data-ttu-id="e7c4c-113">**URI de demande**</span><span class="sxs-lookup"><span data-stu-id="e7c4c-113">**Request URI**</span></span>|<span data-ttu-id="e7c4c-114">**HTTP Version**</span><span class="sxs-lookup"><span data-stu-id="e7c4c-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e7c4c-115">GET</span><span class="sxs-lookup"><span data-stu-id="e7c4c-115">GET</span></span>  <br/> |<span data-ttu-id="e7c4c-116">https:// \<portal\> /QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="e7c4c-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="e7c4c-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="e7c4c-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="e7c4c-118">**Paramètres d’URI** - Aucun.</span><span class="sxs-lookup"><span data-stu-id="e7c4c-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="e7c4c-119">**En-têtes de requête** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="e7c4c-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e7c4c-120">**Corps de la** demande - Aucun.</span><span class="sxs-lookup"><span data-stu-id="e7c4c-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="e7c4c-121">**Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="e7c4c-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="e7c4c-122">**Code d’état** : une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="e7c4c-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="e7c4c-123">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="e7c4c-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e7c4c-124">**Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="e7c4c-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7c4c-125">Un tableau d’objets User est renvoyé.</span><span class="sxs-lookup"><span data-stu-id="e7c4c-125">An array of User objects is returned.</span></span> <span data-ttu-id="e7c4c-126">Pour plus d’informations sur l’objet User, voir Get User.</span><span class="sxs-lookup"><span data-stu-id="e7c4c-126">For details about the User object, see Get User.</span></span> 
  
```json
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


