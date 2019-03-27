---
title: Table Roles
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La table Roles est une table statique qui stocke la liste des rôles possibles pour les conférences, tels que participant et présentateur.
ms.openlocfilehash: 2b7759cc600471a8bf1b989ce429f6b2a4149ee0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891712"
---
# <a name="roles-table"></a><span data-ttu-id="a1f69-103">Table Roles</span><span class="sxs-lookup"><span data-stu-id="a1f69-103">Roles table</span></span>
 
<span data-ttu-id="a1f69-104">La table Roles est une table statique qui stocke la liste des rôles possibles pour les conférences, tels que participant et présentateur.</span><span class="sxs-lookup"><span data-stu-id="a1f69-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="a1f69-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a1f69-105">**Column**</span></span>|<span data-ttu-id="a1f69-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="a1f69-106">**Data Type**</span></span>|<span data-ttu-id="a1f69-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="a1f69-107">**Key/Index**</span></span>|<span data-ttu-id="a1f69-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="a1f69-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a1f69-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="a1f69-109">**RoleId**</span></span> <br/> |<span data-ttu-id="a1f69-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="a1f69-110">tinyint</span></span>  <br/> |<span data-ttu-id="a1f69-111">Principal</span><span class="sxs-lookup"><span data-stu-id="a1f69-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="a1f69-112">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="a1f69-112">**Role**</span></span> <br/> |<span data-ttu-id="a1f69-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a1f69-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="a1f69-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="a1f69-114">Allowed values:</span></span> <br/>  <span data-ttu-id="a1f69-115">0 - inconnu</span><span class="sxs-lookup"><span data-stu-id="a1f69-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="a1f69-116">1 - présentateur</span><span class="sxs-lookup"><span data-stu-id="a1f69-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="a1f69-117">2 - participant</span><span class="sxs-lookup"><span data-stu-id="a1f69-117">2 - Attendee</span></span> <br/> |
   

