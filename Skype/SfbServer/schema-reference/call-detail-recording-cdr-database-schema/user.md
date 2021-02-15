---
title: Affichage utilisateur
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: La vue User stocke des informations sur les utilisateurs qui ont participé à des appels ou sessions qui possèdent des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831694"
---
# <a name="user-view"></a><span data-ttu-id="4fa69-104">Affichage utilisateur</span><span class="sxs-lookup"><span data-stu-id="4fa69-104">User view</span></span>
 
<span data-ttu-id="4fa69-105">La vue User stocke des informations sur les utilisateurs qui ont participé à des appels ou sessions qui possèdent des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="4fa69-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="4fa69-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4fa69-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4fa69-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="4fa69-107">**Column**</span></span>|<span data-ttu-id="4fa69-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="4fa69-108">**Data Type**</span></span>|<span data-ttu-id="4fa69-109">**Détails**</span><span class="sxs-lookup"><span data-stu-id="4fa69-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4fa69-110">UserId</span><span class="sxs-lookup"><span data-stu-id="4fa69-110">UserId</span></span>  <br/> |<span data-ttu-id="4fa69-111">int</span><span class="sxs-lookup"><span data-stu-id="4fa69-111">int</span></span>  <br/> |<span data-ttu-id="4fa69-112">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4fa69-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="4fa69-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="4fa69-113">UserUri</span></span>  <br/> |<span data-ttu-id="4fa69-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="4fa69-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="4fa69-115">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4fa69-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="4fa69-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="4fa69-116">TenantKey</span></span>  <br/> |<span data-ttu-id="4fa69-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="4fa69-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="4fa69-118">Client de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4fa69-118">Tenant of user.</span></span> <span data-ttu-id="4fa69-119">Pour plus [d’informations, voir la table Tenants.](tenants.md)</span><span class="sxs-lookup"><span data-stu-id="4fa69-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4fa69-120">UriType</span><span class="sxs-lookup"><span data-stu-id="4fa69-120">UriType</span></span>  <br/> |<span data-ttu-id="4fa69-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4fa69-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4fa69-122">Type de l’URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4fa69-122">Type of user URI.</span></span> <span data-ttu-id="4fa69-123">Pour plus [d’informations, voir la table UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="4fa69-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

