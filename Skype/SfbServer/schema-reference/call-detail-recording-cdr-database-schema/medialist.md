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
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La table MediaList est une table statique qui stocke la liste de divers types de médias.
ms.openlocfilehash: 243fd3fb705826584f4e786441cdc1faa9075777
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992924"
---
# <a name="medialist-table"></a><span data-ttu-id="fc6ce-103">Table MediaList</span><span class="sxs-lookup"><span data-stu-id="fc6ce-103">MediaList table</span></span>
 
<span data-ttu-id="fc6ce-104">La table MediaList est une table statique qui stocke la liste de divers types de médias.</span><span class="sxs-lookup"><span data-stu-id="fc6ce-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="fc6ce-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="fc6ce-105">**Column**</span></span>|<span data-ttu-id="fc6ce-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="fc6ce-106">**Data Type**</span></span>|<span data-ttu-id="fc6ce-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="fc6ce-107">**Key/Index**</span></span>|<span data-ttu-id="fc6ce-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="fc6ce-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fc6ce-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="fc6ce-109">**MediaId**</span></span> <br/> |<span data-ttu-id="fc6ce-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="fc6ce-110">tinyint</span></span>  <br/> |<span data-ttu-id="fc6ce-111">Principal</span><span class="sxs-lookup"><span data-stu-id="fc6ce-111">Primary</span></span>  <br/> |<span data-ttu-id="fc6ce-112">Valeur : 1-7</span><span class="sxs-lookup"><span data-stu-id="fc6ce-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="fc6ce-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="fc6ce-113">**Media**</span></span> <br/> |<span data-ttu-id="fc6ce-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fc6ce-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="fc6ce-115">Mappage statique de MediaID et des valeurs média :</span><span class="sxs-lookup"><span data-stu-id="fc6ce-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="fc6ce-116">1 – Messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="fc6ce-116">1 -- IM</span></span> <br/>  <span data-ttu-id="fc6ce-117">2-transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="fc6ce-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="fc6ce-118">3-assistance à distance</span><span class="sxs-lookup"><span data-stu-id="fc6ce-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="fc6ce-119">Partage d’application 4</span><span class="sxs-lookup"><span data-stu-id="fc6ce-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="fc6ce-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="fc6ce-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="fc6ce-121">6 – Vidéo</span><span class="sxs-lookup"><span data-stu-id="fc6ce-121">6 -- Video</span></span> <br/>  <span data-ttu-id="fc6ce-122">7-invitation à une application</span><span class="sxs-lookup"><span data-stu-id="fc6ce-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="fc6ce-123">Si vous tentez de déterminer le type de modalité pour les valeurs dans LcsCDR.SessionDetailsView.MediaTypes, vous devrez utiliser l’extrait de Joindre suivant : </span><span class="sxs-lookup"><span data-stu-id="fc6ce-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```json
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
