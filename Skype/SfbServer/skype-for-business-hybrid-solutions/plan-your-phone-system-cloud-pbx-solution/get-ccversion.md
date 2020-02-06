---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Renvoie la version de l’application Cloud Connector. Get-CCVersion ne peut être utilisé que sur l’ordinateur hôte de Cloud Connector.
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799844"
---
# <a name="get-ccversion"></a><span data-ttu-id="77167-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="77167-104">Get-CcVersion</span></span>
 
<span data-ttu-id="77167-105">Renvoie la version de l’application Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="77167-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="77167-106">Get-CCVersion ne peut être utilisé que sur l’ordinateur hôte de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="77167-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="77167-107">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="77167-107">Detailed Description</span></span>

<span data-ttu-id="77167-108">Retourne la version de l’application Cloud Connector basée sur les scripts PowerShell installés, des fichiers dans l’annuaire de l’application et des machines virtuelles déployées sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="77167-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="77167-109">Paramètres</span><span class="sxs-lookup"><span data-stu-id="77167-109">Parameters</span></span>

|<span data-ttu-id="77167-110">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="77167-110">**Parameter**</span></span>|<span data-ttu-id="77167-111">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="77167-111">**Required**</span></span>|<span data-ttu-id="77167-112">**Type**</span><span class="sxs-lookup"><span data-stu-id="77167-112">**Type**</span></span>|<span data-ttu-id="77167-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="77167-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="77167-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="77167-114">VersionType</span></span>  <br/> |<span data-ttu-id="77167-115">Facultatif</span><span class="sxs-lookup"><span data-stu-id="77167-115">Optional</span></span>  <br/> |<span data-ttu-id="77167-116">System.String</span><span class="sxs-lookup"><span data-stu-id="77167-116">System.String</span></span>  <br/> |<span data-ttu-id="77167-117">Type de version.</span><span class="sxs-lookup"><span data-stu-id="77167-117">Type of version.</span></span> <span data-ttu-id="77167-118">La valeur du paramètre peut être RunningScripts, RunningBits, BackupBits ou All.</span><span class="sxs-lookup"><span data-stu-id="77167-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="77167-119">La valeur par défaut est RunningScripts.</span><span class="sxs-lookup"><span data-stu-id="77167-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="77167-120">Exemples</span><span class="sxs-lookup"><span data-stu-id="77167-120">Examples</span></span>
<span data-ttu-id="77167-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="77167-121"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="77167-122">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="77167-122">Example 1</span></span>

<span data-ttu-id="77167-123">L’exemple suivant montre la version Cloud Connector du script en cours d’exécution dans votre console PowerShell ouverte :</span><span class="sxs-lookup"><span data-stu-id="77167-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="77167-124">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="77167-124">Example 2</span></span>

<span data-ttu-id="77167-125">L’exemple suivant montre la version Cloud Connector du binaire en cours d’exécution déployée sur les machines virtuelles.</span><span class="sxs-lookup"><span data-stu-id="77167-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="77167-126">Vous pouvez voir la version dans les noms des machines virtuelles exécutées dans Hyper-v Manager :</span><span class="sxs-lookup"><span data-stu-id="77167-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="77167-127">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="77167-127">Input Types</span></span>
<span data-ttu-id="77167-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="77167-128"><a name="Examples"> </a></span></span>

<span data-ttu-id="77167-129">Aucun.</span><span class="sxs-lookup"><span data-stu-id="77167-129">None.</span></span> <span data-ttu-id="77167-130">L’applet de commande Get-CcVersion n’accepte pas les entrées pipelines.</span><span class="sxs-lookup"><span data-stu-id="77167-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="77167-131">Types de retours</span><span class="sxs-lookup"><span data-stu-id="77167-131">Return Types</span></span>
<span data-ttu-id="77167-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="77167-132"><a name="Examples"> </a></span></span>

<span data-ttu-id="77167-133">Aucun.</span><span class="sxs-lookup"><span data-stu-id="77167-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="77167-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="77167-134">See also</span></span>
<span data-ttu-id="77167-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="77167-135"><a name="Examples"> </a></span></span>

<span data-ttu-id="77167-136">Aucun</span><span class="sxs-lookup"><span data-stu-id="77167-136">None.</span></span>
  

