---
title: Table UserSite
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La UserSite table est une table de prise en charge. Chaque enregistrement représente un site utilisateur défini dans les paramètres de configuration réseau.
ms.openlocfilehash: a52f5cd9aa7059e2b545dec3bcc7ccb86191347a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885887"
---
# <a name="usersite-table"></a><span data-ttu-id="c4cb7-104">Table UserSite</span><span class="sxs-lookup"><span data-stu-id="c4cb7-104">UserSite table</span></span>
 
<span data-ttu-id="c4cb7-105">La UserSite table est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c4cb7-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="c4cb7-106">Chaque enregistrement représente un site utilisateur défini dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="c4cb7-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="c4cb7-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c4cb7-107">**Column**</span></span>|<span data-ttu-id="c4cb7-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="c4cb7-108">**Data Type**</span></span>|<span data-ttu-id="c4cb7-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="c4cb7-109">**Key/Index**</span></span>|<span data-ttu-id="c4cb7-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="c4cb7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c4cb7-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="c4cb7-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="c4cb7-112">int</span><span class="sxs-lookup"><span data-stu-id="c4cb7-112">int</span></span>  <br/> |<span data-ttu-id="c4cb7-113">Principal</span><span class="sxs-lookup"><span data-stu-id="c4cb7-113">Primary</span></span>  <br/> |<span data-ttu-id="c4cb7-114">Numéro unique identifiant le site de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c4cb7-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="c4cb7-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="c4cb7-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="c4cb7-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="c4cb7-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="c4cb7-117">Unique</span><span class="sxs-lookup"><span data-stu-id="c4cb7-117">Unique</span></span>  <br/> |<span data-ttu-id="c4cb7-118">Nom d’utilisateur du site.</span><span class="sxs-lookup"><span data-stu-id="c4cb7-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="c4cb7-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="c4cb7-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="c4cb7-120">int</span><span class="sxs-lookup"><span data-stu-id="c4cb7-120">int</span></span>  <br/> |<span data-ttu-id="c4cb7-121">Étrangère</span><span class="sxs-lookup"><span data-stu-id="c4cb7-121">Foreign</span></span>  <br/> |<span data-ttu-id="c4cb7-122">Référencé depuis la [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="c4cb7-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

