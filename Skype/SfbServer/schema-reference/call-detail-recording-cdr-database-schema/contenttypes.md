---
title: Table ContentTypes dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La table ContentTypes est une table de prise en charge qui stocke une liste des types de contenu utilisés dans les sessions d’égal à égal et des sessions de conférence. Chaque enregistrement de la table représente un type de contenu.
ms.openlocfilehash: 77bbe375a5870d11c7e4a17a0f32392fe14975a0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213248"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="f2aff-104">Table ContentTypes dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f2aff-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f2aff-105">La table ContentTypes est une table de prise en charge qui stocke une liste des types de contenu utilisés dans les sessions d’égal à égal et des sessions de conférence.</span><span class="sxs-lookup"><span data-stu-id="f2aff-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="f2aff-106">Chaque enregistrement de la table représente un type de contenu.</span><span class="sxs-lookup"><span data-stu-id="f2aff-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="f2aff-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f2aff-107">**Column**</span></span>|<span data-ttu-id="f2aff-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="f2aff-108">**Data Type**</span></span>|<span data-ttu-id="f2aff-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="f2aff-109">**Key/Index**</span></span>|<span data-ttu-id="f2aff-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="f2aff-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f2aff-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="f2aff-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="f2aff-112">int</span><span class="sxs-lookup"><span data-stu-id="f2aff-112">int</span></span>  <br/> |<span data-ttu-id="f2aff-113">Principal</span><span class="sxs-lookup"><span data-stu-id="f2aff-113">Primary</span></span>  <br/> |<span data-ttu-id="f2aff-114">Numéro unique identifiant le type de contenu.</span><span class="sxs-lookup"><span data-stu-id="f2aff-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="f2aff-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="f2aff-115">**ContentType**</span></span> <br/> |<span data-ttu-id="f2aff-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f2aff-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="f2aff-117">Nom du type de contenu.</span><span class="sxs-lookup"><span data-stu-id="f2aff-117">Content type name.</span></span>  <br/> |
   

