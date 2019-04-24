---
title: Table MediaList
ms.reviewer: ''
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
ms.openlocfilehash: 72ae6dbb145c3bb284f1090b01585591e4e773bf
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212907"
---
# <a name="medialist-table"></a><span data-ttu-id="56388-103">Table MediaList</span><span class="sxs-lookup"><span data-stu-id="56388-103">MediaList table</span></span>
 
<span data-ttu-id="56388-104">La table MediaList est une table statique qui stocke la liste de divers types de médias.</span><span class="sxs-lookup"><span data-stu-id="56388-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="56388-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="56388-105">**Column**</span></span>|<span data-ttu-id="56388-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="56388-106">**Data Type**</span></span>|<span data-ttu-id="56388-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="56388-107">**Key/Index**</span></span>|<span data-ttu-id="56388-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="56388-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="56388-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="56388-109">**MediaId**</span></span> <br/> |<span data-ttu-id="56388-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="56388-110">tinyint</span></span>  <br/> |<span data-ttu-id="56388-111">Principal</span><span class="sxs-lookup"><span data-stu-id="56388-111">Primary</span></span>  <br/> |<span data-ttu-id="56388-112">Valeur : 1-7</span><span class="sxs-lookup"><span data-stu-id="56388-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="56388-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="56388-113">**Media**</span></span> <br/> |<span data-ttu-id="56388-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="56388-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="56388-115">Mappage statique de MediaID et des valeurs média :</span><span class="sxs-lookup"><span data-stu-id="56388-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="56388-116">1 – Messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="56388-116">1 -- IM</span></span> <br/>  <span data-ttu-id="56388-117">-2 transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="56388-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="56388-118">3 - Assistance à distance</span><span class="sxs-lookup"><span data-stu-id="56388-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="56388-119">-4 partage d’application</span><span class="sxs-lookup"><span data-stu-id="56388-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="56388-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="56388-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="56388-121">6 – Vidéo</span><span class="sxs-lookup"><span data-stu-id="56388-121">6 -- Video</span></span> <br/>  <span data-ttu-id="56388-122">-7 invitation d’application</span><span class="sxs-lookup"><span data-stu-id="56388-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="56388-123">Si vous tentez de déterminer le type de modalité pour les valeurs dans LcsCDR.SessionDetailsView.MediaTypes, vous devrez utiliser l’extrait de Joindre suivant : </span><span class="sxs-lookup"><span data-stu-id="56388-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
