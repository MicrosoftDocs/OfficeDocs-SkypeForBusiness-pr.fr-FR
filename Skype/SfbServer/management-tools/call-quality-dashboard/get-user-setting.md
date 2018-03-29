---
title: Obtenir les paramètres de l’utilisateur
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Résumé : Découvrez l’opération obtenir un paramètre utilisateur, qui fait partie du Service paramètres utilisateur. Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 562886196f06030aef30efbd6f583c29d7f29e59
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-user-setting"></a><span data-ttu-id="9880d-105">Obtenir les paramètres de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="9880d-105">Get User Setting</span></span>
 
<span data-ttu-id="9880d-106">**Résumé :** Obtenir des informations sur l’opération obtenir un paramètre utilisateur, qui fait partie du Service paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9880d-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="9880d-107">Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="9880d-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9880d-108">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9880d-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9880d-109">L’opération obtenir un paramètre utilisateur fait partie du Service de paramètres utilisateur dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="9880d-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="9880d-110">Obtenir les paramètres de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="9880d-110">Get User Setting</span></span>

<span data-ttu-id="9880d-111">Obtenir le paramètre utilisateur retourne un paramètre d’utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="9880d-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="9880d-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="9880d-112">**Method**</span></span>|<span data-ttu-id="9880d-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="9880d-113">**Request URI**</span></span>|<span data-ttu-id="9880d-114">**Version de HTTP**</span><span class="sxs-lookup"><span data-stu-id="9880d-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9880d-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="9880d-115">GET</span></span>  <br/> |<span data-ttu-id="9880d-116">https://\<portal\>{/QoERepositoryService/référentiel/utilisateur/ID utilisateur} /setting/ {clé}</span><span class="sxs-lookup"><span data-stu-id="9880d-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="9880d-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9880d-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9880d-118">**Les paramètres URI** - None.</span><span class="sxs-lookup"><span data-stu-id="9880d-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9880d-119">**En-têtes de requête** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="9880d-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9880d-120">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="9880d-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="9880d-121">**Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="9880d-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9880d-122">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="9880d-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="9880d-123">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="9880d-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9880d-124">**Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="9880d-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}

```

 <span data-ttu-id="9880d-125">*pseudo* - ID de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9880d-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="9880d-126">*clé* - clé du paramètre.</span><span class="sxs-lookup"><span data-stu-id="9880d-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="9880d-127">*valeur* - valeur du paramètre.</span><span class="sxs-lookup"><span data-stu-id="9880d-127">*value*  - Value of the setting.</span></span>
  

