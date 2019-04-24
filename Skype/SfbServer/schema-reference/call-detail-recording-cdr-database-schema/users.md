---
title: Table Users
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Le tableau utilisateurs est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un utilisateur impliqué dans les appels ou des sessions disposant d’enregistrements dans la base de données.
ms.openlocfilehash: 3929ba33737c107ee60ec1e31beebb1addbb2e3f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212739"
---
# <a name="users-table"></a><span data-ttu-id="0f933-104">Table Users</span><span class="sxs-lookup"><span data-stu-id="0f933-104">Users table</span></span>
 
<span data-ttu-id="0f933-105">Le tableau utilisateurs est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0f933-105">The Users table is a supporting table.</span></span> <span data-ttu-id="0f933-106">Chaque enregistrement de la table stocke des informations sur un utilisateur impliqué dans les appels ou des sessions disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="0f933-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="0f933-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0f933-107">**Column**</span></span>|<span data-ttu-id="0f933-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="0f933-108">**Data Type**</span></span>|<span data-ttu-id="0f933-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="0f933-109">**Key/Index**</span></span>|<span data-ttu-id="0f933-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="0f933-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0f933-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="0f933-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="0f933-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="0f933-112">datetime</span></span>  <br/> ||<span data-ttu-id="0f933-113">Horodatage pour utilisation interne.</span><span class="sxs-lookup"><span data-stu-id="0f933-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="0f933-114">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="0f933-114">**UserId**</span></span> <br/> |<span data-ttu-id="0f933-115">int</span><span class="sxs-lookup"><span data-stu-id="0f933-115">int</span></span>  <br/> |<span data-ttu-id="0f933-116">Principal</span><span class="sxs-lookup"><span data-stu-id="0f933-116">Primary</span></span>  <br/> |<span data-ttu-id="0f933-117">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0f933-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="0f933-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="0f933-118">**UserUri**</span></span> <br/> |<span data-ttu-id="0f933-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="0f933-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="0f933-120">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0f933-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="0f933-121">**ID client sur**</span><span class="sxs-lookup"><span data-stu-id="0f933-121">**TenantId**</span></span> <br/> |<span data-ttu-id="0f933-122">int</span><span class="sxs-lookup"><span data-stu-id="0f933-122">int</span></span>  <br/> |<span data-ttu-id="0f933-123">Étrangère</span><span class="sxs-lookup"><span data-stu-id="0f933-123">Foreign</span></span>  <br/> |<span data-ttu-id="0f933-124">Cet ID de client. du utilisateur</span><span class="sxs-lookup"><span data-stu-id="0f933-124">This user's Tenant ID.</span></span> <span data-ttu-id="0f933-125">Consultez le [tableau des clients](tenants.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="0f933-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0f933-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="0f933-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="0f933-127">int</span><span class="sxs-lookup"><span data-stu-id="0f933-127">int</span></span>  <br/> |<span data-ttu-id="0f933-128">Étrangère</span><span class="sxs-lookup"><span data-stu-id="0f933-128">Foreign</span></span>  <br/> |<span data-ttu-id="0f933-129">Type d’URI de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0f933-129">This user's URI type.</span></span> <span data-ttu-id="0f933-130">Consultez la [table UriTypes](uritypes.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="0f933-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

