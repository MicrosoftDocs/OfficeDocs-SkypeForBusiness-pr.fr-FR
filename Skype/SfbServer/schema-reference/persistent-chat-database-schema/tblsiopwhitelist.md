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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212382"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="b4dbe-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="b4dbe-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="b4dbe-104">tblsiopwhitelist représente la liste des compléments inscrits qui peuvent être associés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="b4dbe-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="b4dbe-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="b4dbe-105">**Columns**</span></span>

|<span data-ttu-id="b4dbe-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b4dbe-106">**Column**</span></span>|<span data-ttu-id="b4dbe-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="b4dbe-107">**Type**</span></span>|<span data-ttu-id="b4dbe-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="b4dbe-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b4dbe-109">siopID</span><span class="sxs-lookup"><span data-stu-id="b4dbe-109">siopID</span></span>  <br/> |<span data-ttu-id="b4dbe-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="b4dbe-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="b4dbe-111">GUID de la macro complémentaire.</span><span class="sxs-lookup"><span data-stu-id="b4dbe-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="b4dbe-112">siopName</span><span class="sxs-lookup"><span data-stu-id="b4dbe-112">siopName</span></span>  <br/> |<span data-ttu-id="b4dbe-113">nvarchar (50), non null</span><span class="sxs-lookup"><span data-stu-id="b4dbe-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="b4dbe-114">Nom complet de la macro complémentaire.</span><span class="sxs-lookup"><span data-stu-id="b4dbe-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="b4dbe-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="b4dbe-115">siopUrl</span></span>  <br/> |<span data-ttu-id="b4dbe-116">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="b4dbe-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="b4dbe-117">URL de l’application add-in.</span><span class="sxs-lookup"><span data-stu-id="b4dbe-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="b4dbe-118">**Clé**</span><span class="sxs-lookup"><span data-stu-id="b4dbe-118">**Key**</span></span>

|<span data-ttu-id="b4dbe-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b4dbe-119">**Column**</span></span>|<span data-ttu-id="b4dbe-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="b4dbe-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4dbe-121">siopID</span><span class="sxs-lookup"><span data-stu-id="b4dbe-121">siopID</span></span>  <br/> |<span data-ttu-id="b4dbe-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="b4dbe-122">Primary key.</span></span>  <br/> |
   

