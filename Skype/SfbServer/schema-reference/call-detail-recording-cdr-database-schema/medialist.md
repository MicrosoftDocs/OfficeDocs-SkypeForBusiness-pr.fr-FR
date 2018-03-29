---
title: Table MediaList
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La table MediaList est une table statique qui stocke la liste de divers types de médias.
ms.openlocfilehash: b44a6dd8a4263f50cd187b6c4b154815e1e6350a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="medialist-table"></a><span data-ttu-id="da138-103">Table MediaList</span><span class="sxs-lookup"><span data-stu-id="da138-103">MediaList table</span></span>
 
<span data-ttu-id="da138-104">La table MediaList est une table statique qui stocke la liste de divers types de médias.</span><span class="sxs-lookup"><span data-stu-id="da138-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="da138-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="da138-105">**Column**</span></span>|<span data-ttu-id="da138-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="da138-106">**Data Type**</span></span>|<span data-ttu-id="da138-107">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="da138-107">**Key/Index**</span></span>|<span data-ttu-id="da138-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="da138-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="da138-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="da138-109">**MediaId**</span></span> <br/> |<span data-ttu-id="da138-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="da138-110">tinyint</span></span>  <br/> |<span data-ttu-id="da138-111">Principal</span><span class="sxs-lookup"><span data-stu-id="da138-111">Primary</span></span>  <br/> |<span data-ttu-id="da138-112">Valeur : 1-7</span><span class="sxs-lookup"><span data-stu-id="da138-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="da138-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="da138-113">**Media**</span></span> <br/> |<span data-ttu-id="da138-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="da138-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="da138-115">Mappage statique de MediaID et des valeurs média :</span><span class="sxs-lookup"><span data-stu-id="da138-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="da138-116">1 – Messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="da138-116">1 -- IM</span></span> <br/>  <span data-ttu-id="da138-117">2 - fichier transfert</span><span class="sxs-lookup"><span data-stu-id="da138-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="da138-118">3 - Assistance à distance</span><span class="sxs-lookup"><span data-stu-id="da138-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="da138-119">4 - application partage</span><span class="sxs-lookup"><span data-stu-id="da138-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="da138-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="da138-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="da138-121">6 – Vidéo</span><span class="sxs-lookup"><span data-stu-id="da138-121">6 -- Video</span></span> <br/>  <span data-ttu-id="da138-122">7 - invitation de app</span><span class="sxs-lookup"><span data-stu-id="da138-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="da138-123">Si vous tentez de déterminer le type de modalité pour les valeurs dans LcsCDR.SessionDetailsView.MediaTypes, vous devrez utiliser l’extrait de Joindre suivant : </span><span class="sxs-lookup"><span data-stu-id="da138-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```


