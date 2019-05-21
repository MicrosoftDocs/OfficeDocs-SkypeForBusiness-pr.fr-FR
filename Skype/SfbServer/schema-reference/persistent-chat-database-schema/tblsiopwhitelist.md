---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList est la liste des compléments enregistrés qui peuvent être associés à des nœuds.
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295173"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="d3dea-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="d3dea-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="d3dea-104">tblSiopWhiteList est la liste des compléments enregistrés qui peuvent être associés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="d3dea-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="d3dea-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="d3dea-105">**Columns**</span></span>

|<span data-ttu-id="d3dea-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d3dea-106">**Column**</span></span>|<span data-ttu-id="d3dea-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="d3dea-107">**Type**</span></span>|<span data-ttu-id="d3dea-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="d3dea-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d3dea-109">siopID</span><span class="sxs-lookup"><span data-stu-id="d3dea-109">siopID</span></span>  <br/> |<span data-ttu-id="d3dea-110">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="d3dea-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="d3dea-111">GUID du complément.</span><span class="sxs-lookup"><span data-stu-id="d3dea-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="d3dea-112">siopName</span><span class="sxs-lookup"><span data-stu-id="d3dea-112">siopName</span></span>  <br/> |<span data-ttu-id="d3dea-113">nvarchar (50), pas null</span><span class="sxs-lookup"><span data-stu-id="d3dea-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="d3dea-114">Nom d’affichage du complément.</span><span class="sxs-lookup"><span data-stu-id="d3dea-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="d3dea-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="d3dea-115">siopUrl</span></span>  <br/> |<span data-ttu-id="d3dea-116">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="d3dea-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="d3dea-117">URL du complément.</span><span class="sxs-lookup"><span data-stu-id="d3dea-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="d3dea-118">**Clé**</span><span class="sxs-lookup"><span data-stu-id="d3dea-118">**Key**</span></span>

|<span data-ttu-id="d3dea-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d3dea-119">**Column**</span></span>|<span data-ttu-id="d3dea-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="d3dea-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d3dea-121">siopID</span><span class="sxs-lookup"><span data-stu-id="d3dea-121">siopID</span></span>  <br/> |<span data-ttu-id="d3dea-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="d3dea-122">Primary key.</span></span>  <br/> |
   

