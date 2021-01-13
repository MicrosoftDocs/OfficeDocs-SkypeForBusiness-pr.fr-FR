---
title: Vue FileTransfers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: L’affichage FileTransfer stocke des informations sur les sessions de transfert de fichiers d’égal à égal. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 8b3c2db012b8969bd4b5b75ca19ed090f8227c53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821684"
---
# <a name="filetransfers-view"></a><span data-ttu-id="a09aa-104">Vue FileTransfers</span><span class="sxs-lookup"><span data-stu-id="a09aa-104">FileTransfers view</span></span>
 
<span data-ttu-id="a09aa-105">L’affichage FileTransfer stocke des informations sur les sessions de transfert de fichiers d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="a09aa-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="a09aa-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a09aa-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a09aa-107">L’affichage FileTransfers contient toutes les colonnes de l’affichage [SessionDetails](sessiondetails-0.md) en plus des colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a09aa-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="a09aa-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a09aa-108">**Column**</span></span>|<span data-ttu-id="a09aa-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="a09aa-109">**Data Type**</span></span>|<span data-ttu-id="a09aa-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="a09aa-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a09aa-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="a09aa-111">**FileName**</span></span> <br/> |<span data-ttu-id="a09aa-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a09aa-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a09aa-113">Nom du fichier transféré.</span><span class="sxs-lookup"><span data-stu-id="a09aa-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="a09aa-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="a09aa-114">**Cookie**</span></span> <br/> |<span data-ttu-id="a09aa-115">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="a09aa-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="a09aa-116">Utilisé pour identifier chaque message de suivi comme étant associé à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="a09aa-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="a09aa-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="a09aa-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="a09aa-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a09aa-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="a09aa-119">Identificateur unique permettant de différencier les transferts de fichiers concernant le même nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="a09aa-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="a09aa-120">**Accept**</span><span class="sxs-lookup"><span data-stu-id="a09aa-120">**Accept**</span></span> <br/> |<span data-ttu-id="a09aa-121">bit</span><span class="sxs-lookup"><span data-stu-id="a09aa-121">bit</span></span>  <br/> |<span data-ttu-id="a09aa-p103">Peut-être TRUE ou NULL. Si TRUE, alors Reject et Cancel seront NULL.</span><span class="sxs-lookup"><span data-stu-id="a09aa-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="a09aa-124">**Rejeter**</span><span class="sxs-lookup"><span data-stu-id="a09aa-124">**Reject**</span></span> <br/> |<span data-ttu-id="a09aa-125">bit</span><span class="sxs-lookup"><span data-stu-id="a09aa-125">bit</span></span>  <br/> |<span data-ttu-id="a09aa-p104">Peut-être TRUE ou NULL. Si TRUE, alors Accept et Cancel seront NULL.</span><span class="sxs-lookup"><span data-stu-id="a09aa-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="a09aa-128">**Cancel**</span><span class="sxs-lookup"><span data-stu-id="a09aa-128">**Cancel**</span></span> <br/> |<span data-ttu-id="a09aa-129">bit</span><span class="sxs-lookup"><span data-stu-id="a09aa-129">bit</span></span>  <br/> |<span data-ttu-id="a09aa-p105">Peut-être TRUE ou NULL. Si TRUE, alors Accept et Reject seront NULL.</span><span class="sxs-lookup"><span data-stu-id="a09aa-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

