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
ms.openlocfilehash: c9309219399fac30e318f8e112dd82269fff5ac2
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569767"
---
# <a name="medialist-table"></a><span data-ttu-id="e4dac-103">Table MediaList</span><span class="sxs-lookup"><span data-stu-id="e4dac-103">MediaList table</span></span>
 
<span data-ttu-id="e4dac-104">La table MediaList est une table statique qui stocke la liste de divers types de médias.</span><span class="sxs-lookup"><span data-stu-id="e4dac-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="e4dac-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e4dac-105">**Column**</span></span>|<span data-ttu-id="e4dac-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e4dac-106">**Data Type**</span></span>|<span data-ttu-id="e4dac-107">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="e4dac-107">**Key/Index**</span></span>|<span data-ttu-id="e4dac-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e4dac-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e4dac-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="e4dac-109">**MediaId**</span></span> <br/> |<span data-ttu-id="e4dac-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="e4dac-110">tinyint</span></span>  <br/> |<span data-ttu-id="e4dac-111">Principal</span><span class="sxs-lookup"><span data-stu-id="e4dac-111">Primary</span></span>  <br/> |<span data-ttu-id="e4dac-112">Valeur : 1-7</span><span class="sxs-lookup"><span data-stu-id="e4dac-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="e4dac-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="e4dac-113">**Media**</span></span> <br/> |<span data-ttu-id="e4dac-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e4dac-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="e4dac-115">Mappage statique de MediaID et des valeurs média :</span><span class="sxs-lookup"><span data-stu-id="e4dac-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="e4dac-116">1 – Messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="e4dac-116">1 -- IM</span></span> <br/>  <span data-ttu-id="e4dac-117">-2 transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="e4dac-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="e4dac-118">3 - Assistance à distance</span><span class="sxs-lookup"><span data-stu-id="e4dac-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="e4dac-119">-4 partage d’application</span><span class="sxs-lookup"><span data-stu-id="e4dac-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="e4dac-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="e4dac-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="e4dac-121">6 – Vidéo</span><span class="sxs-lookup"><span data-stu-id="e4dac-121">6 -- Video</span></span> <br/>  <span data-ttu-id="e4dac-122">-7 invitation d’application</span><span class="sxs-lookup"><span data-stu-id="e4dac-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="e4dac-123">Si vous tentez de déterminer le type de modalité pour les valeurs dans LcsCDR.SessionDetailsView.MediaTypes, vous devrez utiliser l’extrait de Joindre suivant : </span><span class="sxs-lookup"><span data-stu-id="e4dac-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```