---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contient les serveurs de chat actifs dans le pool de serveurs de chat permanent.
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295187"
---
# <a name="tblserveridentity"></a><span data-ttu-id="f222f-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="f222f-103">tblServerIdentity</span></span>
 
<span data-ttu-id="f222f-104">tblServerIdentity contient les serveurs de chat actifs dans le pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="f222f-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="f222f-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="f222f-105">**Columns**</span></span>

|<span data-ttu-id="f222f-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f222f-106">**Column**</span></span>|<span data-ttu-id="f222f-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="f222f-107">**Type**</span></span>|<span data-ttu-id="f222f-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="f222f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f222f-109">serverID</span><span class="sxs-lookup"><span data-stu-id="f222f-109">serverID</span></span>  <br/> |<span data-ttu-id="f222f-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="f222f-110">int, not null</span></span>  <br/> |<span data-ttu-id="f222f-111">ID du serveur.</span><span class="sxs-lookup"><span data-stu-id="f222f-111">Server ID.</span></span> <span data-ttu-id="f222f-112">Correspond à l’ID de l’instance du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="f222f-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="f222f-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="f222f-113">serverAddress</span></span>  <br/> |<span data-ttu-id="f222f-114">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="f222f-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="f222f-115">Adresse du serveur à l’aide de l’adresse Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="f222f-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="f222f-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="f222f-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="f222f-117">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f222f-117">datetime</span></span>  <br/> |<span data-ttu-id="f222f-118">Dernière mise à jour de cette ligne par le serveur de canal pour indiquer qu’il est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="f222f-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="f222f-119">**Clé**</span><span class="sxs-lookup"><span data-stu-id="f222f-119">**Key**</span></span>

|<span data-ttu-id="f222f-120">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f222f-120">**Column**</span></span>|<span data-ttu-id="f222f-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="f222f-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f222f-122">serverID</span><span class="sxs-lookup"><span data-stu-id="f222f-122">serverID</span></span>  <br/> |<span data-ttu-id="f222f-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="f222f-123">Primary key.</span></span>  <br/> |
   

