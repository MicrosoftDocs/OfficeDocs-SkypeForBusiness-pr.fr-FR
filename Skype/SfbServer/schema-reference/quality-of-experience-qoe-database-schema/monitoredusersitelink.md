---
title: Table MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La table MonitoredUserSiteLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux sites d’utilisateur.
ms.openlocfilehash: 18f0931feb46e69db76c93225ccc11398b4d6daf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920011"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="e38c1-104">Table MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="e38c1-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="e38c1-105">La table MonitoredUserSiteLink est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="e38c1-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="e38c1-106">Chaque enregistrement représente un lien entre deux sites d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e38c1-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="e38c1-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e38c1-107">**Column**</span></span>|<span data-ttu-id="e38c1-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e38c1-108">**Data Type**</span></span>|<span data-ttu-id="e38c1-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="e38c1-109">**Key/Index**</span></span>|<span data-ttu-id="e38c1-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e38c1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e38c1-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="e38c1-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="e38c1-112">int</span><span class="sxs-lookup"><span data-stu-id="e38c1-112">int</span></span>  <br/> |<span data-ttu-id="e38c1-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="e38c1-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e38c1-114">Référencé depuis la [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="e38c1-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="e38c1-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="e38c1-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="e38c1-116">int</span><span class="sxs-lookup"><span data-stu-id="e38c1-116">int</span></span>  <br/> |<span data-ttu-id="e38c1-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="e38c1-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e38c1-118">Référence de la [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="e38c1-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

