---
title: Affichage de l’utilisateur
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: L’affichage utilisateur stocke des informations sur les utilisateurs qui ont participé à des appels ou des sessions disposant d’enregistrements dans la base de données. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 9e631c101660e8f14bca25f019f5d991a0d9aadd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877642"
---
# <a name="user-view"></a><span data-ttu-id="6263a-104">Affichage de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="6263a-104">User view</span></span>
 
<span data-ttu-id="6263a-105">L’affichage utilisateur stocke des informations sur les utilisateurs qui ont participé à des appels ou des sessions disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6263a-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="6263a-106">Cet affichage a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6263a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="6263a-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="6263a-107">**Column**</span></span>|<span data-ttu-id="6263a-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="6263a-108">**Data Type**</span></span>|<span data-ttu-id="6263a-109">**Détails**</span><span class="sxs-lookup"><span data-stu-id="6263a-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6263a-110">Nom d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="6263a-110">UserId</span></span>  <br/> |<span data-ttu-id="6263a-111">int</span><span class="sxs-lookup"><span data-stu-id="6263a-111">int</span></span>  <br/> |<span data-ttu-id="6263a-112">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6263a-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="6263a-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="6263a-113">UserUri</span></span>  <br/> |<span data-ttu-id="6263a-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6263a-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="6263a-115">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6263a-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="6263a-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="6263a-116">TenantKey</span></span>  <br/> |<span data-ttu-id="6263a-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="6263a-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="6263a-118">Client de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6263a-118">Tenant of user.</span></span> <span data-ttu-id="6263a-119">Consultez le [tableau des clients](tenants.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="6263a-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6263a-120">UriType</span><span class="sxs-lookup"><span data-stu-id="6263a-120">UriType</span></span>  <br/> |<span data-ttu-id="6263a-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6263a-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6263a-122">Type d’URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6263a-122">Type of user URI.</span></span> <span data-ttu-id="6263a-123">Consultez la [table UriTypes](uritypes.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="6263a-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

