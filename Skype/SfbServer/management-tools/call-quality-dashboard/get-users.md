---
title: Obtenir les utilisateurs
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Résumé : en savoir plus sur l’opération obtenir les utilisateurs, qui fait partie du service utilisateur. Le service d’utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 81d261a49798ef49d4a1d693681b4497652cf395
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816723"
---
# <a name="get-users"></a><span data-ttu-id="163c0-105">Obtenir les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="163c0-105">Get Users</span></span>
 
<span data-ttu-id="163c0-106">**Résumé :** En savoir plus sur l’opération obtenir les utilisateurs, qui fait partie du service utilisateur.</span><span class="sxs-lookup"><span data-stu-id="163c0-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="163c0-107">Le service d’utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="163c0-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="163c0-108">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="163c0-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="163c0-109">L’opération obtenir les utilisateurs fait partie du service utilisateur dans l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="163c0-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="163c0-110">Obtenir les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="163c0-110">Get Users</span></span>

<span data-ttu-id="163c0-111">L’accès aux utilisateurs renvoie une liste d’utilisateurs du référentiel.</span><span class="sxs-lookup"><span data-stu-id="163c0-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="163c0-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="163c0-112">**Method**</span></span>|<span data-ttu-id="163c0-113">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="163c0-113">**Request URI**</span></span>|<span data-ttu-id="163c0-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="163c0-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="163c0-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="163c0-115">GET</span></span>  <br/> |<span data-ttu-id="163c0-116">https://\<Portal\>/QoERepositoryService/Repository/User</span><span class="sxs-lookup"><span data-stu-id="163c0-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="163c0-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="163c0-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="163c0-118">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="163c0-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="163c0-119">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="163c0-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="163c0-120">Le corps de la **requête** .</span><span class="sxs-lookup"><span data-stu-id="163c0-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="163c0-121">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="163c0-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="163c0-122">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="163c0-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="163c0-123">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="163c0-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="163c0-124">Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="163c0-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="163c0-125">Un tableau d’objets utilisateur est retourné.</span><span class="sxs-lookup"><span data-stu-id="163c0-125">An array of User objects is returned.</span></span> <span data-ttu-id="163c0-126">Pour plus d’informations sur l’objet utilisateur, voir obtenir de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="163c0-126">For details about the User object, see Get User.</span></span> 
  
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


