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
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contient le verrouillage de l’administrateur requis pour exécuter certaines commandes administrateur.
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295523"
---
# <a name="tbladminlock"></a><span data-ttu-id="3183e-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="3183e-103">tblAdminLock</span></span>
 
<span data-ttu-id="3183e-104">tblAdminLock contient le verrouillage de l’administrateur requis pour exécuter certaines commandes administrateur.</span><span class="sxs-lookup"><span data-stu-id="3183e-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="3183e-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="3183e-105">**Columns**</span></span>

|<span data-ttu-id="3183e-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3183e-106">**Column**</span></span>|<span data-ttu-id="3183e-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="3183e-107">**Type**</span></span>|<span data-ttu-id="3183e-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="3183e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3183e-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="3183e-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="3183e-110">DATEHEURE, pas null</span><span class="sxs-lookup"><span data-stu-id="3183e-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="3183e-111">Verrouillage de la date et de l’heure d’expiration.</span><span class="sxs-lookup"><span data-stu-id="3183e-111">Lock expiration date and time.</span></span> <span data-ttu-id="3183e-112">Le propriétaire peut prolonger cette valeur périodiquement.</span><span class="sxs-lookup"><span data-stu-id="3183e-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="3183e-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="3183e-113">lockServerID</span></span>  <br/> |<span data-ttu-id="3183e-114">ent, non null</span><span class="sxs-lookup"><span data-stu-id="3183e-114">int, not null</span></span>  <br/> |<span data-ttu-id="3183e-115">ID du serveur propriétaire du verrou.</span><span class="sxs-lookup"><span data-stu-id="3183e-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="3183e-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="3183e-116">lockActorID</span></span>  <br/> |<span data-ttu-id="3183e-117">ent, non null</span><span class="sxs-lookup"><span data-stu-id="3183e-117">int, not null</span></span>  <br/> |<span data-ttu-id="3183e-118">ID de l’entité propriétaire du verrou.</span><span class="sxs-lookup"><span data-stu-id="3183e-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

