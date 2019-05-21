---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: L’applet de commande Stop-CcLogging interrompt la création de journaux d'appels entrants et sortants pour une appliance de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: dcc62e8ec772912a8275f5321a6c91e28dde8c25
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286935"
---
# <a name="stop-cclogging"></a><span data-ttu-id="10f35-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="10f35-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="10f35-104">L’applet de commande Stop-CcLogging interrompt la création de journaux d'appels entrants et sortants pour une appliance de la version Cloud Connector de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="10f35-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="10f35-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="10f35-105">Examples</span></span>
<span data-ttu-id="10f35-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="10f35-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="10f35-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="10f35-107">Example 1</span></span>

<span data-ttu-id="10f35-108">L’exemple suivant interrompt la création de journaux d'appels entrants et sortants : </span><span class="sxs-lookup"><span data-stu-id="10f35-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="10f35-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="10f35-109">Example 2</span></span>

<span data-ttu-id="10f35-110">L’exemple suivant interrompt la création de journaux d'appels entrants et sortants et nettoie les fichiers en mémoire :</span><span class="sxs-lookup"><span data-stu-id="10f35-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="10f35-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="10f35-111">Detailed Description</span></span>
<span data-ttu-id="10f35-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="10f35-112"></span></span>

<span data-ttu-id="10f35-113">L’applet de commande Stop-CcLogging interrompt la création de journaux d'appels entrants et sortants sur une appliance.</span><span class="sxs-lookup"><span data-stu-id="10f35-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="10f35-114">Par défaut, les journaux sont automatiquement interrompus après quatre heures.</span><span class="sxs-lookup"><span data-stu-id="10f35-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="10f35-115">Paramètres</span><span class="sxs-lookup"><span data-stu-id="10f35-115">Parameters</span></span>
<span data-ttu-id="10f35-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="10f35-116"></span></span>

|<span data-ttu-id="10f35-117">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="10f35-117">**Parameter**</span></span>|<span data-ttu-id="10f35-118">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="10f35-118">**Required**</span></span>|<span data-ttu-id="10f35-119">**Type**</span><span class="sxs-lookup"><span data-stu-id="10f35-119">**Type**</span></span>|<span data-ttu-id="10f35-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="10f35-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="10f35-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="10f35-121">RemoveCache</span></span> <br/> | <span data-ttu-id="10f35-122">Facultatif</span><span class="sxs-lookup"><span data-stu-id="10f35-122">Optional</span></span> <br/> | <span data-ttu-id="10f35-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="10f35-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="10f35-124">Suppression des fichiers de journaux en mémoire.</span><span class="sxs-lookup"><span data-stu-id="10f35-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="10f35-125">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="10f35-125">Input Types</span></span>
<span data-ttu-id="10f35-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="10f35-126"></span></span>

<span data-ttu-id="10f35-p102">Aucun. L’applet de commande Stop-CcLogging n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="10f35-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="10f35-129">Types de retours</span><span class="sxs-lookup"><span data-stu-id="10f35-129">Return Types</span></span>
<span data-ttu-id="10f35-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="10f35-130"></span></span>

<span data-ttu-id="10f35-131">Aucun</span><span class="sxs-lookup"><span data-stu-id="10f35-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="10f35-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10f35-132">See also</span></span>
<span data-ttu-id="10f35-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="10f35-133"></span></span>

[<span data-ttu-id="10f35-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="10f35-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="10f35-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="10f35-135">Start-CcLogging</span></span>](start-cclogging.md)
  

