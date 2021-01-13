---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contient une configuration non pris en compte du serveur de conversation permanente, sur une ligne.
ms.openlocfilehash: 614e4e6514d695777c39a9d76482f775bd1a0981
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809734"
---
# <a name="tblconfig"></a><span data-ttu-id="42d8b-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="42d8b-103">tblConfig</span></span>
 
<span data-ttu-id="42d8b-104">tblConfig contient une configuration non pris en compte du serveur de conversation permanente, sur une ligne.</span><span class="sxs-lookup"><span data-stu-id="42d8b-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="42d8b-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="42d8b-105">**Columns**</span></span>

|<span data-ttu-id="42d8b-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="42d8b-106">**Column**</span></span>|<span data-ttu-id="42d8b-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="42d8b-107">**Type**</span></span>|<span data-ttu-id="42d8b-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="42d8b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="42d8b-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="42d8b-109">configLabel</span></span>  <br/> |<span data-ttu-id="42d8b-110">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="42d8b-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="42d8b-111">Contient « pool ».</span><span class="sxs-lookup"><span data-stu-id="42d8b-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="42d8b-112">configContent</span><span class="sxs-lookup"><span data-stu-id="42d8b-112">configContent</span></span>  <br/> |<span data-ttu-id="42d8b-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="42d8b-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="42d8b-114">Contenu de configuration.</span><span class="sxs-lookup"><span data-stu-id="42d8b-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="42d8b-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="42d8b-115">configPoolID</span></span>  <br/> |<span data-ttu-id="42d8b-116">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="42d8b-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="42d8b-117">ID unique de l’instance de base de données.</span><span class="sxs-lookup"><span data-stu-id="42d8b-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="42d8b-118">**Clé**</span><span class="sxs-lookup"><span data-stu-id="42d8b-118">**Key**</span></span>

|<span data-ttu-id="42d8b-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="42d8b-119">**Column**</span></span>|<span data-ttu-id="42d8b-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="42d8b-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="42d8b-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="42d8b-121">configLabel</span></span>  <br/> |<span data-ttu-id="42d8b-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="42d8b-122">Primary key.</span></span>  <br/> |
   

