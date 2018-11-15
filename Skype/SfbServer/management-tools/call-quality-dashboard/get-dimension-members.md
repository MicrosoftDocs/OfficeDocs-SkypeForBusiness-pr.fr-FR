---
title: Obtenir les membres de Dimension
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Résumé : Découvrez l’opération obtenir les membres de Dimension. L’opération obtenir les membres de Dimension fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 4c53e809d13b1ceb386c6727805402be9dfaf7f8
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532986"
---
# <a name="get-dimension-members"></a><span data-ttu-id="6eec2-105">Obtenir les membres de Dimension</span><span class="sxs-lookup"><span data-stu-id="6eec2-105">Get Dimension Members</span></span>
 
<span data-ttu-id="6eec2-106">**Résumé :** Obtenir des informations sur l’opération obtenir les membres de Dimension.</span><span class="sxs-lookup"><span data-stu-id="6eec2-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="6eec2-107">L’opération obtenir les membres de Dimension fait partie de l’API de données pour le tableau de bord qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="6eec2-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="6eec2-108">Tableau de bord de qualité des appels est un outil de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="6eec2-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6eec2-109">L’opération obtenir les membres de Dimension fait partie de l’API de données pour le tableau de bord qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="6eec2-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="6eec2-110">Obtenir les membres de Dimension</span><span class="sxs-lookup"><span data-stu-id="6eec2-110">Get Dimension Members</span></span>

<span data-ttu-id="6eec2-111">Opération de membres de Dimension Get renvoie la liste des membres d’une dimension spécifique.</span><span class="sxs-lookup"><span data-stu-id="6eec2-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="6eec2-112">Cela donne aussi la possibilité de filtrer la liste des membres et obtenir un sous-ensemble, afin de réduire le coût de transfert filaire.</span><span class="sxs-lookup"><span data-stu-id="6eec2-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="6eec2-113">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="6eec2-113">**Method**</span></span>|<span data-ttu-id="6eec2-114">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="6eec2-114">**Request URI**</span></span>|<span data-ttu-id="6eec2-115">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="6eec2-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6eec2-116">Publier</span><span class="sxs-lookup"><span data-stu-id="6eec2-116">POST</span></span>  <br/> |<span data-ttu-id="6eec2-117">https://\<portal\>/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="6eec2-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="6eec2-118">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="6eec2-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="6eec2-119">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="6eec2-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="6eec2-120">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="6eec2-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6eec2-121">**Corps de demande** - il contient le nom de nous voulons les membres de dimension.</span><span class="sxs-lookup"><span data-stu-id="6eec2-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="6eec2-122">Nombre maximal de membres renvoyés, situé en regard de vous pouvez également spécifier une partie du filtrage pour limiter les membres renvoyés.</span><span class="sxs-lookup"><span data-stu-id="6eec2-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="6eec2-123">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="6eec2-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="6eec2-124">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="6eec2-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="6eec2-125">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="6eec2-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6eec2-126">**Corps de réponse** - Voici une exemple charge utile de réponse dans JSON en réponse à une demande de « [StartDate]. [Mois] » dimension.</span><span class="sxs-lookup"><span data-stu-id="6eec2-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6eec2-127">La liste est visible uniquement une petite partie de la liste.</span><span class="sxs-lookup"><span data-stu-id="6eec2-127">The list is only showing a small portion of the list.</span></span> 
  
```
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