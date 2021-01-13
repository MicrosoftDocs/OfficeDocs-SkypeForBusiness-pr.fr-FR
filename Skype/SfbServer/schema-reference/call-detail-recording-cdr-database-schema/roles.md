---
title: Table Roles
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La table Roles est une table statique qui stocke la liste des rôles possibles pour les conférences, tels que participant et présentateur.
ms.openlocfilehash: 6c5e28ccd2d186b0122d70f91621a3365e6d2b07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809974"
---
# <a name="roles-table"></a><span data-ttu-id="c3e2b-103">Table Roles</span><span class="sxs-lookup"><span data-stu-id="c3e2b-103">Roles table</span></span>
 
<span data-ttu-id="c3e2b-104">La table Roles est une table statique qui stocke la liste des rôles possibles pour les conférences, tels que participant et présentateur.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="c3e2b-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c3e2b-105">**Column**</span></span>|<span data-ttu-id="c3e2b-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="c3e2b-106">**Data Type**</span></span>|<span data-ttu-id="c3e2b-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="c3e2b-107">**Key/Index**</span></span>|<span data-ttu-id="c3e2b-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="c3e2b-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c3e2b-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="c3e2b-109">**RoleId**</span></span> <br/> |<span data-ttu-id="c3e2b-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="c3e2b-110">tinyint</span></span>  <br/> |<span data-ttu-id="c3e2b-111">Primaire</span><span class="sxs-lookup"><span data-stu-id="c3e2b-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="c3e2b-112">**Role**</span><span class="sxs-lookup"><span data-stu-id="c3e2b-112">**Role**</span></span> <br/> |<span data-ttu-id="c3e2b-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c3e2b-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="c3e2b-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="c3e2b-114">Allowed values:</span></span> <br/>  <span data-ttu-id="c3e2b-115">0 - Inconnu</span><span class="sxs-lookup"><span data-stu-id="c3e2b-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="c3e2b-116">1 - Présentateur</span><span class="sxs-lookup"><span data-stu-id="c3e2b-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="c3e2b-117">2 - Participant</span><span class="sxs-lookup"><span data-stu-id="c3e2b-117">2 - Attendee</span></span> <br/> |
   

