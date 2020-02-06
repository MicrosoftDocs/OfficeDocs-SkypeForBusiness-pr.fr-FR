---
title: Table Roles
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La table rôles est une table statique qui contient la liste des rôles de conférence possibles, tels que participant et présentateur.
ms.openlocfilehash: 8ebd01bc9cc51b33d28f87aa85be1473a6397201
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814932"
---
# <a name="roles-table"></a><span data-ttu-id="f2130-103">Table Roles</span><span class="sxs-lookup"><span data-stu-id="f2130-103">Roles table</span></span>
 
<span data-ttu-id="f2130-104">La table rôles est une table statique qui contient la liste des rôles de conférence possibles, tels que participant et présentateur.</span><span class="sxs-lookup"><span data-stu-id="f2130-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="f2130-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f2130-105">**Column**</span></span>|<span data-ttu-id="f2130-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="f2130-106">**Data Type**</span></span>|<span data-ttu-id="f2130-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="f2130-107">**Key/Index**</span></span>|<span data-ttu-id="f2130-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="f2130-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f2130-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="f2130-109">**RoleId**</span></span> <br/> |<span data-ttu-id="f2130-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="f2130-110">tinyint</span></span>  <br/> |<span data-ttu-id="f2130-111">Principal</span><span class="sxs-lookup"><span data-stu-id="f2130-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="f2130-112">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="f2130-112">**Role**</span></span> <br/> |<span data-ttu-id="f2130-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f2130-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="f2130-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="f2130-114">Allowed values:</span></span> <br/>  <span data-ttu-id="f2130-115">0-Inconnu</span><span class="sxs-lookup"><span data-stu-id="f2130-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="f2130-116">1-présentateur</span><span class="sxs-lookup"><span data-stu-id="f2130-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="f2130-117">2 participants</span><span class="sxs-lookup"><span data-stu-id="f2130-117">2 - Attendee</span></span> <br/> |
   

