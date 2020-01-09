---
title: Obtenir les utilisateurs
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Résumé : en savoir plus sur l’opération obtenir les utilisateurs, qui fait partie du service utilisateur. Le service d’utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 6cf2248035c780c2efce6b1f4539a39cd2a5829a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992611"
---
# <a name="get-users"></a><span data-ttu-id="03ff5-105">Obtenir les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="03ff5-105">Get Users</span></span>
 
<span data-ttu-id="03ff5-106">**Résumé :** En savoir plus sur l’opération obtenir les utilisateurs, qui fait partie du service utilisateur.</span><span class="sxs-lookup"><span data-stu-id="03ff5-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="03ff5-107">Le service d’utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="03ff5-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="03ff5-108">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="03ff5-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="03ff5-109">L’opération obtenir les utilisateurs fait partie du service utilisateur dans l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="03ff5-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="03ff5-110">Obtenir les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="03ff5-110">Get Users</span></span>

<span data-ttu-id="03ff5-111">L’accès aux utilisateurs renvoie une liste d’utilisateurs du référentiel.</span><span class="sxs-lookup"><span data-stu-id="03ff5-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="03ff5-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="03ff5-112">**Method**</span></span>|<span data-ttu-id="03ff5-113">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="03ff5-113">**Request URI**</span></span>|<span data-ttu-id="03ff5-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="03ff5-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="03ff5-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="03ff5-115">GET</span></span>  <br/> |<span data-ttu-id="03ff5-116">https://\<Portal\>/QoERepositoryService/Repository/User</span><span class="sxs-lookup"><span data-stu-id="03ff5-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="03ff5-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="03ff5-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="03ff5-118">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="03ff5-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="03ff5-119">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="03ff5-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="03ff5-120">Le corps de la **requête** .</span><span class="sxs-lookup"><span data-stu-id="03ff5-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="03ff5-121">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="03ff5-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="03ff5-122">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="03ff5-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="03ff5-123">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="03ff5-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="03ff5-124">Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="03ff5-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="03ff5-125">Un tableau d’objets utilisateur est retourné.</span><span class="sxs-lookup"><span data-stu-id="03ff5-125">An array of User objects is returned.</span></span> <span data-ttu-id="03ff5-126">Pour plus d’informations sur l’objet utilisateur, voir obtenir de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="03ff5-126">For details about the User object, see Get User.</span></span> 
  
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


