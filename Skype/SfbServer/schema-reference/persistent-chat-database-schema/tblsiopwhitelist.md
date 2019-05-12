---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblsiopwhitelist représente la liste des compléments inscrits qui peuvent être associés à des nœuds.
ms.openlocfilehash: f3389f3d4a956e00180303c09bd3eb264d786b9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924772"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="37a0a-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="37a0a-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="37a0a-104">tblsiopwhitelist représente la liste des compléments inscrits qui peuvent être associés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="37a0a-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="37a0a-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="37a0a-105">**Columns**</span></span>

|<span data-ttu-id="37a0a-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="37a0a-106">**Column**</span></span>|<span data-ttu-id="37a0a-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="37a0a-107">**Type**</span></span>|<span data-ttu-id="37a0a-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="37a0a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="37a0a-109">siopID</span><span class="sxs-lookup"><span data-stu-id="37a0a-109">siopID</span></span>  <br/> |<span data-ttu-id="37a0a-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="37a0a-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="37a0a-111">GUID de la macro complémentaire.</span><span class="sxs-lookup"><span data-stu-id="37a0a-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="37a0a-112">siopName</span><span class="sxs-lookup"><span data-stu-id="37a0a-112">siopName</span></span>  <br/> |<span data-ttu-id="37a0a-113">nvarchar (50), non null</span><span class="sxs-lookup"><span data-stu-id="37a0a-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="37a0a-114">Nom complet de la macro complémentaire.</span><span class="sxs-lookup"><span data-stu-id="37a0a-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="37a0a-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="37a0a-115">siopUrl</span></span>  <br/> |<span data-ttu-id="37a0a-116">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="37a0a-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="37a0a-117">URL de l’application add-in.</span><span class="sxs-lookup"><span data-stu-id="37a0a-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="37a0a-118">**Clé**</span><span class="sxs-lookup"><span data-stu-id="37a0a-118">**Key**</span></span>

|<span data-ttu-id="37a0a-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="37a0a-119">**Column**</span></span>|<span data-ttu-id="37a0a-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="37a0a-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="37a0a-121">siopID</span><span class="sxs-lookup"><span data-stu-id="37a0a-121">siopID</span></span>  <br/> |<span data-ttu-id="37a0a-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="37a0a-122">Primary key.</span></span>  <br/> |
   

