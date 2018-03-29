---
title: tblSiopWhiteList
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList est la liste des compléments enregistrés qui peuvent être associées à des nœuds.
ms.openlocfilehash: 0653ec7f4a663479f7b7d4787eee4dc0a1045aac
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="d1438-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="d1438-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="d1438-104">tblSiopWhiteList est la liste des compléments enregistrés qui peuvent être associées à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="d1438-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="d1438-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="d1438-105">**Columns**</span></span>

|<span data-ttu-id="d1438-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d1438-106">**Column**</span></span>|<span data-ttu-id="d1438-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="d1438-107">**Type**</span></span>|<span data-ttu-id="d1438-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="d1438-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d1438-109">siopID</span><span class="sxs-lookup"><span data-stu-id="d1438-109">siopID</span></span>  <br/> |<span data-ttu-id="d1438-110">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="d1438-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="d1438-111">GUID de la macro complémentaire.</span><span class="sxs-lookup"><span data-stu-id="d1438-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="d1438-112">siopName</span><span class="sxs-lookup"><span data-stu-id="d1438-112">siopName</span></span>  <br/> |<span data-ttu-id="d1438-113">nvarchar (50), non null</span><span class="sxs-lookup"><span data-stu-id="d1438-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="d1438-114">Nom complet de la macro complémentaire.</span><span class="sxs-lookup"><span data-stu-id="d1438-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="d1438-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="d1438-115">siopUrl</span></span>  <br/> |<span data-ttu-id="d1438-116">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="d1438-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="d1438-117">URL de la macro complémentaire.</span><span class="sxs-lookup"><span data-stu-id="d1438-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="d1438-118">**Clé**</span><span class="sxs-lookup"><span data-stu-id="d1438-118">**Key**</span></span>

|<span data-ttu-id="d1438-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d1438-119">**Column**</span></span>|<span data-ttu-id="d1438-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="d1438-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d1438-121">siopID</span><span class="sxs-lookup"><span data-stu-id="d1438-121">siopID</span></span>  <br/> |<span data-ttu-id="d1438-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="d1438-122">Primary key.</span></span>  <br/> |
   

