---
title: Table DeRegisterType dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La table DeRegisterType est une table statique qui stocke la liste des utilisateurs enregistre différents types, tels que l’initiative du client, « expiration de l’inscription » ou « client ne répond plus ».
ms.openlocfilehash: 958de5dd537f391ca75936ad86a84cb6fed0778d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901172"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b3535-103">Table DeRegisterType dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b3535-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b3535-104">La table DeRegisterType est une table statique qui stocke la liste des utilisateurs enregistre différents types, tels que l’initiative du client, « expiration de l’inscription » ou « client ne répond plus ».</span><span class="sxs-lookup"><span data-stu-id="b3535-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="b3535-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b3535-105">**Column**</span></span>|<span data-ttu-id="b3535-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="b3535-106">**Data Type**</span></span>|<span data-ttu-id="b3535-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="b3535-107">**Key/Index**</span></span>|<span data-ttu-id="b3535-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="b3535-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b3535-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="b3535-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="b3535-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="b3535-110">tinyint</span></span>  <br/> |<span data-ttu-id="b3535-111">Principal</span><span class="sxs-lookup"><span data-stu-id="b3535-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="b3535-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="b3535-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="b3535-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b3535-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="b3535-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="b3535-114">Allowed values:</span></span> <br/>  <span data-ttu-id="b3535-115">0 : inconnu</span><span class="sxs-lookup"><span data-stu-id="b3535-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="b3535-116">1--initiative du client désinscription</span><span class="sxs-lookup"><span data-stu-id="b3535-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="b3535-117">2--expiration de l’inscription</span><span class="sxs-lookup"><span data-stu-id="b3535-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="b3535-118">3 - client bloqué</span><span class="sxs-lookup"><span data-stu-id="b3535-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="b3535-119">4--modifié des attributs utilisateur</span><span class="sxs-lookup"><span data-stu-id="b3535-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="b3535-120">5 - serveurs d’inscriptions par défaut modifié</span><span class="sxs-lookup"><span data-stu-id="b3535-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="b3535-121">6--De Client hérité en Mode survie</span><span class="sxs-lookup"><span data-stu-id="b3535-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

