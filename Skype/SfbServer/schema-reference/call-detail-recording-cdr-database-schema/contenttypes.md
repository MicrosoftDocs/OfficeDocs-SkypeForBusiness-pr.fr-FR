---
title: Table ContentTypes dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La table ContentTypes est une table qui contient une liste des types de contenu utilisés dans les sessions d’égal à égal et de conférences. Chaque enregistrement de la table représente un type de contenu.
ms.openlocfilehash: 6dadf7de0107005cca751e27f0c0250bc8f9f03a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815302"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8e68a-104">Table ContentTypes dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="8e68a-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8e68a-105">La table ContentTypes est une table qui contient une liste des types de contenu utilisés dans les sessions d’égal à égal et de conférences.</span><span class="sxs-lookup"><span data-stu-id="8e68a-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="8e68a-106">Chaque enregistrement de la table représente un type de contenu.</span><span class="sxs-lookup"><span data-stu-id="8e68a-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="8e68a-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8e68a-107">**Column**</span></span>|<span data-ttu-id="8e68a-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="8e68a-108">**Data Type**</span></span>|<span data-ttu-id="8e68a-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="8e68a-109">**Key/Index**</span></span>|<span data-ttu-id="8e68a-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="8e68a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8e68a-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="8e68a-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="8e68a-112">int</span><span class="sxs-lookup"><span data-stu-id="8e68a-112">int</span></span>  <br/> |<span data-ttu-id="8e68a-113">Principal</span><span class="sxs-lookup"><span data-stu-id="8e68a-113">Primary</span></span>  <br/> |<span data-ttu-id="8e68a-114">Numéro unique identifiant le type de contenu.</span><span class="sxs-lookup"><span data-stu-id="8e68a-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="8e68a-115">**Indiquez**</span><span class="sxs-lookup"><span data-stu-id="8e68a-115">**ContentType**</span></span> <br/> |<span data-ttu-id="8e68a-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8e68a-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="8e68a-117">Nom du type de contenu.</span><span class="sxs-lookup"><span data-stu-id="8e68a-117">Content type name.</span></span>  <br/> |
   

