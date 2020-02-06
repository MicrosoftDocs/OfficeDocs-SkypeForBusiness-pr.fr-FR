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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La table MonitoredUserSiteLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux sites d’utilisateurs.
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807792"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="75f65-104">Table MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="75f65-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="75f65-105">La table MonitoredUserSiteLink est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="75f65-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="75f65-106">Chaque enregistrement représente un lien entre deux sites d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="75f65-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="75f65-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="75f65-107">**Column**</span></span>|<span data-ttu-id="75f65-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="75f65-108">**Data Type**</span></span>|<span data-ttu-id="75f65-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="75f65-109">**Key/Index**</span></span>|<span data-ttu-id="75f65-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="75f65-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="75f65-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="75f65-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="75f65-112">int</span><span class="sxs-lookup"><span data-stu-id="75f65-112">int</span></span>  <br/> |<span data-ttu-id="75f65-113">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="75f65-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="75f65-114">Fait référence à partir de la [table UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="75f65-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="75f65-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="75f65-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="75f65-116">int</span><span class="sxs-lookup"><span data-stu-id="75f65-116">int</span></span>  <br/> |<span data-ttu-id="75f65-117">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="75f65-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="75f65-118">Référence à partir de la [table UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="75f65-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

