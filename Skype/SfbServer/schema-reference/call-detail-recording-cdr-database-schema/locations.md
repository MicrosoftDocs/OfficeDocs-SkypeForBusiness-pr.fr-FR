---
title: Table Locations dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Chaque enregistrement représente une référence d’emplacement dans un appel d’urgence, comme un appel E9-1-1.
ms.openlocfilehash: 180a094ef10cc54b4fd65a30adb0909789afa3d6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876943"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2fa36-103">Table Locations dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2fa36-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2fa36-104">Chaque enregistrement représente une référence d’emplacement dans un appel d’urgence, comme un appel E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="2fa36-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="2fa36-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2fa36-105">**Column**</span></span>|<span data-ttu-id="2fa36-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="2fa36-106">**Data Type**</span></span>|<span data-ttu-id="2fa36-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="2fa36-107">**Key/Index**</span></span>|<span data-ttu-id="2fa36-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="2fa36-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2fa36-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="2fa36-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="2fa36-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2fa36-110">datetime</span></span>  <br/> |<span data-ttu-id="2fa36-111">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="2fa36-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2fa36-112">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="2fa36-112">Time of session request.</span></span> <span data-ttu-id="2fa36-113">Utilisé en conjonction avec **SessionIdSeq** pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="2fa36-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="2fa36-114">Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="2fa36-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2fa36-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="2fa36-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="2fa36-116">int</span><span class="sxs-lookup"><span data-stu-id="2fa36-116">int</span></span>  <br/> |<span data-ttu-id="2fa36-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="2fa36-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2fa36-118">Numéro d’identification pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="2fa36-118">ID number to identify the session.</span></span> <span data-ttu-id="2fa36-119">Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="2fa36-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="2fa36-120">Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="2fa36-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2fa36-121">**Emplacement**</span><span class="sxs-lookup"><span data-stu-id="2fa36-121">**Location**</span></span> <br/> |<span data-ttu-id="2fa36-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="2fa36-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="2fa36-123">Emplacement de l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="2fa36-123">Location of emergency call.</span></span>  <br/> |
   

