---
title: Table MediaList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: e7d739b27bf45b5f5a21183c30bd5b07108b4a9d
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888513"
---
# <a name="medialist-table"></a><span data-ttu-id="91fff-103">Table MediaList</span><span class="sxs-lookup"><span data-stu-id="91fff-103">MediaList table</span></span>
 
<span data-ttu-id="91fff-104">La table MediaList est une table statique qui stocke la liste de divers types de médias.</span><span class="sxs-lookup"><span data-stu-id="91fff-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="91fff-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="91fff-105">**Column**</span></span>|<span data-ttu-id="91fff-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="91fff-106">**Data Type**</span></span>|<span data-ttu-id="91fff-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="91fff-107">**Key/Index**</span></span>|<span data-ttu-id="91fff-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="91fff-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="91fff-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="91fff-109">**MediaId**</span></span> <br/> |<span data-ttu-id="91fff-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="91fff-110">tinyint</span></span>  <br/> |<span data-ttu-id="91fff-111">Principal</span><span class="sxs-lookup"><span data-stu-id="91fff-111">Primary</span></span>  <br/> |<span data-ttu-id="91fff-112">Valeur : 1-7</span><span class="sxs-lookup"><span data-stu-id="91fff-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="91fff-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="91fff-113">**Media**</span></span> <br/> |<span data-ttu-id="91fff-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91fff-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="91fff-115">Mappage statique de MediaID et des valeurs média :</span><span class="sxs-lookup"><span data-stu-id="91fff-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="91fff-116">1 – Messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="91fff-116">1 -- IM</span></span> <br/>  <span data-ttu-id="91fff-117">2-transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="91fff-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="91fff-118">3-assistance à distance</span><span class="sxs-lookup"><span data-stu-id="91fff-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="91fff-119">Partage d’application 4</span><span class="sxs-lookup"><span data-stu-id="91fff-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="91fff-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="91fff-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="91fff-121">6 – Vidéo</span><span class="sxs-lookup"><span data-stu-id="91fff-121">6 -- Video</span></span> <br/>  <span data-ttu-id="91fff-122">7-invitation à une application</span><span class="sxs-lookup"><span data-stu-id="91fff-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="91fff-123">Si vous tentez de déterminer le type de modalité pour les valeurs dans LcsCDR.SessionDetailsView.MediaTypes, vous devrez utiliser l’extrait de Joindre suivant : </span><span class="sxs-lookup"><span data-stu-id="91fff-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
