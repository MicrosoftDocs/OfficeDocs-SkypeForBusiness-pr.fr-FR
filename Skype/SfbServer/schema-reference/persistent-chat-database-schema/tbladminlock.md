---
title: tblAdminLock
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.
ms.openlocfilehash: bf7537b7d1081bd415ff2e8fe3615864c71f593a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898951"
---
# <a name="tbladminlock"></a><span data-ttu-id="cd1ab-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="cd1ab-103">tblAdminLock</span></span>
 
<span data-ttu-id="cd1ab-104">tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.</span><span class="sxs-lookup"><span data-stu-id="cd1ab-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="cd1ab-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="cd1ab-105">**Columns**</span></span>

|<span data-ttu-id="cd1ab-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cd1ab-106">**Column**</span></span>|<span data-ttu-id="cd1ab-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="cd1ab-107">**Type**</span></span>|<span data-ttu-id="cd1ab-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="cd1ab-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cd1ab-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="cd1ab-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="cd1ab-110">DateTime, non null</span><span class="sxs-lookup"><span data-stu-id="cd1ab-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="cd1ab-111">Verrouiller la date d’expiration et l’heure.</span><span class="sxs-lookup"><span data-stu-id="cd1ab-111">Lock expiration date and time.</span></span> <span data-ttu-id="cd1ab-112">Le propriétaire peut étendre régulièrement cette valeur.</span><span class="sxs-lookup"><span data-stu-id="cd1ab-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="cd1ab-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="cd1ab-113">lockServerID</span></span>  <br/> |<span data-ttu-id="cd1ab-114">int, non null</span><span class="sxs-lookup"><span data-stu-id="cd1ab-114">int, not null</span></span>  <br/> |<span data-ttu-id="cd1ab-115">ID du serveur qui détient le verrou.</span><span class="sxs-lookup"><span data-stu-id="cd1ab-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="cd1ab-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="cd1ab-116">lockActorID</span></span>  <br/> |<span data-ttu-id="cd1ab-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="cd1ab-117">int, not null</span></span>  <br/> |<span data-ttu-id="cd1ab-118">ID du principal qui détient le verrou.</span><span class="sxs-lookup"><span data-stu-id="cd1ab-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

