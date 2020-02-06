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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contient les serveurs de chat actifs dans le pool de serveurs de chat permanent.
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812272"
---
# <a name="tblserveridentity"></a><span data-ttu-id="c6b0b-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="c6b0b-103">tblServerIdentity</span></span>
 
<span data-ttu-id="c6b0b-104">tblServerIdentity contient les serveurs de chat actifs dans le pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="c6b0b-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="c6b0b-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="c6b0b-105">**Columns**</span></span>

|<span data-ttu-id="c6b0b-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c6b0b-106">**Column**</span></span>|<span data-ttu-id="c6b0b-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="c6b0b-107">**Type**</span></span>|<span data-ttu-id="c6b0b-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="c6b0b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c6b0b-109">serverID</span><span class="sxs-lookup"><span data-stu-id="c6b0b-109">serverID</span></span>  <br/> |<span data-ttu-id="c6b0b-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="c6b0b-110">int, not null</span></span>  <br/> |<span data-ttu-id="c6b0b-111">ID du serveur.</span><span class="sxs-lookup"><span data-stu-id="c6b0b-111">Server ID.</span></span> <span data-ttu-id="c6b0b-112">Correspond à l’ID de l’instance du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="c6b0b-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="c6b0b-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="c6b0b-113">serverAddress</span></span>  <br/> |<span data-ttu-id="c6b0b-114">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="c6b0b-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="c6b0b-115">Adresse du serveur à l’aide de l’adresse Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="c6b0b-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="c6b0b-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="c6b0b-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="c6b0b-117">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c6b0b-117">datetime</span></span>  <br/> |<span data-ttu-id="c6b0b-118">Dernière mise à jour de cette ligne par le serveur de canal pour indiquer qu’il est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="c6b0b-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="c6b0b-119">**Clé**</span><span class="sxs-lookup"><span data-stu-id="c6b0b-119">**Key**</span></span>

|<span data-ttu-id="c6b0b-120">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c6b0b-120">**Column**</span></span>|<span data-ttu-id="c6b0b-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="c6b0b-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c6b0b-122">serverID</span><span class="sxs-lookup"><span data-stu-id="c6b0b-122">serverID</span></span>  <br/> |<span data-ttu-id="c6b0b-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="c6b0b-123">Primary key.</span></span>  <br/> |
   

