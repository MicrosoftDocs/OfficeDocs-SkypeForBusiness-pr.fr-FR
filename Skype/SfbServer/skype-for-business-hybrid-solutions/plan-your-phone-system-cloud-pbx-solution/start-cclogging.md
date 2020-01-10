---
title: Start-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 01b62253-2aaf-43ed-9d63-804e31edc522
description: "L’applet de commande Start-CcLogging crée le journal d'appels entrants et sortants pour une appliance de la version Cloud Connector de Skype Entreprise. "
ms.openlocfilehash: 2064fa4efd730812b5073821784ff5c524056341
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003174"
---
# <a name="start-cclogging"></a><span data-ttu-id="6867a-103">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="6867a-103">Start-CcLogging</span></span>
 
<span data-ttu-id="6867a-104">L’applet de commande Start-CcLogging crée le journal d'appels entrants et sortants pour une appliance de la version Cloud Connector de Skype Entreprise. </span><span class="sxs-lookup"><span data-stu-id="6867a-104">The Start-CcLogging cmdlet generates the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span> 
  
```powershell
Start-CcLogging
```

## <a name="parameters"></a><span data-ttu-id="6867a-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="6867a-105">Parameters</span></span>

<span data-ttu-id="6867a-106">Aucun</span><span class="sxs-lookup"><span data-stu-id="6867a-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="6867a-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="6867a-107">Examples</span></span>
<span data-ttu-id="6867a-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6867a-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="6867a-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="6867a-109">Example 1</span></span>

<span data-ttu-id="6867a-110">L'exemple suivant créé le journal d'appels entrants et sortants :</span><span class="sxs-lookup"><span data-stu-id="6867a-110">The following example generates the incoming and outgoing call log:</span></span>
  
```powershell
Start-CcLogging
```

## <a name="detailed-description"></a><span data-ttu-id="6867a-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="6867a-111">Detailed Description</span></span>
<span data-ttu-id="6867a-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6867a-112"></span></span>

<span data-ttu-id="6867a-113">L’applet de connexion Start-CcLogging permet aux administrateurs de commencer à enregistrer les appels entrants et sortants sur un appareil de connecteur Cloud.</span><span class="sxs-lookup"><span data-stu-id="6867a-113">The Start-CcLogging cmdlet provides a way for administrators to begin logging incoming and outgoing calls on a Cloud Connector appliance.</span></span> <span data-ttu-id="6867a-114">Par défaut, le journal est automatiquement interrompu après quatre heures.</span><span class="sxs-lookup"><span data-stu-id="6867a-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="6867a-115">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="6867a-115">Input Types</span></span>
<span data-ttu-id="6867a-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6867a-116"></span></span>

<span data-ttu-id="6867a-p102">Aucun. L’applet de commande Start-CcLogging n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="6867a-p102">None. The Start-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6867a-119">Types de retours</span><span class="sxs-lookup"><span data-stu-id="6867a-119">Return Types</span></span>
<span data-ttu-id="6867a-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6867a-120"></span></span>

<span data-ttu-id="6867a-121">Aucun</span><span class="sxs-lookup"><span data-stu-id="6867a-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6867a-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6867a-122">See also</span></span>
<span data-ttu-id="6867a-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6867a-123"></span></span>

[<span data-ttu-id="6867a-124">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="6867a-124">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="6867a-125">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="6867a-125">Stop-CcLogging</span></span>](stop-cclogging.md)
  

