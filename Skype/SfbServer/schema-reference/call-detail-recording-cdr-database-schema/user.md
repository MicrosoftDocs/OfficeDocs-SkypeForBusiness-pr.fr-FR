---
title: Affichage utilisateur
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: L’affichage utilisateur stocke les informations sur les utilisateurs qui ont participé à des appels ou des sessions ayant des enregistrements dans la base de données. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 1d170b558dbf77cd8ebeff09a914826830d5621d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814832"
---
# <a name="user-view"></a><span data-ttu-id="1027c-104">Affichage utilisateur</span><span class="sxs-lookup"><span data-stu-id="1027c-104">User view</span></span>
 
<span data-ttu-id="1027c-105">L’affichage utilisateur stocke les informations sur les utilisateurs qui ont participé à des appels ou des sessions ayant des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="1027c-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="1027c-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1027c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="1027c-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1027c-107">**Column**</span></span>|<span data-ttu-id="1027c-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="1027c-108">**Data Type**</span></span>|<span data-ttu-id="1027c-109">**Détails**</span><span class="sxs-lookup"><span data-stu-id="1027c-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1027c-110">UserId</span><span class="sxs-lookup"><span data-stu-id="1027c-110">UserId</span></span>  <br/> |<span data-ttu-id="1027c-111">int</span><span class="sxs-lookup"><span data-stu-id="1027c-111">int</span></span>  <br/> |<span data-ttu-id="1027c-112">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1027c-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="1027c-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="1027c-113">UserUri</span></span>  <br/> |<span data-ttu-id="1027c-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1027c-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="1027c-115">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1027c-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="1027c-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="1027c-116">TenantKey</span></span>  <br/> |<span data-ttu-id="1027c-117">identificateur</span><span class="sxs-lookup"><span data-stu-id="1027c-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="1027c-118">Client de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1027c-118">Tenant of user.</span></span> <span data-ttu-id="1027c-119">Pour plus d’informations, voir la [table locataires](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="1027c-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="1027c-120">UriType</span><span class="sxs-lookup"><span data-stu-id="1027c-120">UriType</span></span>  <br/> |<span data-ttu-id="1027c-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1027c-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1027c-122">Type d’URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1027c-122">Type of user URI.</span></span> <span data-ttu-id="1027c-123">Pour plus d’informations, voir la [table UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="1027c-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

