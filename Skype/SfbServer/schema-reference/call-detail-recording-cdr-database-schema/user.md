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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213178"
---
# <a name="user-view"></a><span data-ttu-id="b829b-104">Affichage de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="b829b-104">User view</span></span>
 
<span data-ttu-id="b829b-105">L’affichage utilisateur stocke des informations sur les utilisateurs qui ont participé à des appels ou des sessions disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="b829b-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="b829b-106">Cet affichage a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b829b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b829b-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b829b-107">**Column**</span></span>|<span data-ttu-id="b829b-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="b829b-108">**Data Type**</span></span>|<span data-ttu-id="b829b-109">**Détails**</span><span class="sxs-lookup"><span data-stu-id="b829b-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b829b-110">Nom d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="b829b-110">UserId</span></span>  <br/> |<span data-ttu-id="b829b-111">int</span><span class="sxs-lookup"><span data-stu-id="b829b-111">int</span></span>  <br/> |<span data-ttu-id="b829b-112">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b829b-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="b829b-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="b829b-113">UserUri</span></span>  <br/> |<span data-ttu-id="b829b-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="b829b-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="b829b-115">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b829b-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="b829b-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="b829b-116">TenantKey</span></span>  <br/> |<span data-ttu-id="b829b-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="b829b-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="b829b-118">Client de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b829b-118">Tenant of user.</span></span> <span data-ttu-id="b829b-119">Consultez le [tableau des clients](tenants.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="b829b-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b829b-120">UriType</span><span class="sxs-lookup"><span data-stu-id="b829b-120">UriType</span></span>  <br/> |<span data-ttu-id="b829b-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b829b-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b829b-122">Type d’URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b829b-122">Type of user URI.</span></span> <span data-ttu-id="b829b-123">Consultez la [table UriTypes](uritypes.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="b829b-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

