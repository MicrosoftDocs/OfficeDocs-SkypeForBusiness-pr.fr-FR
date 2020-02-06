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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList est la liste des compléments enregistrés qui peuvent être associés à des nœuds.
ms.openlocfilehash: ae287a1a32b09ce309c688dac2a042913383a263
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812112"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="0d116-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="0d116-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="0d116-104">tblSiopWhiteList est la liste des compléments enregistrés qui peuvent être associés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="0d116-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="0d116-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="0d116-105">**Columns**</span></span>

|<span data-ttu-id="0d116-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0d116-106">**Column**</span></span>|<span data-ttu-id="0d116-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="0d116-107">**Type**</span></span>|<span data-ttu-id="0d116-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="0d116-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0d116-109">siopID</span><span class="sxs-lookup"><span data-stu-id="0d116-109">siopID</span></span>  <br/> |<span data-ttu-id="0d116-110">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="0d116-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="0d116-111">GUID du complément.</span><span class="sxs-lookup"><span data-stu-id="0d116-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="0d116-112">siopName</span><span class="sxs-lookup"><span data-stu-id="0d116-112">siopName</span></span>  <br/> |<span data-ttu-id="0d116-113">nvarchar (50), pas null</span><span class="sxs-lookup"><span data-stu-id="0d116-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="0d116-114">Nom d’affichage du complément.</span><span class="sxs-lookup"><span data-stu-id="0d116-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="0d116-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="0d116-115">siopUrl</span></span>  <br/> |<span data-ttu-id="0d116-116">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="0d116-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="0d116-117">URL du complément.</span><span class="sxs-lookup"><span data-stu-id="0d116-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="0d116-118">**Clé**</span><span class="sxs-lookup"><span data-stu-id="0d116-118">**Key**</span></span>

|<span data-ttu-id="0d116-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0d116-119">**Column**</span></span>|<span data-ttu-id="0d116-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="0d116-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0d116-121">siopID</span><span class="sxs-lookup"><span data-stu-id="0d116-121">siopID</span></span>  <br/> |<span data-ttu-id="0d116-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="0d116-122">Primary key.</span></span>  <br/> |
   

