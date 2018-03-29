---
title: Affichage de l’utilisateur
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: L’affichage utilisateur stocke des informations sur les utilisateurs qui ont été impliqués dans les appels ou les sessions qui ont des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 014b773a60cc053c0ec258c7dd853e31a590319c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="user-view"></a><span data-ttu-id="81109-104">Affichage de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="81109-104">User view</span></span>
 
<span data-ttu-id="81109-105">L’affichage utilisateur stocke des informations sur les utilisateurs qui ont été impliqués dans les appels ou les sessions qui ont des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="81109-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="81109-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81109-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="81109-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="81109-107">**Column**</span></span>|<span data-ttu-id="81109-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="81109-108">**Data Type**</span></span>|<span data-ttu-id="81109-109">**Détails**</span><span class="sxs-lookup"><span data-stu-id="81109-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="81109-110">ID utilisateur</span><span class="sxs-lookup"><span data-stu-id="81109-110">UserId</span></span>  <br/> |<span data-ttu-id="81109-111">int</span><span class="sxs-lookup"><span data-stu-id="81109-111">int</span></span>  <br/> |<span data-ttu-id="81109-112">Numéro unique identifiant l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="81109-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="81109-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="81109-113">UserUri</span></span>  <br/> |<span data-ttu-id="81109-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="81109-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="81109-115">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="81109-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="81109-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="81109-116">TenantKey</span></span>  <br/> |<span data-ttu-id="81109-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="81109-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="81109-118">Clients de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="81109-118">Tenant of user.</span></span> <span data-ttu-id="81109-119">Consultez le [tableau des locataires](tenants.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="81109-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="81109-120">UriType</span><span class="sxs-lookup"><span data-stu-id="81109-120">UriType</span></span>  <br/> |<span data-ttu-id="81109-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="81109-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="81109-122">Type d’utilisateur URI.</span><span class="sxs-lookup"><span data-stu-id="81109-122">Type of user URI.</span></span> <span data-ttu-id="81109-123">Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="81109-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

