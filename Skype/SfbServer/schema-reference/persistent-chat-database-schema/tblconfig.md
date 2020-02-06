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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contient certaines configurations du serveur de chat permanent non prises en charge, en une seule ligne.
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814622"
---
# <a name="tblconfig"></a><span data-ttu-id="db21d-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="db21d-103">tblConfig</span></span>
 
<span data-ttu-id="db21d-104">tblConfig contient certaines configurations du serveur de chat permanent non prises en charge, en une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="db21d-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="db21d-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="db21d-105">**Columns**</span></span>

|<span data-ttu-id="db21d-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="db21d-106">**Column**</span></span>|<span data-ttu-id="db21d-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="db21d-107">**Type**</span></span>|<span data-ttu-id="db21d-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="db21d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="db21d-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="db21d-109">configLabel</span></span>  <br/> |<span data-ttu-id="db21d-110">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="db21d-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="db21d-111">Contient « pool ».</span><span class="sxs-lookup"><span data-stu-id="db21d-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="db21d-112">configContent</span><span class="sxs-lookup"><span data-stu-id="db21d-112">configContent</span></span>  <br/> |<span data-ttu-id="db21d-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="db21d-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="db21d-114">Contenu de configuration.</span><span class="sxs-lookup"><span data-stu-id="db21d-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="db21d-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="db21d-115">configPoolID</span></span>  <br/> |<span data-ttu-id="db21d-116">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="db21d-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="db21d-117">ID unique de l’instance de base de données.</span><span class="sxs-lookup"><span data-stu-id="db21d-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="db21d-118">**Clé**</span><span class="sxs-lookup"><span data-stu-id="db21d-118">**Key**</span></span>

|<span data-ttu-id="db21d-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="db21d-119">**Column**</span></span>|<span data-ttu-id="db21d-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="db21d-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="db21d-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="db21d-121">configLabel</span></span>  <br/> |<span data-ttu-id="db21d-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="db21d-122">Primary key.</span></span>  <br/> |
   

