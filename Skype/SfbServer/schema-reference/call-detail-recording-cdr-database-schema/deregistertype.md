---
title: Table DeRegisterType dans Skype entreprise Server 2015
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La table DeRegisterType est une table statique qui stocke la liste de types de déregistreurs d’utilisateurs possibles, par exemple « client lancé », « inscription expirée » ou « le client a cessé de répondre ».
ms.openlocfilehash: ae9afafe91336b1e5c74fd0a854e2975a3b4ba8e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815292"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e9cb7-103">Table DeRegisterType dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="e9cb7-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e9cb7-104">La table DeRegisterType est une table statique qui stocke la liste de types de déregistreurs d’utilisateurs possibles, par exemple « client lancé », « inscription expirée » ou « le client a cessé de répondre ».</span><span class="sxs-lookup"><span data-stu-id="e9cb7-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="e9cb7-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e9cb7-105">**Column**</span></span>|<span data-ttu-id="e9cb7-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e9cb7-106">**Data Type**</span></span>|<span data-ttu-id="e9cb7-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="e9cb7-107">**Key/Index**</span></span>|<span data-ttu-id="e9cb7-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e9cb7-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e9cb7-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="e9cb7-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="e9cb7-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="e9cb7-110">tinyint</span></span>  <br/> |<span data-ttu-id="e9cb7-111">Principal</span><span class="sxs-lookup"><span data-stu-id="e9cb7-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="e9cb7-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="e9cb7-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="e9cb7-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e9cb7-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="e9cb7-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="e9cb7-114">Allowed values:</span></span> <br/>  <span data-ttu-id="e9cb7-115">0--Inconnu</span><span class="sxs-lookup"><span data-stu-id="e9cb7-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="e9cb7-116">1--le client a démarré la suppression</span><span class="sxs-lookup"><span data-stu-id="e9cb7-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="e9cb7-117">2--inscription expirée</span><span class="sxs-lookup"><span data-stu-id="e9cb7-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="e9cb7-118">3-client bloqué</span><span class="sxs-lookup"><span data-stu-id="e9cb7-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="e9cb7-119">4--attributs utilisateur modifiés</span><span class="sxs-lookup"><span data-stu-id="e9cb7-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="e9cb7-120">5-Bureau d’enregistrement préféré modifié</span><span class="sxs-lookup"><span data-stu-id="e9cb7-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="e9cb7-121">6--client hérité en mode de survie</span><span class="sxs-lookup"><span data-stu-id="e9cb7-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

