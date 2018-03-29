---
title: tblAdminLock
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contient le verrou de l’administrateur qui est nécessaire pour exécuter certaines commandes de l’administrateur.
ms.openlocfilehash: 919ead84ed9baab859e1e85eb2f30f5ff6902531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tbladminlock"></a><span data-ttu-id="599d2-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="599d2-103">tblAdminLock</span></span>
 
<span data-ttu-id="599d2-104">tblAdminLock contient le verrou de l’administrateur qui est nécessaire pour exécuter certaines commandes de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="599d2-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="599d2-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="599d2-105">**Columns**</span></span>

|<span data-ttu-id="599d2-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="599d2-106">**Column**</span></span>|<span data-ttu-id="599d2-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="599d2-107">**Type**</span></span>|<span data-ttu-id="599d2-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="599d2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="599d2-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="599d2-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="599d2-110">DateTime, non null</span><span class="sxs-lookup"><span data-stu-id="599d2-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="599d2-111">Verrou d’expiration date et heure.</span><span class="sxs-lookup"><span data-stu-id="599d2-111">Lock expiration date and time.</span></span> <span data-ttu-id="599d2-112">Le propriétaire peut étendre cette valeur périodiquement.</span><span class="sxs-lookup"><span data-stu-id="599d2-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="599d2-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="599d2-113">lockServerID</span></span>  <br/> |<span data-ttu-id="599d2-114">int, non null</span><span class="sxs-lookup"><span data-stu-id="599d2-114">int, not null</span></span>  <br/> |<span data-ttu-id="599d2-115">ID du serveur qui détient le verrou.</span><span class="sxs-lookup"><span data-stu-id="599d2-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="599d2-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="599d2-116">lockActorID</span></span>  <br/> |<span data-ttu-id="599d2-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="599d2-117">int, not null</span></span>  <br/> |<span data-ttu-id="599d2-118">ID de l’entité qui détient le verrou.</span><span class="sxs-lookup"><span data-stu-id="599d2-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

