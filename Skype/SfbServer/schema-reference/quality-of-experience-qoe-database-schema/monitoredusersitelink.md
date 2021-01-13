---
title: Table MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 88b4d385f3c96dc93a519274c584e1f99584982f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806354"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="3f7f0-104">Table MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="3f7f0-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="3f7f0-p102">La table MonitoredUserSiteLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux sites d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3f7f0-p102">The MonitoredUserSiteLink table is a supporting table. Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="3f7f0-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3f7f0-107">**Column**</span></span>|<span data-ttu-id="3f7f0-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="3f7f0-108">**Data Type**</span></span>|<span data-ttu-id="3f7f0-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="3f7f0-109">**Key/Index**</span></span>|<span data-ttu-id="3f7f0-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="3f7f0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3f7f0-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="3f7f0-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="3f7f0-112">int</span><span class="sxs-lookup"><span data-stu-id="3f7f0-112">int</span></span>  <br/> |<span data-ttu-id="3f7f0-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="3f7f0-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3f7f0-114">Référencé à partir de [la table UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="3f7f0-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="3f7f0-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="3f7f0-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="3f7f0-116">int</span><span class="sxs-lookup"><span data-stu-id="3f7f0-116">int</span></span>  <br/> |<span data-ttu-id="3f7f0-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="3f7f0-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3f7f0-118">Référence à partir de [la table UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="3f7f0-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

