---
title: Table UserSite
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La table UserSite est un tableau de prise en charge. Chaque enregistrement représente un site de l’utilisateur défini dans le paramètre de configuration réseau.
ms.openlocfilehash: effc2404a91bf122dc9be9ad371372e8355b230f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="usersite-table"></a><span data-ttu-id="cb085-104">Table UserSite</span><span class="sxs-lookup"><span data-stu-id="cb085-104">UserSite table</span></span>
 
<span data-ttu-id="cb085-105">La table UserSite est un tableau de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="cb085-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="cb085-106">Chaque enregistrement représente un site de l’utilisateur défini dans le paramètre de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="cb085-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="cb085-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cb085-107">**Column**</span></span>|<span data-ttu-id="cb085-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="cb085-108">**Data Type**</span></span>|<span data-ttu-id="cb085-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="cb085-109">**Key/Index**</span></span>|<span data-ttu-id="cb085-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="cb085-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cb085-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="cb085-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="cb085-112">int</span><span class="sxs-lookup"><span data-stu-id="cb085-112">int</span></span>  <br/> |<span data-ttu-id="cb085-113">Principal</span><span class="sxs-lookup"><span data-stu-id="cb085-113">Primary</span></span>  <br/> |<span data-ttu-id="cb085-114">Numéro unique identifiant le site de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cb085-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="cb085-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="cb085-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="cb085-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="cb085-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="cb085-117">Unique</span><span class="sxs-lookup"><span data-stu-id="cb085-117">Unique</span></span>  <br/> |<span data-ttu-id="cb085-118">Nom de site de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cb085-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="cb085-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="cb085-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="cb085-120">int</span><span class="sxs-lookup"><span data-stu-id="cb085-120">int</span></span>  <br/> |<span data-ttu-id="cb085-121">Étrangère</span><span class="sxs-lookup"><span data-stu-id="cb085-121">Foreign</span></span>  <br/> |<span data-ttu-id="cb085-122">Référencé à partir de la [table de la région](region.md).</span><span class="sxs-lookup"><span data-stu-id="cb085-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

