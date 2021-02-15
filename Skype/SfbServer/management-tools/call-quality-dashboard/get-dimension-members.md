---
title: Obtenir les membres de dimension
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Résumé : Découvrez l’opération Obtenir les membres de dimension. L’opération Obtenir les membres de dimension fait partie de l’API de données du tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: ffec3b02a3c876a003adb679a28b0e8f2edb91c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832634"
---
# <a name="get-dimension-members"></a><span data-ttu-id="bf071-105">Obtenir les membres de dimension</span><span class="sxs-lookup"><span data-stu-id="bf071-105">Get Dimension Members</span></span>
 
<span data-ttu-id="bf071-106">**Résumé :** Découvrez l’opération Obtenir les membres de dimension.</span><span class="sxs-lookup"><span data-stu-id="bf071-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="bf071-107">L’opération Obtenir les membres de dimension fait partie de l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="bf071-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="bf071-108">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="bf071-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="bf071-109">L’opération Obtenir les membres de dimension fait partie de l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="bf071-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="bf071-110">Obtenir les membres de dimension</span><span class="sxs-lookup"><span data-stu-id="bf071-110">Get Dimension Members</span></span>

<span data-ttu-id="bf071-111">L’opération Obtenir les membres de dimension renvoie la liste des membres d’une dimension spécifique.</span><span class="sxs-lookup"><span data-stu-id="bf071-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="bf071-112">Il permet également de filtrer la liste des membres et d’obtenir un sous-ensemble, afin de réduire le coût de transfert de câblage.</span><span class="sxs-lookup"><span data-stu-id="bf071-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="bf071-113">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="bf071-113">**Method**</span></span>|<span data-ttu-id="bf071-114">**URI de demande**</span><span class="sxs-lookup"><span data-stu-id="bf071-114">**Request URI**</span></span>|<span data-ttu-id="bf071-115">**HTTP Version**</span><span class="sxs-lookup"><span data-stu-id="bf071-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf071-116">POST</span><span class="sxs-lookup"><span data-stu-id="bf071-116">POST</span></span>  <br/> |<span data-ttu-id="bf071-117">https:// \<portal\> /QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="bf071-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="bf071-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="bf071-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="bf071-119">**Paramètres d’URI** - Aucun.</span><span class="sxs-lookup"><span data-stu-id="bf071-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="bf071-120">**En-têtes de requête** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="bf071-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bf071-121">**Corps de** la demande : contient le nom de la dimension pour qui nous voulons les membres.</span><span class="sxs-lookup"><span data-stu-id="bf071-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="bf071-122">En outre, le nombre maximum de membres renvoyés, en plus de vous pouvez spécifier un filtrage pour limiter les membres renvoyés.</span><span class="sxs-lookup"><span data-stu-id="bf071-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="bf071-123">**Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="bf071-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="bf071-124">**Code d’état** : une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="bf071-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="bf071-125">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="bf071-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bf071-126">**Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON en réponse à une demande de « [StartDate]. Dimension [Month] ».</span><span class="sxs-lookup"><span data-stu-id="bf071-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf071-127">La liste affiche uniquement une petite partie de la liste.</span><span class="sxs-lookup"><span data-stu-id="bf071-127">The list is only showing a small portion of the list.</span></span> 
  
```json
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
