---
title: Table DeRegisterType dans Skype Entreprise Server 2015
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La table DeRegisterType est une table statique qui stocke la liste des types d’utilisateurs dé-inscrits possibles, tels que « initié par le client » ou « l’inscription a expiré » ou « le client a cessé de répondre ».
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816074"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e50b7-103">Table DeRegisterType dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="e50b7-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e50b7-104">La table DeRegisterType est une table statique qui stocke la liste des types d’utilisateurs dé-inscrits possibles, tels que « initié par le client » ou « l’inscription a expiré » ou « le client a cessé de répondre ».</span><span class="sxs-lookup"><span data-stu-id="e50b7-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="e50b7-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e50b7-105">**Column**</span></span>|<span data-ttu-id="e50b7-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e50b7-106">**Data Type**</span></span>|<span data-ttu-id="e50b7-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="e50b7-107">**Key/Index**</span></span>|<span data-ttu-id="e50b7-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e50b7-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e50b7-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="e50b7-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="e50b7-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="e50b7-110">tinyint</span></span>  <br/> |<span data-ttu-id="e50b7-111">Primaire</span><span class="sxs-lookup"><span data-stu-id="e50b7-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="e50b7-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="e50b7-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="e50b7-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e50b7-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="e50b7-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="e50b7-114">Allowed values:</span></span> <br/>  <span data-ttu-id="e50b7-115">0 -- Inconnu</span><span class="sxs-lookup"><span data-stu-id="e50b7-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="e50b7-116">1 -- Désinscription à l’initiative du client</span><span class="sxs-lookup"><span data-stu-id="e50b7-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="e50b7-117">2 -- Expiration de l’inscription</span><span class="sxs-lookup"><span data-stu-id="e50b7-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="e50b7-118">3 - Le client s’est crashé</span><span class="sxs-lookup"><span data-stu-id="e50b7-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="e50b7-119">4 -- Modification des attributs de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="e50b7-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="e50b7-120">5 - Bureau d’enregistrement préféré modifié</span><span class="sxs-lookup"><span data-stu-id="e50b7-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="e50b7-121">6 -- Client hérité en mode survie</span><span class="sxs-lookup"><span data-stu-id="e50b7-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

