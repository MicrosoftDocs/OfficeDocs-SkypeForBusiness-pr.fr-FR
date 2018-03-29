---
title: Tableau de types de contenus dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: Le tableau de types de contenus est une table de prise en charge qui stocke une liste des types de contenu utilisés dans les sessions de peer-to-peer et des sessions de conférence. Chaque enregistrement de la table représente un type de contenu.
ms.openlocfilehash: 207e2a4e6ba605950181c437c236205fc8b2778f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="bdda8-104">Tableau de types de contenus dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bdda8-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bdda8-105">Le tableau de types de contenus est une table de prise en charge qui stocke une liste des types de contenu utilisés dans les sessions de peer-to-peer et des sessions de conférence.</span><span class="sxs-lookup"><span data-stu-id="bdda8-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="bdda8-106">Chaque enregistrement de la table représente un type de contenu.</span><span class="sxs-lookup"><span data-stu-id="bdda8-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="bdda8-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="bdda8-107">**Column**</span></span>|<span data-ttu-id="bdda8-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="bdda8-108">**Data Type**</span></span>|<span data-ttu-id="bdda8-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="bdda8-109">**Key/Index**</span></span>|<span data-ttu-id="bdda8-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="bdda8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bdda8-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="bdda8-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="bdda8-112">int</span><span class="sxs-lookup"><span data-stu-id="bdda8-112">int</span></span>  <br/> |<span data-ttu-id="bdda8-113">Principal</span><span class="sxs-lookup"><span data-stu-id="bdda8-113">Primary</span></span>  <br/> |<span data-ttu-id="bdda8-114">Numéro unique identifiant le type de contenu.</span><span class="sxs-lookup"><span data-stu-id="bdda8-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="bdda8-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="bdda8-115">**ContentType**</span></span> <br/> |<span data-ttu-id="bdda8-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bdda8-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="bdda8-117">Nom du type de contenu.</span><span class="sxs-lookup"><span data-stu-id="bdda8-117">Content type name.</span></span>  <br/> |
   

