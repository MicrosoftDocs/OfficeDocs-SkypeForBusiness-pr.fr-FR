---
title: Commutateur-CcVersion
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: L’applet de commande du commutateur-CcVersion déconnecte de la solution matérielle-logicielle en cours d’exécution et bascule vers une solution matérielle-logicielle qui vient d’être déployé ou de sauvegarde.
ms.openlocfilehash: 651dad80ef5c9907eb6c182527b646da7aa5acc8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="switch-ccversion"></a><span data-ttu-id="51f5a-103">Commutateur-CcVersion</span><span class="sxs-lookup"><span data-stu-id="51f5a-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="51f5a-104">L’applet de commande du commutateur-CcVersion déconnecte de la solution matérielle-logicielle en cours d’exécution et bascule vers une solution matérielle-logicielle qui vient d’être déployé ou de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="51f5a-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="51f5a-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="51f5a-105">Examples</span></span>
<span data-ttu-id="51f5a-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="51f5a-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="51f5a-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="51f5a-107">Example 1</span></span>

<span data-ttu-id="51f5a-108">L’exemple suivant draine les services de l’application en cours d’exécution en cours, puis passe à un matériel nouvellement déployé ou de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="51f5a-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="51f5a-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="51f5a-109">Example 2</span></span>

<span data-ttu-id="51f5a-110">L’exemple suivant draine les services de l’application en cours d’exécution en cours et arrête les services force si les services de drainage échoue.</span><span class="sxs-lookup"><span data-stu-id="51f5a-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="51f5a-111">La commande passe ensuite à une solution matérielle-logicielle qui vient d’être déployé ou de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="51f5a-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="51f5a-112">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="51f5a-112">Detailed Description</span></span>
<span data-ttu-id="51f5a-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="51f5a-113"></span></span>

<span data-ttu-id="51f5a-114">L’applet de commande du commutateur-CcVersion draine les services Cloud connecteur sur le serveur de médiation et d’un serveur de transport Edge.</span><span class="sxs-lookup"><span data-stu-id="51f5a-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="51f5a-115">Tous les appels en cours d’exécution seront effectuées, mais la solution matérielle-logicielle rejette tous les appels de nouveau.</span><span class="sxs-lookup"><span data-stu-id="51f5a-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="51f5a-116">Après l’écoulement, l’applet de commande déconnecte de la solution matérielle-logicielle en cours d’exécution à partir de l’entreprise et les réseaux Internet, désactive tous les ordinateurs virtuels appartenant à la solution matérielle-logicielle et connecte ensuite l’équipement de sauvegarde à l’entreprise et les réseaux Internet.</span><span class="sxs-lookup"><span data-stu-id="51f5a-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="51f5a-117">Paramètres</span><span class="sxs-lookup"><span data-stu-id="51f5a-117">Parameters</span></span>
<span data-ttu-id="51f5a-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="51f5a-118"></span></span>

|<span data-ttu-id="51f5a-119">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="51f5a-119">**Parameter**</span></span>|<span data-ttu-id="51f5a-120">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="51f5a-120">**Required**</span></span>|<span data-ttu-id="51f5a-121">**Type de**</span><span class="sxs-lookup"><span data-stu-id="51f5a-121">**Type**</span></span>|<span data-ttu-id="51f5a-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="51f5a-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="51f5a-123">Force</span><span class="sxs-lookup"><span data-stu-id="51f5a-123">Force</span></span> <br/> | <span data-ttu-id="51f5a-124">Facultatif</span><span class="sxs-lookup"><span data-stu-id="51f5a-124">Optional</span></span> <br/> |<span data-ttu-id="51f5a-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="51f5a-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="51f5a-126">Arrête les services force si les services de drainage échoue.</span><span class="sxs-lookup"><span data-stu-id="51f5a-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="51f5a-127">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="51f5a-127">Input Types</span></span>
<span data-ttu-id="51f5a-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="51f5a-128"></span></span>

<span data-ttu-id="51f5a-129">Aucune</span><span class="sxs-lookup"><span data-stu-id="51f5a-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="51f5a-130">Types de retours</span><span class="sxs-lookup"><span data-stu-id="51f5a-130">Return Types</span></span>
<span data-ttu-id="51f5a-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="51f5a-131"></span></span>

<span data-ttu-id="51f5a-132">Aucun</span><span class="sxs-lookup"><span data-stu-id="51f5a-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="51f5a-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="51f5a-133">See also</span></span>
<span data-ttu-id="51f5a-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="51f5a-134"></span></span>

<span data-ttu-id="51f5a-135">Aucun</span><span class="sxs-lookup"><span data-stu-id="51f5a-135">None</span></span>
  

