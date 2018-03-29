---
title: Table DeRegisterType dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La table DeRegisterType est une table statique qui stocke la liste des utilisateurs possible enregistre des types, tels que « client ouverte », « inscription expiré » ou 'client a cessé de répondre.'
ms.openlocfilehash: 97b342a8d0175da0517aa36e0fea477e32df4dd9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="f2014-103">Table DeRegisterType dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f2014-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f2014-104">La table DeRegisterType est une table statique qui stocke la liste des utilisateurs possible enregistre des types, tels que « client ouverte », « inscription expiré » ou 'client a cessé de répondre.'</span><span class="sxs-lookup"><span data-stu-id="f2014-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="f2014-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f2014-105">**Column**</span></span>|<span data-ttu-id="f2014-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="f2014-106">**Data Type**</span></span>|<span data-ttu-id="f2014-107">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="f2014-107">**Key/Index**</span></span>|<span data-ttu-id="f2014-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="f2014-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f2014-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="f2014-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="f2014-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="f2014-110">tinyint</span></span>  <br/> |<span data-ttu-id="f2014-111">Principal</span><span class="sxs-lookup"><span data-stu-id="f2014-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="f2014-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="f2014-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="f2014-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f2014-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="f2014-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="f2014-114">Allowed values:</span></span> <br/>  <span data-ttu-id="f2014-115">0--inconnu</span><span class="sxs-lookup"><span data-stu-id="f2014-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="f2014-116">1--annulation d’enregistrement initié par le client</span><span class="sxs-lookup"><span data-stu-id="f2014-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="f2014-117">2 – l’enregistrement a expiré.</span><span class="sxs-lookup"><span data-stu-id="f2014-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="f2014-118">3 - le client est tombé en panne</span><span class="sxs-lookup"><span data-stu-id="f2014-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="f2014-119">4--les attributs utilisateur modifiés</span><span class="sxs-lookup"><span data-stu-id="f2014-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="f2014-120">5 - Registrar par défaut modifié</span><span class="sxs-lookup"><span data-stu-id="f2014-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="f2014-121">6--Client hérité mode de survie</span><span class="sxs-lookup"><span data-stu-id="f2014-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

