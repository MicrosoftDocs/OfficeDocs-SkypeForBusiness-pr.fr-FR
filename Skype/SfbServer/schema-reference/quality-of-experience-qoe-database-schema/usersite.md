---
title: Table UserSite
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La table UserSite est une table de prise en charge. Chaque enregistrement représente un site d’utilisateurs défini dans les paramètres de configuration réseau.
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799914"
---
# <a name="usersite-table"></a><span data-ttu-id="22d65-104">Table UserSite</span><span class="sxs-lookup"><span data-stu-id="22d65-104">UserSite table</span></span>
 
<span data-ttu-id="22d65-p102">La table UserSite est une table de prise en charge. Chaque enregistrement représente un site d’utilisateurs défini dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="22d65-p102">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="22d65-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="22d65-107">**Column**</span></span>|<span data-ttu-id="22d65-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="22d65-108">**Data Type**</span></span>|<span data-ttu-id="22d65-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="22d65-109">**Key/Index**</span></span>|<span data-ttu-id="22d65-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="22d65-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="22d65-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="22d65-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="22d65-112">int</span><span class="sxs-lookup"><span data-stu-id="22d65-112">int</span></span>  <br/> |<span data-ttu-id="22d65-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="22d65-113">Primary</span></span>  <br/> |<span data-ttu-id="22d65-114">Numéro unique d’identification de ce site utilisateur.</span><span class="sxs-lookup"><span data-stu-id="22d65-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="22d65-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="22d65-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="22d65-116">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="22d65-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="22d65-117">Uniques</span><span class="sxs-lookup"><span data-stu-id="22d65-117">Unique</span></span>  <br/> |<span data-ttu-id="22d65-118">Nom du site utilisateur.</span><span class="sxs-lookup"><span data-stu-id="22d65-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="22d65-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="22d65-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="22d65-120">int</span><span class="sxs-lookup"><span data-stu-id="22d65-120">int</span></span>  <br/> |<span data-ttu-id="22d65-121">Étranger</span><span class="sxs-lookup"><span data-stu-id="22d65-121">Foreign</span></span>  <br/> |<span data-ttu-id="22d65-122">Référencé à partir [de la table Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="22d65-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

