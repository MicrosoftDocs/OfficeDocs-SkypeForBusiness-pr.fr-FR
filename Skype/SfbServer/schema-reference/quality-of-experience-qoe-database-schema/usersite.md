---
title: Table UserSite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La UserSite table est une table de prise en charge. Chaque enregistrement représente un site utilisateur défini dans les paramètres de configuration réseau.
ms.openlocfilehash: 519cedc35c03fd9bcb5479ea3cecf75ec617917c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906952"
---
# <a name="usersite-table"></a><span data-ttu-id="b548f-104">Table UserSite</span><span class="sxs-lookup"><span data-stu-id="b548f-104">UserSite table</span></span>
 
<span data-ttu-id="b548f-105">La UserSite table est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="b548f-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="b548f-106">Chaque enregistrement représente un site utilisateur défini dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="b548f-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="b548f-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b548f-107">**Column**</span></span>|<span data-ttu-id="b548f-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="b548f-108">**Data Type**</span></span>|<span data-ttu-id="b548f-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="b548f-109">**Key/Index**</span></span>|<span data-ttu-id="b548f-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="b548f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b548f-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="b548f-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="b548f-112">int</span><span class="sxs-lookup"><span data-stu-id="b548f-112">int</span></span>  <br/> |<span data-ttu-id="b548f-113">Principal</span><span class="sxs-lookup"><span data-stu-id="b548f-113">Primary</span></span>  <br/> |<span data-ttu-id="b548f-114">Numéro unique identifiant le site de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b548f-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="b548f-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="b548f-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="b548f-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="b548f-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="b548f-117">Unique</span><span class="sxs-lookup"><span data-stu-id="b548f-117">Unique</span></span>  <br/> |<span data-ttu-id="b548f-118">Nom d’utilisateur du site.</span><span class="sxs-lookup"><span data-stu-id="b548f-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="b548f-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="b548f-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="b548f-120">int</span><span class="sxs-lookup"><span data-stu-id="b548f-120">int</span></span>  <br/> |<span data-ttu-id="b548f-121">Étrangère</span><span class="sxs-lookup"><span data-stu-id="b548f-121">Foreign</span></span>  <br/> |<span data-ttu-id="b548f-122">Référencé depuis la [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="b548f-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

