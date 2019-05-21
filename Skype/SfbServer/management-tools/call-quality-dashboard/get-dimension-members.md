---
title: Obtenir les membres de dimension
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Résumé: en savoir plus sur l’opération obtenir les membres d’une dimension. L’opération obtenir les membres de la dimension fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: c457e7f3b42aaeb11c35180bc4c1ae6ee42b914e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274750"
---
# <a name="get-dimension-members"></a><span data-ttu-id="b743e-105">Obtenir les membres de dimension</span><span class="sxs-lookup"><span data-stu-id="b743e-105">Get Dimension Members</span></span>
 
<span data-ttu-id="b743e-106">**Résumé:** En savoir plus sur l’opération obtenir les membres d’une dimension.</span><span class="sxs-lookup"><span data-stu-id="b743e-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="b743e-107">L’opération obtenir les membres de la dimension fait partie de l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="b743e-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="b743e-108">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b743e-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b743e-109">L’opération obtenir les membres de la dimension fait partie de l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="b743e-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="b743e-110">Obtenir les membres de dimension</span><span class="sxs-lookup"><span data-stu-id="b743e-110">Get Dimension Members</span></span>

<span data-ttu-id="b743e-111">Opération obtenir les membres d’une dimension renvoie la liste des membres d’une dimension spécifique.</span><span class="sxs-lookup"><span data-stu-id="b743e-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="b743e-112">Vous pouvez également filtrer la liste des membres et obtenir un sous-ensemble afin de réduire le coût de transfert bancaire.</span><span class="sxs-lookup"><span data-stu-id="b743e-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="b743e-113">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="b743e-113">**Method**</span></span>|<span data-ttu-id="b743e-114">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="b743e-114">**Request URI**</span></span>|<span data-ttu-id="b743e-115">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="b743e-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b743e-116">Publier</span><span class="sxs-lookup"><span data-stu-id="b743e-116">POST</span></span>  <br/> |<span data-ttu-id="b743e-117">https://\<Portal\>/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="b743e-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="b743e-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="b743e-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="b743e-119">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="b743e-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="b743e-120">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="b743e-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b743e-121">Le corps de la **requête** contient le nom de la dimension pour laquelle nous voulons les membres.</span><span class="sxs-lookup"><span data-stu-id="b743e-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="b743e-122">Le nombre maximal de membres retourné, à côté de vous pouvez spécifier un filtre pour limiter les membres renvoyés.</span><span class="sxs-lookup"><span data-stu-id="b743e-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
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

 <span data-ttu-id="b743e-123">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="b743e-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="b743e-124">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="b743e-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="b743e-125">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="b743e-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b743e-126">Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON en réponse à une demande de «[DateDébut]. [Mois] "dimension.</span><span class="sxs-lookup"><span data-stu-id="b743e-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b743e-127">La liste affiche uniquement une petite partie de la liste.</span><span class="sxs-lookup"><span data-stu-id="b743e-127">The list is only showing a small portion of the list.</span></span> 
  
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
