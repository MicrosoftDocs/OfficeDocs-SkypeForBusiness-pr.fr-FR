---
title: Switch-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: L’applet de commande commutateur-CcVersion déconnecte l’application en cours d’exécution et bascule vers un appareil nouvellement déployé ou de sauvegarde.
ms.openlocfilehash: 73ae9b4f93a2488dea29f3271565ac3d25759fd1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872858"
---
# <a name="switch-ccversion"></a><span data-ttu-id="8382c-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="8382c-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="8382c-104">L’applet de commande commutateur-CcVersion déconnecte l’application en cours d’exécution et bascule vers un appareil nouvellement déployé ou de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8382c-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="8382c-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="8382c-105">Examples</span></span>
<span data-ttu-id="8382c-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8382c-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="8382c-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="8382c-107">Example 1</span></span>

<span data-ttu-id="8382c-108">L’exemple suivant draine les services de l’application en cours d’exécution en cours, puis bascule vers un appareil nouvellement déployé ou de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="8382c-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="8382c-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="8382c-109">Example 2</span></span>

<span data-ttu-id="8382c-110">L’exemple suivant draine les services de l’application en cours d’exécution en cours et arrête les services force en cas d’échec de drainage les services.</span><span class="sxs-lookup"><span data-stu-id="8382c-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="8382c-111">La commande bascule alors vers un appareil nouvellement déployé ou de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="8382c-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="8382c-112">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="8382c-112">Detailed Description</span></span>
<span data-ttu-id="8382c-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8382c-113"></span></span>

<span data-ttu-id="8382c-114">L’applet de commande commutateur-CcVersion draine les services de nuage connecteur sur le serveur de médiation et le serveur de périphérie.</span><span class="sxs-lookup"><span data-stu-id="8382c-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="8382c-115">Tous les appels en cours d’exécution seront effectuées, mais rejette les nouveaux appels.</span><span class="sxs-lookup"><span data-stu-id="8382c-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="8382c-116">Après l’écoulement, l’applet de commande déconnecte l’application en cours d’exécution de l’entreprise et les réseaux Internet, désactive tous les ordinateurs virtuels appartenant à l’application et connecte ensuite l’équipement de sauvegarde à l’entreprise et les réseaux Internet.</span><span class="sxs-lookup"><span data-stu-id="8382c-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="8382c-117">Paramètres</span><span class="sxs-lookup"><span data-stu-id="8382c-117">Parameters</span></span>
<span data-ttu-id="8382c-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8382c-118"></span></span>

|<span data-ttu-id="8382c-119">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="8382c-119">**Parameter**</span></span>|<span data-ttu-id="8382c-120">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="8382c-120">**Required**</span></span>|<span data-ttu-id="8382c-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="8382c-121">**Type**</span></span>|<span data-ttu-id="8382c-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="8382c-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8382c-123">Force</span><span class="sxs-lookup"><span data-stu-id="8382c-123">Force</span></span> <br/> | <span data-ttu-id="8382c-124">Facultatif</span><span class="sxs-lookup"><span data-stu-id="8382c-124">Optional</span></span> <br/> |<span data-ttu-id="8382c-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="8382c-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="8382c-126">Arrête les services force si les services de drainage échoue.</span><span class="sxs-lookup"><span data-stu-id="8382c-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="8382c-127">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="8382c-127">Input Types</span></span>
<span data-ttu-id="8382c-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8382c-128"></span></span>

<span data-ttu-id="8382c-129">Aucun</span><span class="sxs-lookup"><span data-stu-id="8382c-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8382c-130">Types de retours</span><span class="sxs-lookup"><span data-stu-id="8382c-130">Return Types</span></span>
<span data-ttu-id="8382c-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8382c-131"></span></span>

<span data-ttu-id="8382c-132">Aucune</span><span class="sxs-lookup"><span data-stu-id="8382c-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8382c-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8382c-133">See also</span></span>
<span data-ttu-id="8382c-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8382c-134"></span></span>

<span data-ttu-id="8382c-135">Aucun</span><span class="sxs-lookup"><span data-stu-id="8382c-135">None</span></span>
  

