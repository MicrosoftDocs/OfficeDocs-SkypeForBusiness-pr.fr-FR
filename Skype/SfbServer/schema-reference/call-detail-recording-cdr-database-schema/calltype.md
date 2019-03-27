---
title: Table CallType dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La table CallType est une table statique qui stocke la liste des types d’appels possibles.
ms.openlocfilehash: 29e5ed85de5917092ad00cd0e1aa60fec1a31b22
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883178"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="38674-103">Table CallType dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="38674-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="38674-104">La table CallType est une table statique qui stocke la liste des types d’appels possibles.</span><span class="sxs-lookup"><span data-stu-id="38674-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="38674-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="38674-105">**Column**</span></span>|<span data-ttu-id="38674-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="38674-106">**Data Type**</span></span>|<span data-ttu-id="38674-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="38674-107">**Key/Index**</span></span>|<span data-ttu-id="38674-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="38674-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="38674-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="38674-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="38674-110">int</span><span class="sxs-lookup"><span data-stu-id="38674-110">int</span></span>  <br/> |<span data-ttu-id="38674-111">Principal</span><span class="sxs-lookup"><span data-stu-id="38674-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="38674-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="38674-112">**CallType**</span></span> <br/> |<span data-ttu-id="38674-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="38674-113">nvarchar</span></span>  <br/> || <span data-ttu-id="38674-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="38674-114">Allowed values:</span></span> <br/>  <span data-ttu-id="38674-115">0 : inconnu</span><span class="sxs-lookup"><span data-stu-id="38674-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="38674-116">1 - pic</span><span class="sxs-lookup"><span data-stu-id="38674-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="38674-117">2 : Partage d’application</span><span class="sxs-lookup"><span data-stu-id="38674-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="38674-118">3--audio</span><span class="sxs-lookup"><span data-stu-id="38674-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="38674-119">4 - audio et vidéo</span><span class="sxs-lookup"><span data-stu-id="38674-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="38674-120">5 - transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="38674-120">5 - File Transfer</span></span> <br/> |
   

