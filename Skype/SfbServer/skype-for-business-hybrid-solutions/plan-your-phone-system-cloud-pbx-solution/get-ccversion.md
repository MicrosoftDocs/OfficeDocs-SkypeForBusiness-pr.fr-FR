---
title: Get-CcVersion
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Retourne la version de la solution matérielle-logicielle connecteur de nuage. Get-CCVersion est réservée sur l’ordinateur hôte du connecteur de nuage.
ms.openlocfilehash: 8391264603a73e3f594122dcdd2eb62b9ba19978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccversion"></a><span data-ttu-id="702bf-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="702bf-104">Get-CcVersion</span></span>
 
<span data-ttu-id="702bf-105">Retourne la version de la solution matérielle-logicielle connecteur de nuage.</span><span class="sxs-lookup"><span data-stu-id="702bf-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="702bf-106">Get-CCVersion est réservée sur l’ordinateur hôte du connecteur de nuage.</span><span class="sxs-lookup"><span data-stu-id="702bf-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="702bf-107">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="702bf-107">Detailed Description</span></span>

<span data-ttu-id="702bf-108">Retourne la version de la solution matérielle-logicielle de connecteur de nuage reposant sur des scripts PowerShell installés, les fichiers dans le répertoire de la solution matérielle-logicielle et les ordinateurs virtuels déployés sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="702bf-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="702bf-109">Paramètres</span><span class="sxs-lookup"><span data-stu-id="702bf-109">Parameters</span></span>

|<span data-ttu-id="702bf-110">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="702bf-110">**Parameter**</span></span>|<span data-ttu-id="702bf-111">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="702bf-111">**Required**</span></span>|<span data-ttu-id="702bf-112">**Type de**</span><span class="sxs-lookup"><span data-stu-id="702bf-112">**Type**</span></span>|<span data-ttu-id="702bf-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="702bf-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="702bf-114">TypeDeVersion</span><span class="sxs-lookup"><span data-stu-id="702bf-114">VersionType</span></span>  <br/> |<span data-ttu-id="702bf-115">Facultatif</span><span class="sxs-lookup"><span data-stu-id="702bf-115">Optional</span></span>  <br/> |<span data-ttu-id="702bf-116">System.String</span><span class="sxs-lookup"><span data-stu-id="702bf-116">System.String</span></span>  <br/> |<span data-ttu-id="702bf-117">Type de version.</span><span class="sxs-lookup"><span data-stu-id="702bf-117">Type of version.</span></span> <span data-ttu-id="702bf-118">Valeur du paramètre peut être RunningScripts, RunningBits, BackupBits ou tous.</span><span class="sxs-lookup"><span data-stu-id="702bf-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="702bf-119">Valeur par défaut est RunningScripts.</span><span class="sxs-lookup"><span data-stu-id="702bf-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="702bf-120">Exemples</span><span class="sxs-lookup"><span data-stu-id="702bf-120">Examples</span></span>
<span data-ttu-id="702bf-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="702bf-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="702bf-122">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="702bf-122">Example 1</span></span>

<span data-ttu-id="702bf-123">L’exemple suivant montre la version de connecteur de nuage du script en cours d’exécution dans votre console PowerShell ouverte :</span><span class="sxs-lookup"><span data-stu-id="702bf-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="702bf-124">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="702bf-124">Example 2</span></span>

<span data-ttu-id="702bf-125">L’exemple suivant montre la version de connecteur de nuage des binaires déployés sur les ordinateurs virtuels en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="702bf-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="702bf-126">Vous pouvez voir la version dans les noms de machine virtuelle en cours d’exécution dans le Gestionnaire Hyper-v :</span><span class="sxs-lookup"><span data-stu-id="702bf-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="702bf-127">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="702bf-127">Input Types</span></span>
<span data-ttu-id="702bf-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="702bf-128"></span></span>

<span data-ttu-id="702bf-129">Aucun.</span><span class="sxs-lookup"><span data-stu-id="702bf-129">None.</span></span> <span data-ttu-id="702bf-130">L’applet de commande Get-CcVersion n’accepte pas les entrées de pipeline.</span><span class="sxs-lookup"><span data-stu-id="702bf-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="702bf-131">Types de retours</span><span class="sxs-lookup"><span data-stu-id="702bf-131">Return Types</span></span>
<span data-ttu-id="702bf-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="702bf-132"></span></span>

<span data-ttu-id="702bf-133">Aucun.</span><span class="sxs-lookup"><span data-stu-id="702bf-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="702bf-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="702bf-134">See also</span></span>
<span data-ttu-id="702bf-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="702bf-135"></span></span>

<span data-ttu-id="702bf-136">Aucun</span><span class="sxs-lookup"><span data-stu-id="702bf-136">None.</span></span>
  

