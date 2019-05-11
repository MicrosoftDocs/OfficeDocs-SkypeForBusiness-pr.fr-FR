---
title: Table Roles
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La table Roles est une table statique qui stocke la liste des rôles possibles pour les conférences, tels que participant et présentateur.
ms.openlocfilehash: e0088d059d6e4ed536e5f52e1290211377438889
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930303"
---
# <a name="roles-table"></a><span data-ttu-id="4223f-103">Table Roles</span><span class="sxs-lookup"><span data-stu-id="4223f-103">Roles table</span></span>
 
<span data-ttu-id="4223f-104">La table Roles est une table statique qui stocke la liste des rôles possibles pour les conférences, tels que participant et présentateur.</span><span class="sxs-lookup"><span data-stu-id="4223f-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="4223f-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="4223f-105">**Column**</span></span>|<span data-ttu-id="4223f-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="4223f-106">**Data Type**</span></span>|<span data-ttu-id="4223f-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="4223f-107">**Key/Index**</span></span>|<span data-ttu-id="4223f-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="4223f-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4223f-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="4223f-109">**RoleId**</span></span> <br/> |<span data-ttu-id="4223f-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="4223f-110">tinyint</span></span>  <br/> |<span data-ttu-id="4223f-111">Principal</span><span class="sxs-lookup"><span data-stu-id="4223f-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="4223f-112">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="4223f-112">**Role**</span></span> <br/> |<span data-ttu-id="4223f-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4223f-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="4223f-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="4223f-114">Allowed values:</span></span> <br/>  <span data-ttu-id="4223f-115">0 - inconnu</span><span class="sxs-lookup"><span data-stu-id="4223f-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="4223f-116">1 - présentateur</span><span class="sxs-lookup"><span data-stu-id="4223f-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="4223f-117">2 - participant</span><span class="sxs-lookup"><span data-stu-id="4223f-117">2 - Attendee</span></span> <br/> |
   

