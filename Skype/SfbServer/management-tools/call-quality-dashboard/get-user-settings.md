---
title: Obtention des paramètres utilisateur
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Résumé : en savoir plus sur l’opération obtenir les paramètres d’utilisateur, qui fait partie du service des paramètres utilisateur. Le service de paramètres utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 5b5ad679387866ba6562e031b6d3a42cc68851a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816743"
---
# <a name="get-user-settings"></a><span data-ttu-id="74295-105">Obtention des paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="74295-105">Get User Settings</span></span>
 
<span data-ttu-id="74295-106">**Résumé :** En savoir plus sur l’opération obtenir les paramètres d’utilisateur, qui fait partie du service des paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="74295-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="74295-107">Le service de paramètres utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="74295-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="74295-108">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="74295-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="74295-109">L’opération obtenir les paramètres utilisateur fait partie du service de paramètres utilisateur de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="74295-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="74295-110">Obtention des paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="74295-110">Get User Settings</span></span>

<span data-ttu-id="74295-111">Obtenir les paramètres d’utilisateur renvoie une liste de paramètres pour un utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="74295-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="74295-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="74295-112">**Method**</span></span>|<span data-ttu-id="74295-113">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="74295-113">**Request URI**</span></span>|<span data-ttu-id="74295-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="74295-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="74295-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="74295-115">GET</span></span>  <br/> |<span data-ttu-id="74295-116">https://\<Portal\>/QoERepositoryService/Repository/User/{userid}/Setting</span><span class="sxs-lookup"><span data-stu-id="74295-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="74295-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="74295-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="74295-118">**Paramètres d’URI**</span><span class="sxs-lookup"><span data-stu-id="74295-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="74295-119">*effective* -facultatif.</span><span class="sxs-lookup"><span data-stu-id="74295-119">*effective*  - Optional.</span></span> <span data-ttu-id="74295-120">Ce paramètre s’applique uniquement lorsque la valeur par défaut de l’ID utilisateur spécial est utilisée.</span><span class="sxs-lookup"><span data-stu-id="74295-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="74295-121">Dans les autres cas, elle est ignorée.</span><span class="sxs-lookup"><span data-stu-id="74295-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="74295-122">`True`renvoie des paramètres utilisateur efficaces `false` et renvoie des paramètres utilisateur uniquement (par défaut).</span><span class="sxs-lookup"><span data-stu-id="74295-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="74295-123">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="74295-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="74295-124">Le corps de la **requête** .</span><span class="sxs-lookup"><span data-stu-id="74295-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="74295-125">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="74295-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="74295-126">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="74295-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="74295-127">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="74295-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="74295-128">Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="74295-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
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
