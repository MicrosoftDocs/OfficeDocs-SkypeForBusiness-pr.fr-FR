---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contient une configuration non prise en charge Persistent Chat Server, dans une seule ligne.
ms.openlocfilehash: 79cd7e2303210bb07f35fa2c6b7ecc5c86b7e8cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930021"
---
# <a name="tblconfig"></a><span data-ttu-id="25400-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="25400-103">tblConfig</span></span>
 
<span data-ttu-id="25400-104">tblConfig contient une configuration non prise en charge Persistent Chat Server, dans une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="25400-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="25400-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="25400-105">**Columns**</span></span>

|<span data-ttu-id="25400-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="25400-106">**Column**</span></span>|<span data-ttu-id="25400-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="25400-107">**Type**</span></span>|<span data-ttu-id="25400-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="25400-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="25400-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="25400-109">configLabel</span></span>  <br/> |<span data-ttu-id="25400-110">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="25400-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="25400-111">Contient « pool ».</span><span class="sxs-lookup"><span data-stu-id="25400-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="25400-112">configContent</span><span class="sxs-lookup"><span data-stu-id="25400-112">configContent</span></span>  <br/> |<span data-ttu-id="25400-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="25400-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="25400-114">Contenu de la configuration.</span><span class="sxs-lookup"><span data-stu-id="25400-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="25400-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="25400-115">configPoolID</span></span>  <br/> |<span data-ttu-id="25400-116">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="25400-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="25400-117">ID unique de l’instance de base de données.</span><span class="sxs-lookup"><span data-stu-id="25400-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="25400-118">**Clé**</span><span class="sxs-lookup"><span data-stu-id="25400-118">**Key**</span></span>

|<span data-ttu-id="25400-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="25400-119">**Column**</span></span>|<span data-ttu-id="25400-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="25400-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="25400-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="25400-121">configLabel</span></span>  <br/> |<span data-ttu-id="25400-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="25400-122">Primary key.</span></span>  <br/> |
   

