---
title: Table Users
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La table Users est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un utilisateur impliqué dans des appels ou des sessions qui ont des enregistrements dans la base de données.
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831614"
---
# <a name="users-table"></a><span data-ttu-id="dd6dd-104">Table Users</span><span class="sxs-lookup"><span data-stu-id="dd6dd-104">Users table</span></span>
 
<span data-ttu-id="dd6dd-105">La table Users est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="dd6dd-105">The Users table is a supporting table.</span></span> <span data-ttu-id="dd6dd-106">Chaque enregistrement de la table stocke des informations sur un utilisateur impliqué dans des appels ou des sessions qui ont des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="dd6dd-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="dd6dd-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="dd6dd-107">**Column**</span></span>|<span data-ttu-id="dd6dd-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="dd6dd-108">**Data Type**</span></span>|<span data-ttu-id="dd6dd-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="dd6dd-109">**Key/Index**</span></span>|<span data-ttu-id="dd6dd-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="dd6dd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dd6dd-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="dd6dd-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="dd6dd-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="dd6dd-112">datetime</span></span>  <br/> ||<span data-ttu-id="dd6dd-113">Horodat pour une utilisation interne.</span><span class="sxs-lookup"><span data-stu-id="dd6dd-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="dd6dd-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="dd6dd-114">**UserId**</span></span> <br/> |<span data-ttu-id="dd6dd-115">int</span><span class="sxs-lookup"><span data-stu-id="dd6dd-115">int</span></span>  <br/> |<span data-ttu-id="dd6dd-116">Primaire</span><span class="sxs-lookup"><span data-stu-id="dd6dd-116">Primary</span></span>  <br/> |<span data-ttu-id="dd6dd-117">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dd6dd-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="dd6dd-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="dd6dd-118">**UserUri**</span></span> <br/> |<span data-ttu-id="dd6dd-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="dd6dd-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="dd6dd-120">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dd6dd-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="dd6dd-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="dd6dd-121">**TenantId**</span></span> <br/> |<span data-ttu-id="dd6dd-122">int</span><span class="sxs-lookup"><span data-stu-id="dd6dd-122">int</span></span>  <br/> |<span data-ttu-id="dd6dd-123">Étranger</span><span class="sxs-lookup"><span data-stu-id="dd6dd-123">Foreign</span></span>  <br/> |<span data-ttu-id="dd6dd-124">ID de locataire de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dd6dd-124">This user's Tenant ID.</span></span> <span data-ttu-id="dd6dd-125">Pour plus [d’informations, voir la table Tenants.](tenants.md)</span><span class="sxs-lookup"><span data-stu-id="dd6dd-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="dd6dd-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="dd6dd-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="dd6dd-127">int</span><span class="sxs-lookup"><span data-stu-id="dd6dd-127">int</span></span>  <br/> |<span data-ttu-id="dd6dd-128">Étranger</span><span class="sxs-lookup"><span data-stu-id="dd6dd-128">Foreign</span></span>  <br/> |<span data-ttu-id="dd6dd-129">Type d’URI de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dd6dd-129">This user's URI type.</span></span> <span data-ttu-id="dd6dd-130">Pour plus [d’informations, voir la table UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="dd6dd-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

