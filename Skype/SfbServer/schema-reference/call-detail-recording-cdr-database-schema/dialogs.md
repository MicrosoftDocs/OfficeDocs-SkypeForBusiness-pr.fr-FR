---
title: Tableau boîtes de dialogue dans Skype entreprise Server 2015
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Le tableau boîtes de dialogue est une table de prise en charge qui contient les informations sur DialogIDs pour les sessions d’égal à égal.
ms.openlocfilehash: f6cfc3e078ee8f4492d6f5baf65f66df77d7aedf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815272"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="16b1e-103">Tableau boîtes de dialogue dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="16b1e-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="16b1e-104">Le tableau boîtes de dialogue est une table de prise en charge qui contient les informations sur DialogIDs pour les sessions d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="16b1e-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="16b1e-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="16b1e-105">**Column**</span></span>|<span data-ttu-id="16b1e-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="16b1e-106">**Data Type**</span></span>|<span data-ttu-id="16b1e-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="16b1e-107">**Key/Index**</span></span>|<span data-ttu-id="16b1e-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="16b1e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="16b1e-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="16b1e-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="16b1e-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="16b1e-110">datetime</span></span>  <br/> |<span data-ttu-id="16b1e-111">Principal</span><span class="sxs-lookup"><span data-stu-id="16b1e-111">Primary</span></span>  <br/> |<span data-ttu-id="16b1e-112">Durée de la demande de session ; utilisé conjointement avec SessionIDSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="16b1e-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="16b1e-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="16b1e-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="16b1e-114">int</span><span class="sxs-lookup"><span data-stu-id="16b1e-114">int</span></span>  <br/> |<span data-ttu-id="16b1e-115">Principal</span><span class="sxs-lookup"><span data-stu-id="16b1e-115">Primary</span></span>  <br/> |<span data-ttu-id="16b1e-116">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="16b1e-116">ID number to identify the session.</span></span> <span data-ttu-id="16b1e-117">Utilisé conjointement avec SessionIDTime pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="16b1e-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="16b1e-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="16b1e-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="16b1e-119">int</span><span class="sxs-lookup"><span data-stu-id="16b1e-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="16b1e-120">Checksum du ExternalID.</span><span class="sxs-lookup"><span data-stu-id="16b1e-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="16b1e-121">Ce champ est utilisé pour augmenter la vitesse de recherche de la base de données.</span><span class="sxs-lookup"><span data-stu-id="16b1e-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="16b1e-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="16b1e-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="16b1e-123">varbinary (LGA775)</span><span class="sxs-lookup"><span data-stu-id="16b1e-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="16b1e-124">ID de boîte de dialogue SIP, enregistré en tant que fichier binaire.</span><span class="sxs-lookup"><span data-stu-id="16b1e-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="16b1e-125">Le format du binaire est le suivant :</span><span class="sxs-lookup"><span data-stu-id="16b1e-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="16b1e-126">boîte de dialogue ; à partir d’une balise</span><span class="sxs-lookup"><span data-stu-id="16b1e-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="16b1e-127">Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="16b1e-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

