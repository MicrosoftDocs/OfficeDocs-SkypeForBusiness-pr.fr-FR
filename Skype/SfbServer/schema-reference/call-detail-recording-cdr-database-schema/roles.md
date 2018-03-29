---
title: Table Roles
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Le tableau rôles est une table statique qui stocke la liste des rôles de conférence possible, par exemple du présentateur ou du participant.
ms.openlocfilehash: a9f35c510eaca054dd504db4045686cb4eeaac4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="roles-table"></a><span data-ttu-id="a8e06-103">Table Roles</span><span class="sxs-lookup"><span data-stu-id="a8e06-103">Roles table</span></span>
 
<span data-ttu-id="a8e06-104">Le tableau rôles est une table statique qui stocke la liste des rôles de conférence possible, par exemple du présentateur ou du participant.</span><span class="sxs-lookup"><span data-stu-id="a8e06-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="a8e06-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a8e06-105">**Column**</span></span>|<span data-ttu-id="a8e06-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="a8e06-106">**Data Type**</span></span>|<span data-ttu-id="a8e06-107">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="a8e06-107">**Key/Index**</span></span>|<span data-ttu-id="a8e06-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="a8e06-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a8e06-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="a8e06-109">**RoleId**</span></span> <br/> |<span data-ttu-id="a8e06-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="a8e06-110">tinyint</span></span>  <br/> |<span data-ttu-id="a8e06-111">Principal</span><span class="sxs-lookup"><span data-stu-id="a8e06-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="a8e06-112">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="a8e06-112">**Role**</span></span> <br/> |<span data-ttu-id="a8e06-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a8e06-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="a8e06-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="a8e06-114">Allowed values:</span></span> <br/>  <span data-ttu-id="a8e06-115">0 - inconnu</span><span class="sxs-lookup"><span data-stu-id="a8e06-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="a8e06-116">1 - présentateur</span><span class="sxs-lookup"><span data-stu-id="a8e06-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="a8e06-117">2 - participant</span><span class="sxs-lookup"><span data-stu-id="a8e06-117">2 - Attendee</span></span> <br/> |
   

