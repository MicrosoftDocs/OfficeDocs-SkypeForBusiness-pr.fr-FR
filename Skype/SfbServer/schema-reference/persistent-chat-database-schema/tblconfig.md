---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contient certaines configurations du serveur de chat permanent non prises en charge, en une seule ligne.
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295453"
---
# <a name="tblconfig"></a><span data-ttu-id="d7f1c-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="d7f1c-103">tblConfig</span></span>
 
<span data-ttu-id="d7f1c-104">tblConfig contient certaines configurations du serveur de chat permanent non prises en charge, en une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="d7f1c-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="d7f1c-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="d7f1c-105">**Columns**</span></span>

|<span data-ttu-id="d7f1c-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d7f1c-106">**Column**</span></span>|<span data-ttu-id="d7f1c-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="d7f1c-107">**Type**</span></span>|<span data-ttu-id="d7f1c-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="d7f1c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d7f1c-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="d7f1c-109">configLabel</span></span>  <br/> |<span data-ttu-id="d7f1c-110">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="d7f1c-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="d7f1c-111">Contient «pool».</span><span class="sxs-lookup"><span data-stu-id="d7f1c-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="d7f1c-112">configContent</span><span class="sxs-lookup"><span data-stu-id="d7f1c-112">configContent</span></span>  <br/> |<span data-ttu-id="d7f1c-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="d7f1c-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="d7f1c-114">Contenu de configuration.</span><span class="sxs-lookup"><span data-stu-id="d7f1c-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="d7f1c-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="d7f1c-115">configPoolID</span></span>  <br/> |<span data-ttu-id="d7f1c-116">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="d7f1c-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="d7f1c-117">ID unique de l’instance de base de données.</span><span class="sxs-lookup"><span data-stu-id="d7f1c-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="d7f1c-118">**Clé**</span><span class="sxs-lookup"><span data-stu-id="d7f1c-118">**Key**</span></span>

|<span data-ttu-id="d7f1c-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d7f1c-119">**Column**</span></span>|<span data-ttu-id="d7f1c-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="d7f1c-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d7f1c-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="d7f1c-121">configLabel</span></span>  <br/> |<span data-ttu-id="d7f1c-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="d7f1c-122">Primary key.</span></span>  <br/> |
   

