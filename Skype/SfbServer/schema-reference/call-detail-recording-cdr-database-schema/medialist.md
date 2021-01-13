---
title: Table MediaList
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La table MediaList est une table statique qui stocke la liste de divers types de médias.
ms.openlocfilehash: 6f593876a1b42163b6f2e75dbe44c1eb26b2ff16
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813134"
---
# <a name="medialist-table"></a><span data-ttu-id="56044-103">Table MediaList</span><span class="sxs-lookup"><span data-stu-id="56044-103">MediaList table</span></span>
 
<span data-ttu-id="56044-104">La table MediaList est une table statique qui stocke la liste de divers types de médias.</span><span class="sxs-lookup"><span data-stu-id="56044-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="56044-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="56044-105">**Column**</span></span>|<span data-ttu-id="56044-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="56044-106">**Data Type**</span></span>|<span data-ttu-id="56044-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="56044-107">**Key/Index**</span></span>|<span data-ttu-id="56044-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="56044-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="56044-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="56044-109">**MediaId**</span></span> <br/> |<span data-ttu-id="56044-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="56044-110">tinyint</span></span>  <br/> |<span data-ttu-id="56044-111">Primaire</span><span class="sxs-lookup"><span data-stu-id="56044-111">Primary</span></span>  <br/> |<span data-ttu-id="56044-112">Valeurs : 1-7</span><span class="sxs-lookup"><span data-stu-id="56044-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="56044-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="56044-113">**Media**</span></span> <br/> |<span data-ttu-id="56044-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="56044-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="56044-115">Mappage statique des valeurs MediaID et Media :</span><span class="sxs-lookup"><span data-stu-id="56044-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="56044-116">1 – Messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="56044-116">1 -- IM</span></span> <br/>  <span data-ttu-id="56044-117">2 - Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="56044-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="56044-118">3 - Assistance à distance</span><span class="sxs-lookup"><span data-stu-id="56044-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="56044-119">4 - Partage d’application</span><span class="sxs-lookup"><span data-stu-id="56044-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="56044-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="56044-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="56044-121">6 – Vidéo</span><span class="sxs-lookup"><span data-stu-id="56044-121">6 -- Video</span></span> <br/>  <span data-ttu-id="56044-122">7 - Invitation d’application</span><span class="sxs-lookup"><span data-stu-id="56044-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="56044-123">Si vous essayez de déterminer le type de modalité pour les valeurs dans LcsCDR.SessionDetailsView.MediaTypes, vous devez utiliser l’extrait de code join suivant :</span><span class="sxs-lookup"><span data-stu-id="56044-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
