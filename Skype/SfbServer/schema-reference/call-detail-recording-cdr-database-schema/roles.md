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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212830"
---
# <a name="roles-table"></a><span data-ttu-id="c1451-103">Table Roles</span><span class="sxs-lookup"><span data-stu-id="c1451-103">Roles table</span></span>
 
<span data-ttu-id="c1451-104">La table Roles est une table statique qui stocke la liste des rôles possibles pour les conférences, tels que participant et présentateur.</span><span class="sxs-lookup"><span data-stu-id="c1451-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="c1451-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c1451-105">**Column**</span></span>|<span data-ttu-id="c1451-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="c1451-106">**Data Type**</span></span>|<span data-ttu-id="c1451-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="c1451-107">**Key/Index**</span></span>|<span data-ttu-id="c1451-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="c1451-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c1451-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="c1451-109">**RoleId**</span></span> <br/> |<span data-ttu-id="c1451-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="c1451-110">tinyint</span></span>  <br/> |<span data-ttu-id="c1451-111">Principal</span><span class="sxs-lookup"><span data-stu-id="c1451-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="c1451-112">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="c1451-112">**Role**</span></span> <br/> |<span data-ttu-id="c1451-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c1451-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="c1451-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="c1451-114">Allowed values:</span></span> <br/>  <span data-ttu-id="c1451-115">0 - inconnu</span><span class="sxs-lookup"><span data-stu-id="c1451-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="c1451-116">1 - présentateur</span><span class="sxs-lookup"><span data-stu-id="c1451-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="c1451-117">2 - participant</span><span class="sxs-lookup"><span data-stu-id="c1451-117">2 - Attendee</span></span> <br/> |
   

