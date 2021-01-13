---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809884"
---
# <a name="tbladminlock"></a><span data-ttu-id="b3cb3-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="b3cb3-103">tblAdminLock</span></span>
 
<span data-ttu-id="b3cb3-104">tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.</span><span class="sxs-lookup"><span data-stu-id="b3cb3-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="b3cb3-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="b3cb3-105">**Columns**</span></span>

|<span data-ttu-id="b3cb3-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b3cb3-106">**Column**</span></span>|<span data-ttu-id="b3cb3-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="b3cb3-107">**Type**</span></span>|<span data-ttu-id="b3cb3-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="b3cb3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b3cb3-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="b3cb3-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="b3cb3-110">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="b3cb3-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="b3cb3-p101">Date et heure d’expiration du verrou. Le propriétaire peut étendre cette valeur de manière périodique.</span><span class="sxs-lookup"><span data-stu-id="b3cb3-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="b3cb3-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="b3cb3-113">lockServerID</span></span>  <br/> |<span data-ttu-id="b3cb3-114">int, non null</span><span class="sxs-lookup"><span data-stu-id="b3cb3-114">int, not null</span></span>  <br/> |<span data-ttu-id="b3cb3-115">ID du serveur qui détient le verrou.</span><span class="sxs-lookup"><span data-stu-id="b3cb3-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="b3cb3-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="b3cb3-116">lockActorID</span></span>  <br/> |<span data-ttu-id="b3cb3-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="b3cb3-117">int, not null</span></span>  <br/> |<span data-ttu-id="b3cb3-118">ID du principal qui détient le verrou.</span><span class="sxs-lookup"><span data-stu-id="b3cb3-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

