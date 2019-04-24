---
title: tblConfig
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contient une configuration non prise en charge Persistent Chat Server, dans une seule ligne.
ms.openlocfilehash: 9d28c0506b905975e2a72eeb83605fe4e32e7cfd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213066"
---
# <a name="tblconfig"></a><span data-ttu-id="0a1de-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="0a1de-103">tblConfig</span></span>
 
<span data-ttu-id="0a1de-104">tblConfig contient une configuration non prise en charge Persistent Chat Server, dans une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="0a1de-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="0a1de-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="0a1de-105">**Columns**</span></span>

|<span data-ttu-id="0a1de-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0a1de-106">**Column**</span></span>|<span data-ttu-id="0a1de-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="0a1de-107">**Type**</span></span>|<span data-ttu-id="0a1de-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="0a1de-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0a1de-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="0a1de-109">configLabel</span></span>  <br/> |<span data-ttu-id="0a1de-110">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="0a1de-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="0a1de-111">Contient « pool ».</span><span class="sxs-lookup"><span data-stu-id="0a1de-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="0a1de-112">configContent</span><span class="sxs-lookup"><span data-stu-id="0a1de-112">configContent</span></span>  <br/> |<span data-ttu-id="0a1de-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="0a1de-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="0a1de-114">Contenu de la configuration.</span><span class="sxs-lookup"><span data-stu-id="0a1de-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="0a1de-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="0a1de-115">configPoolID</span></span>  <br/> |<span data-ttu-id="0a1de-116">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="0a1de-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="0a1de-117">ID unique de l’instance de base de données.</span><span class="sxs-lookup"><span data-stu-id="0a1de-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="0a1de-118">**Clé**</span><span class="sxs-lookup"><span data-stu-id="0a1de-118">**Key**</span></span>

|<span data-ttu-id="0a1de-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0a1de-119">**Column**</span></span>|<span data-ttu-id="0a1de-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="0a1de-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0a1de-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="0a1de-121">configLabel</span></span>  <br/> |<span data-ttu-id="0a1de-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="0a1de-122">Primary key.</span></span>  <br/> |
   

