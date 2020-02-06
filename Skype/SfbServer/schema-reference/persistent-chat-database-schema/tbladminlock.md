---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contient le verrouillage de l’administrateur requis pour exécuter certaines commandes administrateur.
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814692"
---
# <a name="tbladminlock"></a><span data-ttu-id="a9ce6-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="a9ce6-103">tblAdminLock</span></span>
 
<span data-ttu-id="a9ce6-104">tblAdminLock contient le verrouillage de l’administrateur requis pour exécuter certaines commandes administrateur.</span><span class="sxs-lookup"><span data-stu-id="a9ce6-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="a9ce6-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="a9ce6-105">**Columns**</span></span>

|<span data-ttu-id="a9ce6-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a9ce6-106">**Column**</span></span>|<span data-ttu-id="a9ce6-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="a9ce6-107">**Type**</span></span>|<span data-ttu-id="a9ce6-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="a9ce6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a9ce6-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="a9ce6-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="a9ce6-110">DATEHEURE, pas null</span><span class="sxs-lookup"><span data-stu-id="a9ce6-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="a9ce6-111">Verrouillage de la date et de l’heure d’expiration.</span><span class="sxs-lookup"><span data-stu-id="a9ce6-111">Lock expiration date and time.</span></span> <span data-ttu-id="a9ce6-112">Le propriétaire peut prolonger cette valeur périodiquement.</span><span class="sxs-lookup"><span data-stu-id="a9ce6-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="a9ce6-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="a9ce6-113">lockServerID</span></span>  <br/> |<span data-ttu-id="a9ce6-114">ent, non null</span><span class="sxs-lookup"><span data-stu-id="a9ce6-114">int, not null</span></span>  <br/> |<span data-ttu-id="a9ce6-115">ID du serveur propriétaire du verrou.</span><span class="sxs-lookup"><span data-stu-id="a9ce6-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="a9ce6-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="a9ce6-116">lockActorID</span></span>  <br/> |<span data-ttu-id="a9ce6-117">ent, non null</span><span class="sxs-lookup"><span data-stu-id="a9ce6-117">int, not null</span></span>  <br/> |<span data-ttu-id="a9ce6-118">ID de l’entité propriétaire du verrou.</span><span class="sxs-lookup"><span data-stu-id="a9ce6-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

