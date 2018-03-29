---
title: Table CallType dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La table CallType est une table statique qui stocke la liste des types d’appel possibles.
ms.openlocfilehash: e2353176a69db9eada137525561541d26caa7a8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5f158-103">Table CallType dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5f158-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5f158-104">La table CallType est une table statique qui stocke la liste des types d’appel possibles.</span><span class="sxs-lookup"><span data-stu-id="5f158-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="5f158-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5f158-105">**Column**</span></span>|<span data-ttu-id="5f158-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="5f158-106">**Data Type**</span></span>|<span data-ttu-id="5f158-107">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="5f158-107">**Key/Index**</span></span>|<span data-ttu-id="5f158-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="5f158-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f158-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="5f158-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="5f158-110">int</span><span class="sxs-lookup"><span data-stu-id="5f158-110">int</span></span>  <br/> |<span data-ttu-id="5f158-111">Principal</span><span class="sxs-lookup"><span data-stu-id="5f158-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="5f158-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="5f158-112">**CallType**</span></span> <br/> |<span data-ttu-id="5f158-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="5f158-113">nvarchar</span></span>  <br/> || <span data-ttu-id="5f158-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="5f158-114">Allowed values:</span></span> <br/>  <span data-ttu-id="5f158-115">0--inconnu</span><span class="sxs-lookup"><span data-stu-id="5f158-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="5f158-116">1 - la messagerie instantanée de</span><span class="sxs-lookup"><span data-stu-id="5f158-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="5f158-117">2 : Partage d’application</span><span class="sxs-lookup"><span data-stu-id="5f158-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="5f158-118">3--audio</span><span class="sxs-lookup"><span data-stu-id="5f158-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="5f158-119">4 - audio et vidéo</span><span class="sxs-lookup"><span data-stu-id="5f158-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="5f158-120">5 - transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="5f158-120">5 - File Transfer</span></span> <br/> |
   

