---
title: Table Users
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Le tableau utilisateurs est une table de prise en charge. Chaque enregistrement dans la table stocke des informations sur un utilisateur impliqué dans les appels ou les sessions qui ont des enregistrements dans la base de données.
ms.openlocfilehash: b14350d060485a57b4af42cbfe26db729872f6f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="users-table"></a><span data-ttu-id="aca38-104">Table Users</span><span class="sxs-lookup"><span data-stu-id="aca38-104">Users table</span></span>
 
<span data-ttu-id="aca38-105">Le tableau utilisateurs est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="aca38-105">The Users table is a supporting table.</span></span> <span data-ttu-id="aca38-106">Chaque enregistrement dans la table stocke des informations sur un utilisateur impliqué dans les appels ou les sessions qui ont des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="aca38-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="aca38-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="aca38-107">**Column**</span></span>|<span data-ttu-id="aca38-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="aca38-108">**Data Type**</span></span>|<span data-ttu-id="aca38-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="aca38-109">**Key/Index**</span></span>|<span data-ttu-id="aca38-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="aca38-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aca38-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="aca38-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="aca38-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="aca38-112">datetime</span></span>  <br/> ||<span data-ttu-id="aca38-113">Horodatage pour un usage interne.</span><span class="sxs-lookup"><span data-stu-id="aca38-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="aca38-114">**ID utilisateur**</span><span class="sxs-lookup"><span data-stu-id="aca38-114">**UserId**</span></span> <br/> |<span data-ttu-id="aca38-115">int</span><span class="sxs-lookup"><span data-stu-id="aca38-115">int</span></span>  <br/> |<span data-ttu-id="aca38-116">Principal</span><span class="sxs-lookup"><span data-stu-id="aca38-116">Primary</span></span>  <br/> |<span data-ttu-id="aca38-117">Numéro unique identifiant l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="aca38-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="aca38-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="aca38-118">**UserUri**</span></span> <br/> |<span data-ttu-id="aca38-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="aca38-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="aca38-120">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="aca38-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="aca38-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="aca38-121">**TenantId**</span></span> <br/> |<span data-ttu-id="aca38-122">int</span><span class="sxs-lookup"><span data-stu-id="aca38-122">int</span></span>  <br/> |<span data-ttu-id="aca38-123">Étrangère</span><span class="sxs-lookup"><span data-stu-id="aca38-123">Foreign</span></span>  <br/> |<span data-ttu-id="aca38-124">Cet ID de client. du utilisateur</span><span class="sxs-lookup"><span data-stu-id="aca38-124">This user's Tenant ID.</span></span> <span data-ttu-id="aca38-125">Consultez le [tableau des locataires](tenants.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="aca38-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="aca38-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="aca38-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="aca38-127">int</span><span class="sxs-lookup"><span data-stu-id="aca38-127">int</span></span>  <br/> |<span data-ttu-id="aca38-128">Étrangère</span><span class="sxs-lookup"><span data-stu-id="aca38-128">Foreign</span></span>  <br/> |<span data-ttu-id="aca38-129">Type d’URI de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="aca38-129">This user's URI type.</span></span> <span data-ttu-id="aca38-130">Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="aca38-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

