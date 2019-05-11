---
title: Table Users
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Le tableau utilisateurs est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un utilisateur impliqué dans les appels ou des sessions disposant d’enregistrements dans la base de données.
ms.openlocfilehash: fbe3ff7d2570f78cdf3b3418629fb9fd6209d944
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929986"
---
# <a name="users-table"></a><span data-ttu-id="1b6f9-104">Table Users</span><span class="sxs-lookup"><span data-stu-id="1b6f9-104">Users table</span></span>
 
<span data-ttu-id="1b6f9-105">Le tableau utilisateurs est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="1b6f9-105">The Users table is a supporting table.</span></span> <span data-ttu-id="1b6f9-106">Chaque enregistrement de la table stocke des informations sur un utilisateur impliqué dans les appels ou des sessions disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="1b6f9-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="1b6f9-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1b6f9-107">**Column**</span></span>|<span data-ttu-id="1b6f9-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="1b6f9-108">**Data Type**</span></span>|<span data-ttu-id="1b6f9-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="1b6f9-109">**Key/Index**</span></span>|<span data-ttu-id="1b6f9-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="1b6f9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1b6f9-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="1b6f9-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="1b6f9-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="1b6f9-112">datetime</span></span>  <br/> ||<span data-ttu-id="1b6f9-113">Horodatage pour utilisation interne.</span><span class="sxs-lookup"><span data-stu-id="1b6f9-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="1b6f9-114">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="1b6f9-114">**UserId**</span></span> <br/> |<span data-ttu-id="1b6f9-115">int</span><span class="sxs-lookup"><span data-stu-id="1b6f9-115">int</span></span>  <br/> |<span data-ttu-id="1b6f9-116">Principal</span><span class="sxs-lookup"><span data-stu-id="1b6f9-116">Primary</span></span>  <br/> |<span data-ttu-id="1b6f9-117">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1b6f9-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="1b6f9-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="1b6f9-118">**UserUri**</span></span> <br/> |<span data-ttu-id="1b6f9-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="1b6f9-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="1b6f9-120">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1b6f9-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="1b6f9-121">**ID client sur**</span><span class="sxs-lookup"><span data-stu-id="1b6f9-121">**TenantId**</span></span> <br/> |<span data-ttu-id="1b6f9-122">int</span><span class="sxs-lookup"><span data-stu-id="1b6f9-122">int</span></span>  <br/> |<span data-ttu-id="1b6f9-123">Étrangère</span><span class="sxs-lookup"><span data-stu-id="1b6f9-123">Foreign</span></span>  <br/> |<span data-ttu-id="1b6f9-124">Cet ID de client. du utilisateur</span><span class="sxs-lookup"><span data-stu-id="1b6f9-124">This user's Tenant ID.</span></span> <span data-ttu-id="1b6f9-125">Consultez le [tableau des clients](tenants.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="1b6f9-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="1b6f9-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="1b6f9-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="1b6f9-127">int</span><span class="sxs-lookup"><span data-stu-id="1b6f9-127">int</span></span>  <br/> |<span data-ttu-id="1b6f9-128">Étrangère</span><span class="sxs-lookup"><span data-stu-id="1b6f9-128">Foreign</span></span>  <br/> |<span data-ttu-id="1b6f9-129">Type d’URI de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1b6f9-129">This user's URI type.</span></span> <span data-ttu-id="1b6f9-130">Consultez la [table UriTypes](uritypes.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="1b6f9-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

