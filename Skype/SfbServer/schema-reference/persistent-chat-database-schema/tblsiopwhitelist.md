---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblsiopwhitelist représente la liste des compléments inscrits qui peuvent être associés à des nœuds.
ms.openlocfilehash: e5201fff31982da039d864adc4d29d900dbdcf99
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899714"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="6b22f-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="6b22f-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="6b22f-104">tblsiopwhitelist représente la liste des compléments inscrits qui peuvent être associés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="6b22f-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="6b22f-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="6b22f-105">**Columns**</span></span>

|<span data-ttu-id="6b22f-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="6b22f-106">**Column**</span></span>|<span data-ttu-id="6b22f-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="6b22f-107">**Type**</span></span>|<span data-ttu-id="6b22f-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="6b22f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6b22f-109">siopID</span><span class="sxs-lookup"><span data-stu-id="6b22f-109">siopID</span></span>  <br/> |<span data-ttu-id="6b22f-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="6b22f-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="6b22f-111">GUID de la macro complémentaire.</span><span class="sxs-lookup"><span data-stu-id="6b22f-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="6b22f-112">siopName</span><span class="sxs-lookup"><span data-stu-id="6b22f-112">siopName</span></span>  <br/> |<span data-ttu-id="6b22f-113">nvarchar (50), non null</span><span class="sxs-lookup"><span data-stu-id="6b22f-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="6b22f-114">Nom complet de la macro complémentaire.</span><span class="sxs-lookup"><span data-stu-id="6b22f-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="6b22f-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="6b22f-115">siopUrl</span></span>  <br/> |<span data-ttu-id="6b22f-116">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="6b22f-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="6b22f-117">URL de l’application add-in.</span><span class="sxs-lookup"><span data-stu-id="6b22f-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="6b22f-118">**Clé**</span><span class="sxs-lookup"><span data-stu-id="6b22f-118">**Key**</span></span>

|<span data-ttu-id="6b22f-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="6b22f-119">**Column**</span></span>|<span data-ttu-id="6b22f-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="6b22f-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6b22f-121">siopID</span><span class="sxs-lookup"><span data-stu-id="6b22f-121">siopID</span></span>  <br/> |<span data-ttu-id="6b22f-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="6b22f-122">Primary key.</span></span>  <br/> |
   

