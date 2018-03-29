---
title: Table MonitoredUserSiteLink
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La table MonitoredUserSiteLink est un tableau de prise en charge. Chaque enregistrement représente une liaison entre deux sites d’utilisateur.
ms.openlocfilehash: 7b9b2ddab3bff48105a24f586816666b15c0b9b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="07ade-104">Table MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="07ade-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="07ade-105">La table MonitoredUserSiteLink est un tableau de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="07ade-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="07ade-106">Chaque enregistrement représente une liaison entre deux sites d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="07ade-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="07ade-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="07ade-107">**Column**</span></span>|<span data-ttu-id="07ade-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="07ade-108">**Data Type**</span></span>|<span data-ttu-id="07ade-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="07ade-109">**Key/Index**</span></span>|<span data-ttu-id="07ade-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="07ade-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07ade-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="07ade-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="07ade-112">int</span><span class="sxs-lookup"><span data-stu-id="07ade-112">int</span></span>  <br/> |<span data-ttu-id="07ade-113">Primaires et étrangères</span><span class="sxs-lookup"><span data-stu-id="07ade-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="07ade-114">Référencé à partir de la [table de UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="07ade-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="07ade-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="07ade-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="07ade-116">int</span><span class="sxs-lookup"><span data-stu-id="07ade-116">int</span></span>  <br/> |<span data-ttu-id="07ade-117">Primaires et étrangères</span><span class="sxs-lookup"><span data-stu-id="07ade-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="07ade-118">Référence de la [table de UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="07ade-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

