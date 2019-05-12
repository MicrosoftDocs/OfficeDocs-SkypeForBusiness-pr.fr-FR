---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.
ms.openlocfilehash: ea1cff137e58ef65eda172a9c09e5dd38e66d8a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929811"
---
# <a name="tbladminlock"></a><span data-ttu-id="5f3d8-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="5f3d8-103">tblAdminLock</span></span>
 
<span data-ttu-id="5f3d8-104">tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.</span><span class="sxs-lookup"><span data-stu-id="5f3d8-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="5f3d8-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="5f3d8-105">**Columns**</span></span>

|<span data-ttu-id="5f3d8-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5f3d8-106">**Column**</span></span>|<span data-ttu-id="5f3d8-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="5f3d8-107">**Type**</span></span>|<span data-ttu-id="5f3d8-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="5f3d8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5f3d8-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="5f3d8-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="5f3d8-110">DateTime, non null</span><span class="sxs-lookup"><span data-stu-id="5f3d8-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="5f3d8-111">Verrouiller la date d’expiration et l’heure.</span><span class="sxs-lookup"><span data-stu-id="5f3d8-111">Lock expiration date and time.</span></span> <span data-ttu-id="5f3d8-112">Le propriétaire peut étendre régulièrement cette valeur.</span><span class="sxs-lookup"><span data-stu-id="5f3d8-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="5f3d8-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="5f3d8-113">lockServerID</span></span>  <br/> |<span data-ttu-id="5f3d8-114">int, non null</span><span class="sxs-lookup"><span data-stu-id="5f3d8-114">int, not null</span></span>  <br/> |<span data-ttu-id="5f3d8-115">ID du serveur qui détient le verrou.</span><span class="sxs-lookup"><span data-stu-id="5f3d8-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="5f3d8-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="5f3d8-116">lockActorID</span></span>  <br/> |<span data-ttu-id="5f3d8-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="5f3d8-117">int, not null</span></span>  <br/> |<span data-ttu-id="5f3d8-118">ID du principal qui détient le verrou.</span><span class="sxs-lookup"><span data-stu-id="5f3d8-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

