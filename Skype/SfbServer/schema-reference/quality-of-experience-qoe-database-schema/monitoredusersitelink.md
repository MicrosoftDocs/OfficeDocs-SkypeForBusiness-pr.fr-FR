---
title: Table MonitoredUserSiteLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La table MonitoredUserSiteLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux sites d’utilisateur.
ms.openlocfilehash: 8022286289d4acd5fab8ea821c72897d9500597b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874258"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="63d28-104">Table MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="63d28-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="63d28-105">La table MonitoredUserSiteLink est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="63d28-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="63d28-106">Chaque enregistrement représente un lien entre deux sites d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="63d28-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="63d28-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="63d28-107">**Column**</span></span>|<span data-ttu-id="63d28-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="63d28-108">**Data Type**</span></span>|<span data-ttu-id="63d28-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="63d28-109">**Key/Index**</span></span>|<span data-ttu-id="63d28-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="63d28-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="63d28-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="63d28-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="63d28-112">int</span><span class="sxs-lookup"><span data-stu-id="63d28-112">int</span></span>  <br/> |<span data-ttu-id="63d28-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="63d28-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="63d28-114">Référencé depuis la [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="63d28-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="63d28-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="63d28-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="63d28-116">int</span><span class="sxs-lookup"><span data-stu-id="63d28-116">int</span></span>  <br/> |<span data-ttu-id="63d28-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="63d28-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="63d28-118">Référence de la [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="63d28-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

