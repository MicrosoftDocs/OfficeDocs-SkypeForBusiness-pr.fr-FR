---
title: Table Users
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La table users est une table de prise en charge. Chaque enregistrement de la table stocke des informations relatives à un utilisateur impliqué dans des appels ou des sessions ayant des enregistrements dans la base de données.
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814802"
---
# <a name="users-table"></a><span data-ttu-id="2cad0-104">Table Users</span><span class="sxs-lookup"><span data-stu-id="2cad0-104">Users table</span></span>
 
<span data-ttu-id="2cad0-105">La table users est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="2cad0-105">The Users table is a supporting table.</span></span> <span data-ttu-id="2cad0-106">Chaque enregistrement de la table stocke des informations relatives à un utilisateur impliqué dans des appels ou des sessions ayant des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2cad0-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="2cad0-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2cad0-107">**Column**</span></span>|<span data-ttu-id="2cad0-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="2cad0-108">**Data Type**</span></span>|<span data-ttu-id="2cad0-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="2cad0-109">**Key/Index**</span></span>|<span data-ttu-id="2cad0-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="2cad0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2cad0-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="2cad0-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="2cad0-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2cad0-112">datetime</span></span>  <br/> ||<span data-ttu-id="2cad0-113">Horodatage pour un usage interne.</span><span class="sxs-lookup"><span data-stu-id="2cad0-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="2cad0-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="2cad0-114">**UserId**</span></span> <br/> |<span data-ttu-id="2cad0-115">int</span><span class="sxs-lookup"><span data-stu-id="2cad0-115">int</span></span>  <br/> |<span data-ttu-id="2cad0-116">Principal</span><span class="sxs-lookup"><span data-stu-id="2cad0-116">Primary</span></span>  <br/> |<span data-ttu-id="2cad0-117">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2cad0-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="2cad0-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="2cad0-118">**UserUri**</span></span> <br/> |<span data-ttu-id="2cad0-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2cad0-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="2cad0-120">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2cad0-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="2cad0-121">**IDClient**</span><span class="sxs-lookup"><span data-stu-id="2cad0-121">**TenantId**</span></span> <br/> |<span data-ttu-id="2cad0-122">int</span><span class="sxs-lookup"><span data-stu-id="2cad0-122">int</span></span>  <br/> |<span data-ttu-id="2cad0-123">Externes</span><span class="sxs-lookup"><span data-stu-id="2cad0-123">Foreign</span></span>  <br/> |<span data-ttu-id="2cad0-124">ID de client de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2cad0-124">This user's Tenant ID.</span></span> <span data-ttu-id="2cad0-125">Pour plus d’informations, voir la [table locataires](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="2cad0-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2cad0-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="2cad0-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="2cad0-127">int</span><span class="sxs-lookup"><span data-stu-id="2cad0-127">int</span></span>  <br/> |<span data-ttu-id="2cad0-128">Externes</span><span class="sxs-lookup"><span data-stu-id="2cad0-128">Foreign</span></span>  <br/> |<span data-ttu-id="2cad0-129">Type d’URI de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2cad0-129">This user's URI type.</span></span> <span data-ttu-id="2cad0-130">Pour plus d’informations, voir la [table UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="2cad0-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

