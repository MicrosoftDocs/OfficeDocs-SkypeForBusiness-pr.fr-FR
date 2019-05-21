---
title: Table UserSite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La table UserSite est une table de prise en charge. Chaque enregistrement représente un site d’utilisateur défini dans les paramètres de configuration réseau.
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294571"
---
# <a name="usersite-table"></a><span data-ttu-id="cb4f2-104">Table UserSite</span><span class="sxs-lookup"><span data-stu-id="cb4f2-104">UserSite table</span></span>
 
<span data-ttu-id="cb4f2-105">La table UserSite est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="cb4f2-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="cb4f2-106">Chaque enregistrement représente un site d’utilisateur défini dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="cb4f2-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="cb4f2-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cb4f2-107">**Column**</span></span>|<span data-ttu-id="cb4f2-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="cb4f2-108">**Data Type**</span></span>|<span data-ttu-id="cb4f2-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="cb4f2-109">**Key/Index**</span></span>|<span data-ttu-id="cb4f2-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="cb4f2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cb4f2-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="cb4f2-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="cb4f2-112">int</span><span class="sxs-lookup"><span data-stu-id="cb4f2-112">int</span></span>  <br/> |<span data-ttu-id="cb4f2-113">Principal</span><span class="sxs-lookup"><span data-stu-id="cb4f2-113">Primary</span></span>  <br/> |<span data-ttu-id="cb4f2-114">Numéro unique identifiant le site de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cb4f2-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="cb4f2-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="cb4f2-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="cb4f2-116">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="cb4f2-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="cb4f2-117">Différent</span><span class="sxs-lookup"><span data-stu-id="cb4f2-117">Unique</span></span>  <br/> |<span data-ttu-id="cb4f2-118">Nom du site de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cb4f2-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="cb4f2-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="cb4f2-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="cb4f2-120">int</span><span class="sxs-lookup"><span data-stu-id="cb4f2-120">int</span></span>  <br/> |<span data-ttu-id="cb4f2-121">Externes</span><span class="sxs-lookup"><span data-stu-id="cb4f2-121">Foreign</span></span>  <br/> |<span data-ttu-id="cb4f2-122">Référencé à partir de la [table région](region.md).</span><span class="sxs-lookup"><span data-stu-id="cb4f2-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

