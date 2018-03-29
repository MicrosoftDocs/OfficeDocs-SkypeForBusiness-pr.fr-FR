---
title: Table de boîtes de dialogue dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La table de boîtes de dialogue est une table de support qui stocke les informations sur les DialogIDs pour les sessions de peer-to-peer.
ms.openlocfilehash: b2953ff2bec35575221bc0d43785eb6c0d90e2d1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="dee01-103">Table de boîtes de dialogue dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dee01-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dee01-104">La table de boîtes de dialogue est une table de support qui stocke les informations sur les DialogIDs pour les sessions de peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="dee01-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="dee01-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="dee01-105">**Column**</span></span>|<span data-ttu-id="dee01-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="dee01-106">**Data Type**</span></span>|<span data-ttu-id="dee01-107">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="dee01-107">**Key/Index**</span></span>|<span data-ttu-id="dee01-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="dee01-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dee01-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="dee01-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="dee01-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="dee01-110">datetime</span></span>  <br/> |<span data-ttu-id="dee01-111">Principal</span><span class="sxs-lookup"><span data-stu-id="dee01-111">Primary</span></span>  <br/> |<span data-ttu-id="dee01-112">Heure de la demande de la session ; utilisé en association avec SessionIDSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="dee01-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="dee01-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="dee01-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="dee01-114">int</span><span class="sxs-lookup"><span data-stu-id="dee01-114">int</span></span>  <br/> |<span data-ttu-id="dee01-115">Principal</span><span class="sxs-lookup"><span data-stu-id="dee01-115">Primary</span></span>  <br/> |<span data-ttu-id="dee01-116">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="dee01-116">ID number to identify the session.</span></span> <span data-ttu-id="dee01-117">Utilisé en association avec SessionIDTime pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="dee01-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="dee01-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="dee01-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="dee01-119">int</span><span class="sxs-lookup"><span data-stu-id="dee01-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="dee01-120">Total de contrôle de la ExternalID.</span><span class="sxs-lookup"><span data-stu-id="dee01-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="dee01-121">Ce champ est utilisé pour augmenter la vitesse des recherches de base de données.</span><span class="sxs-lookup"><span data-stu-id="dee01-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="dee01-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="dee01-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="dee01-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="dee01-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="dee01-124">ID de boîte de dialogue SIP, stockée sous la forme d’un fichier binaire.</span><span class="sxs-lookup"><span data-stu-id="dee01-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="dee01-125">Le format de fichier binaire est :</span><span class="sxs-lookup"><span data-stu-id="dee01-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="dee01-126">boîte de dialogue, à partir de balise ; de balise</span><span class="sxs-lookup"><span data-stu-id="dee01-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="dee01-127">Ces données peuvent être converties au format de texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="dee01-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

