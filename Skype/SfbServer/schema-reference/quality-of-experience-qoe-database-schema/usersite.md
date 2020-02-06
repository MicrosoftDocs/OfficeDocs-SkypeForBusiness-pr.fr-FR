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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La table UserSite est une table de prise en charge. Chaque enregistrement représente un site d’utilisateur défini dans les paramètres de configuration réseau.
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805002"
---
# <a name="usersite-table"></a><span data-ttu-id="0b94f-104">Table UserSite</span><span class="sxs-lookup"><span data-stu-id="0b94f-104">UserSite table</span></span>
 
<span data-ttu-id="0b94f-105">La table UserSite est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0b94f-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="0b94f-106">Chaque enregistrement représente un site d’utilisateur défini dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="0b94f-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="0b94f-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0b94f-107">**Column**</span></span>|<span data-ttu-id="0b94f-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="0b94f-108">**Data Type**</span></span>|<span data-ttu-id="0b94f-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="0b94f-109">**Key/Index**</span></span>|<span data-ttu-id="0b94f-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="0b94f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0b94f-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="0b94f-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="0b94f-112">int</span><span class="sxs-lookup"><span data-stu-id="0b94f-112">int</span></span>  <br/> |<span data-ttu-id="0b94f-113">Principal</span><span class="sxs-lookup"><span data-stu-id="0b94f-113">Primary</span></span>  <br/> |<span data-ttu-id="0b94f-114">Numéro unique identifiant le site de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0b94f-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="0b94f-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="0b94f-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="0b94f-116">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0b94f-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="0b94f-117">Différent</span><span class="sxs-lookup"><span data-stu-id="0b94f-117">Unique</span></span>  <br/> |<span data-ttu-id="0b94f-118">Nom du site de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0b94f-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="0b94f-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="0b94f-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="0b94f-120">int</span><span class="sxs-lookup"><span data-stu-id="0b94f-120">int</span></span>  <br/> |<span data-ttu-id="0b94f-121">Externes</span><span class="sxs-lookup"><span data-stu-id="0b94f-121">Foreign</span></span>  <br/> |<span data-ttu-id="0b94f-122">Référencé à partir de la [table région](region.md).</span><span class="sxs-lookup"><span data-stu-id="0b94f-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

