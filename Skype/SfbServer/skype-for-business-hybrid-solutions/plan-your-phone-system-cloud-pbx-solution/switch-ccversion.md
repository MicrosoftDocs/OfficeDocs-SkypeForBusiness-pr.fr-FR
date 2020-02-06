---
title: Switch-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: L’applet de commande Switch-CcVersion déconnecte l’application en cours d’exécution et bascule vers une nouvelle appliance déployée ou Backup.
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824148"
---
# <a name="switch-ccversion"></a><span data-ttu-id="fc9ea-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="fc9ea-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="fc9ea-104">L’applet de commande Switch-CcVersion déconnecte l’application en cours d’exécution et bascule vers une nouvelle appliance déployée ou Backup.</span><span class="sxs-lookup"><span data-stu-id="fc9ea-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="fc9ea-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="fc9ea-105">Examples</span></span>
<span data-ttu-id="fc9ea-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fc9ea-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="fc9ea-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="fc9ea-107">Example 1</span></span>

<span data-ttu-id="fc9ea-108">L’exemple suivant drainne les services de l’application en cours d’exécution, puis bascule vers une nouvelle application de déploiement ou de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="fc9ea-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="fc9ea-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="fc9ea-109">Example 2</span></span>

<span data-ttu-id="fc9ea-110">L’exemple suivant drainne les services de l’application en cours d’exécution et arrête les services de force en cas d’échec du drainage des services.</span><span class="sxs-lookup"><span data-stu-id="fc9ea-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="fc9ea-111">La commande bascule alors vers une nouvelle appliance déployée ou de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="fc9ea-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="fc9ea-112">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="fc9ea-112">Detailed Description</span></span>
<span data-ttu-id="fc9ea-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fc9ea-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="fc9ea-114">L’applet de connexion Switch-CcVersion draine les services de connecteur Cloud sur le serveur de médiation et le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="fc9ea-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="fc9ea-115">Tous les appels en cours seront exécutés, mais les nouveaux appels seront rejetés par l’appliance.</span><span class="sxs-lookup"><span data-stu-id="fc9ea-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="fc9ea-116">Après le vidage, l’applet de connexion déconnecte l’application en cours d’exécution des réseaux d’entreprise et Internet, éteint toutes les machines virtuelles appartenant à l’application, puis connecte l’appareil de sauvegarde aux réseaux d’entreprise et Internet.</span><span class="sxs-lookup"><span data-stu-id="fc9ea-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="fc9ea-117">Paramètres</span><span class="sxs-lookup"><span data-stu-id="fc9ea-117">Parameters</span></span>
<span data-ttu-id="fc9ea-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fc9ea-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="fc9ea-119">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="fc9ea-119">**Parameter**</span></span>|<span data-ttu-id="fc9ea-120">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="fc9ea-120">**Required**</span></span>|<span data-ttu-id="fc9ea-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="fc9ea-121">**Type**</span></span>|<span data-ttu-id="fc9ea-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="fc9ea-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="fc9ea-123">Force</span><span class="sxs-lookup"><span data-stu-id="fc9ea-123">Force</span></span> <br/> | <span data-ttu-id="fc9ea-124">Facultatif</span><span class="sxs-lookup"><span data-stu-id="fc9ea-124">Optional</span></span> <br/> |<span data-ttu-id="fc9ea-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="fc9ea-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="fc9ea-126">Arrête les services de force en cas d’échec du drainage des services.</span><span class="sxs-lookup"><span data-stu-id="fc9ea-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="fc9ea-127">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="fc9ea-127">Input Types</span></span>
<span data-ttu-id="fc9ea-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fc9ea-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="fc9ea-129">Aucun</span><span class="sxs-lookup"><span data-stu-id="fc9ea-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="fc9ea-130">Types de retours</span><span class="sxs-lookup"><span data-stu-id="fc9ea-130">Return Types</span></span>
<span data-ttu-id="fc9ea-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fc9ea-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="fc9ea-132">Aucune</span><span class="sxs-lookup"><span data-stu-id="fc9ea-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fc9ea-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fc9ea-133">See also</span></span>
<span data-ttu-id="fc9ea-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fc9ea-134"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="fc9ea-135">Aucun</span><span class="sxs-lookup"><span data-stu-id="fc9ea-135">None</span></span>
  

