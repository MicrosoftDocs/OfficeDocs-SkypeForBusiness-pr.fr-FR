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
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La table rôles est une table statique qui contient la liste des rôles de conférence possibles, tels que participant et présentateur.
ms.openlocfilehash: 2cf1fb22230d92951df0b3b8e18a5bd666c73519
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295894"
---
# <a name="roles-table"></a><span data-ttu-id="025f0-103">Table Roles</span><span class="sxs-lookup"><span data-stu-id="025f0-103">Roles table</span></span>
 
<span data-ttu-id="025f0-104">La table rôles est une table statique qui contient la liste des rôles de conférence possibles, tels que participant et présentateur.</span><span class="sxs-lookup"><span data-stu-id="025f0-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="025f0-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="025f0-105">**Column**</span></span>|<span data-ttu-id="025f0-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="025f0-106">**Data Type**</span></span>|<span data-ttu-id="025f0-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="025f0-107">**Key/Index**</span></span>|<span data-ttu-id="025f0-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="025f0-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="025f0-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="025f0-109">**RoleId**</span></span> <br/> |<span data-ttu-id="025f0-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="025f0-110">tinyint</span></span>  <br/> |<span data-ttu-id="025f0-111">Principal</span><span class="sxs-lookup"><span data-stu-id="025f0-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="025f0-112">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="025f0-112">**Role**</span></span> <br/> |<span data-ttu-id="025f0-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="025f0-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="025f0-114">Valeurs autorisées:</span><span class="sxs-lookup"><span data-stu-id="025f0-114">Allowed values:</span></span> <br/>  <span data-ttu-id="025f0-115">0-Inconnu</span><span class="sxs-lookup"><span data-stu-id="025f0-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="025f0-116">1-présentateur</span><span class="sxs-lookup"><span data-stu-id="025f0-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="025f0-117">2 participants</span><span class="sxs-lookup"><span data-stu-id="025f0-117">2 - Attendee</span></span> <br/> |
   

