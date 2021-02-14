---
title: Table Locations dans Skype Entreprise Server 2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Chaque enregistrement représente une référence d’emplacement dans un appel d’urgence, par exemple un appel E9-1-1.
ms.openlocfilehash: b177e79217f8586d7655b2a4645a603bd8e2f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821514"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="00130-103">Table Locations dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="00130-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="00130-104">Chaque enregistrement représente une référence d’emplacement dans un appel d’urgence, par exemple un appel E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="00130-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="00130-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="00130-105">**Column**</span></span>|<span data-ttu-id="00130-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="00130-106">**Data Type**</span></span>|<span data-ttu-id="00130-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="00130-107">**Key/Index**</span></span>|<span data-ttu-id="00130-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="00130-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="00130-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="00130-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="00130-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="00130-110">datetime</span></span>  <br/> |<span data-ttu-id="00130-111">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="00130-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="00130-112">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="00130-112">Time of session request.</span></span> <span data-ttu-id="00130-113">Utilisée conjointement avec **SessionIdSeq** pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="00130-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="00130-114">Pour plus d’informations, voir le tableau Dialogs dans Skype Entreprise [Server 2015.](dialogs.md)</span><span class="sxs-lookup"><span data-stu-id="00130-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="00130-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="00130-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="00130-116">int</span><span class="sxs-lookup"><span data-stu-id="00130-116">int</span></span>  <br/> |<span data-ttu-id="00130-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="00130-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="00130-118">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="00130-118">ID number to identify the session.</span></span> <span data-ttu-id="00130-119">Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="00130-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="00130-120">Pour plus d’informations, voir le tableau Dialogs dans Skype Entreprise [Server 2015.](dialogs.md)</span><span class="sxs-lookup"><span data-stu-id="00130-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="00130-121">**Emplacement**</span><span class="sxs-lookup"><span data-stu-id="00130-121">**Location**</span></span> <br/> |<span data-ttu-id="00130-122">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="00130-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="00130-123">Emplacement de l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="00130-123">Location of emergency call.</span></span>  <br/> |
   

