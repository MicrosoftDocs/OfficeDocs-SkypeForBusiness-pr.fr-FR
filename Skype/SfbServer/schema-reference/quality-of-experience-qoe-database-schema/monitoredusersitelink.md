---
title: Table MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La table MonitoredUserSiteLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux sites d’utilisateurs.
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294851"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="e7184-104">Table MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="e7184-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="e7184-105">La table MonitoredUserSiteLink est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="e7184-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="e7184-106">Chaque enregistrement représente un lien entre deux sites d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e7184-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="e7184-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e7184-107">**Column**</span></span>|<span data-ttu-id="e7184-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e7184-108">**Data Type**</span></span>|<span data-ttu-id="e7184-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="e7184-109">**Key/Index**</span></span>|<span data-ttu-id="e7184-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e7184-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e7184-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="e7184-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="e7184-112">int</span><span class="sxs-lookup"><span data-stu-id="e7184-112">int</span></span>  <br/> |<span data-ttu-id="e7184-113">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="e7184-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e7184-114">Fait référence à partir de la [table UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="e7184-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="e7184-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="e7184-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="e7184-116">int</span><span class="sxs-lookup"><span data-stu-id="e7184-116">int</span></span>  <br/> |<span data-ttu-id="e7184-117">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="e7184-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e7184-118">Référence à partir de la [table UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="e7184-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

