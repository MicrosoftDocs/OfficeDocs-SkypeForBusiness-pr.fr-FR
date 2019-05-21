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
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La table DeRegisterType est une table statique qui stocke la liste de types de déregistreurs d’utilisateurs possibles, par exemple «client lancé», «inscription expirée» ou «le client a cessé de répondre».
ms.openlocfilehash: 794f8f98ffe20cd69b63fd2084fee38ed055d40f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296349"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e9877-103">Table DeRegisterType dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="e9877-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e9877-104">La table DeRegisterType est une table statique qui stocke la liste de types de déregistreurs d’utilisateurs possibles, par exemple «client lancé», «inscription expirée» ou «le client a cessé de répondre».</span><span class="sxs-lookup"><span data-stu-id="e9877-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="e9877-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e9877-105">**Column**</span></span>|<span data-ttu-id="e9877-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e9877-106">**Data Type**</span></span>|<span data-ttu-id="e9877-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="e9877-107">**Key/Index**</span></span>|<span data-ttu-id="e9877-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e9877-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e9877-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="e9877-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="e9877-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="e9877-110">tinyint</span></span>  <br/> |<span data-ttu-id="e9877-111">Principal</span><span class="sxs-lookup"><span data-stu-id="e9877-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="e9877-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="e9877-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="e9877-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e9877-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="e9877-114">Valeurs autorisées:</span><span class="sxs-lookup"><span data-stu-id="e9877-114">Allowed values:</span></span> <br/>  <span data-ttu-id="e9877-115">0--Inconnu</span><span class="sxs-lookup"><span data-stu-id="e9877-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="e9877-116">1--le client a démarré la suppression</span><span class="sxs-lookup"><span data-stu-id="e9877-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="e9877-117">2--inscription expirée</span><span class="sxs-lookup"><span data-stu-id="e9877-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="e9877-118">3-client bloqué</span><span class="sxs-lookup"><span data-stu-id="e9877-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="e9877-119">4--attributs utilisateur modifiés</span><span class="sxs-lookup"><span data-stu-id="e9877-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="e9877-120">5-Bureau d’enregistrement préféré modifié</span><span class="sxs-lookup"><span data-stu-id="e9877-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="e9877-121">6--client hérité en mode de survie</span><span class="sxs-lookup"><span data-stu-id="e9877-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

