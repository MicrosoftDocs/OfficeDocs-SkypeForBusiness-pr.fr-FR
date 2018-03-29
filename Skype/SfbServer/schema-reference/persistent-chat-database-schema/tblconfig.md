---
title: tblConfig
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contient une configuration non prise en charge permanente Chat Server, dans une ligne.
ms.openlocfilehash: 099060f0957ae21c14b285eac1b753ad0b8c1719
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblconfig"></a><span data-ttu-id="f281b-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="f281b-103">tblConfig</span></span>
 
<span data-ttu-id="f281b-104">tblConfig contient une configuration non prise en charge permanente Chat Server, dans une ligne.</span><span class="sxs-lookup"><span data-stu-id="f281b-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="f281b-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="f281b-105">**Columns**</span></span>

|<span data-ttu-id="f281b-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f281b-106">**Column**</span></span>|<span data-ttu-id="f281b-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="f281b-107">**Type**</span></span>|<span data-ttu-id="f281b-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="f281b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f281b-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="f281b-109">configLabel</span></span>  <br/> |<span data-ttu-id="f281b-110">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="f281b-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="f281b-111">Contient « pool ».</span><span class="sxs-lookup"><span data-stu-id="f281b-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="f281b-112">configContent</span><span class="sxs-lookup"><span data-stu-id="f281b-112">configContent</span></span>  <br/> |<span data-ttu-id="f281b-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="f281b-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="f281b-114">Contenu de la configuration.</span><span class="sxs-lookup"><span data-stu-id="f281b-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="f281b-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="f281b-115">configPoolID</span></span>  <br/> |<span data-ttu-id="f281b-116">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="f281b-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="f281b-117">ID unique de l’instance de base de données.</span><span class="sxs-lookup"><span data-stu-id="f281b-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="f281b-118">**Clé**</span><span class="sxs-lookup"><span data-stu-id="f281b-118">**Key**</span></span>

|<span data-ttu-id="f281b-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f281b-119">**Column**</span></span>|<span data-ttu-id="f281b-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="f281b-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f281b-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="f281b-121">configLabel</span></span>  <br/> |<span data-ttu-id="f281b-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="f281b-122">Primary key.</span></span>  <br/> |
   

