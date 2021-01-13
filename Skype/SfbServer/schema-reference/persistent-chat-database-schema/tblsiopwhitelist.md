---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList représente la liste des compléments inscrits qui peuvent être associés à des nœuds.
ms.openlocfilehash: cf7a727bd34e5c6f29f5bf0b203411983c90ae53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831484"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="c0140-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="c0140-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="c0140-104">tblSiopWhiteList représente la liste des compléments inscrits qui peuvent être associés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="c0140-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="c0140-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="c0140-105">**Columns**</span></span>

|<span data-ttu-id="c0140-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c0140-106">**Column**</span></span>|<span data-ttu-id="c0140-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="c0140-107">**Type**</span></span>|<span data-ttu-id="c0140-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="c0140-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c0140-109">siopID</span><span class="sxs-lookup"><span data-stu-id="c0140-109">siopID</span></span>  <br/> |<span data-ttu-id="c0140-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="c0140-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="c0140-111">GUID du complément.</span><span class="sxs-lookup"><span data-stu-id="c0140-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="c0140-112">siopName</span><span class="sxs-lookup"><span data-stu-id="c0140-112">siopName</span></span>  <br/> |<span data-ttu-id="c0140-113">nvarchar (50), non null</span><span class="sxs-lookup"><span data-stu-id="c0140-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="c0140-114">Nom d’affichage du complément.</span><span class="sxs-lookup"><span data-stu-id="c0140-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="c0140-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="c0140-115">siopUrl</span></span>  <br/> |<span data-ttu-id="c0140-116">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="c0140-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="c0140-117">URL du complément.</span><span class="sxs-lookup"><span data-stu-id="c0140-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="c0140-118">**Clé**</span><span class="sxs-lookup"><span data-stu-id="c0140-118">**Key**</span></span>

|<span data-ttu-id="c0140-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c0140-119">**Column**</span></span>|<span data-ttu-id="c0140-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="c0140-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c0140-121">siopID</span><span class="sxs-lookup"><span data-stu-id="c0140-121">siopID</span></span>  <br/> |<span data-ttu-id="c0140-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="c0140-122">Primary key.</span></span>  <br/> |
   

