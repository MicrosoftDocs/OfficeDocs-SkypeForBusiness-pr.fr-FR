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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Résumé : Découvrez l’opération obtenir les paramètres utilisateur, qui fait partie du Service paramètres utilisateur. Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 55c3247f0412a9ce10927496ee65255129edfd93
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-user-settings"></a><span data-ttu-id="7e485-105">Obtenir les paramètres de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="7e485-105">Get User Settings</span></span>
 
<span data-ttu-id="7e485-106">**Résumé :** Obtenir des informations sur l’opération obtenir les paramètres utilisateur, qui fait partie du Service paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7e485-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="7e485-107">Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="7e485-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="7e485-108">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7e485-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7e485-109">L’opération obtenir les paramètres utilisateur fait partie du Service de paramètres utilisateur dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="7e485-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="7e485-110">Obtenir les paramètres de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="7e485-110">Get User Settings</span></span>

<span data-ttu-id="7e485-111">Paramètres d’utilisateur get retourne une liste de paramètres pour un utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="7e485-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="7e485-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="7e485-112">**Method**</span></span>|<span data-ttu-id="7e485-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="7e485-113">**Request URI**</span></span>|<span data-ttu-id="7e485-114">**Version de HTTP**</span><span class="sxs-lookup"><span data-stu-id="7e485-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7e485-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="7e485-115">GET</span></span>  <br/> |<span data-ttu-id="7e485-116">https://\<portal\>/QoERepositoryService/repository/utilisateur / {ID utilisateur} / définition</span><span class="sxs-lookup"><span data-stu-id="7e485-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="7e485-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="7e485-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="7e485-118">**Paramètres URI**</span><span class="sxs-lookup"><span data-stu-id="7e485-118">**URI Parameters**</span></span>
  
-  <span data-ttu-id="7e485-119">*efficace* : facultatif.</span><span class="sxs-lookup"><span data-stu-id="7e485-119">*effective*  - Optional.</span></span> <span data-ttu-id="7e485-120">Ce paramètre s’applique uniquement lorsque la valeur par défaut des ID utilisateur spécial est utilisé.</span><span class="sxs-lookup"><span data-stu-id="7e485-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="7e485-121">Dans les autres cas, il sera ignoré.</span><span class="sxs-lookup"><span data-stu-id="7e485-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="7e485-122">`True`Renvoie les paramètres d’utilisateur efficace et `false` renvoie simplement les paramètres utilisateur (par défaut).</span><span class="sxs-lookup"><span data-stu-id="7e485-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
 <span data-ttu-id="7e485-123">**En-têtes de requête** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="7e485-123">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7e485-124">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="7e485-124">**Request Body** - None.</span></span>
  
 <span data-ttu-id="7e485-125">**Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="7e485-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="7e485-126">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="7e485-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="7e485-127">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="7e485-127">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7e485-128">**Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="7e485-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
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


