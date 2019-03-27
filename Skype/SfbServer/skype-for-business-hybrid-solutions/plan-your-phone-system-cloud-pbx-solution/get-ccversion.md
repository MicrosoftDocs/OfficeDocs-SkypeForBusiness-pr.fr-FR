---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Retourne la version de la solution de nuage connecteur. Get-CCVersion utilisable uniquement sur l’ordinateur hôte du nuage connecteur.
ms.openlocfilehash: 5e5428e53d53eec66bafa9eb566059ef1b5a5833
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881332"
---
# <a name="get-ccversion"></a><span data-ttu-id="0bdc3-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="0bdc3-104">Get-CcVersion</span></span>
 
<span data-ttu-id="0bdc3-105">Retourne la version de la solution de nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="0bdc3-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="0bdc3-106">Get-CCVersion utilisable uniquement sur l’ordinateur hôte du nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="0bdc3-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="0bdc3-107">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="0bdc3-107">Detailed Description</span></span>

<span data-ttu-id="0bdc3-108">Renvoie la version de l’appliance nuage connecteur basés sur des scripts PowerShell installés, les fichiers dans le répertoire de l’application et les ordinateurs virtuels déployés sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="0bdc3-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0bdc3-109">Paramètres</span><span class="sxs-lookup"><span data-stu-id="0bdc3-109">Parameters</span></span>

|<span data-ttu-id="0bdc3-110">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="0bdc3-110">**Parameter**</span></span>|<span data-ttu-id="0bdc3-111">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="0bdc3-111">**Required**</span></span>|<span data-ttu-id="0bdc3-112">**Type**</span><span class="sxs-lookup"><span data-stu-id="0bdc3-112">**Type**</span></span>|<span data-ttu-id="0bdc3-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="0bdc3-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0bdc3-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="0bdc3-114">VersionType</span></span>  <br/> |<span data-ttu-id="0bdc3-115">Facultatif</span><span class="sxs-lookup"><span data-stu-id="0bdc3-115">Optional</span></span>  <br/> |<span data-ttu-id="0bdc3-116">System.String</span><span class="sxs-lookup"><span data-stu-id="0bdc3-116">System.String</span></span>  <br/> |<span data-ttu-id="0bdc3-117">Type de version.</span><span class="sxs-lookup"><span data-stu-id="0bdc3-117">Type of version.</span></span> <span data-ttu-id="0bdc3-118">Valeur du paramètre peut être RunningScripts, RunningBits, BackupBits ou tous.</span><span class="sxs-lookup"><span data-stu-id="0bdc3-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="0bdc3-119">Valeur par défaut est RunningScripts.</span><span class="sxs-lookup"><span data-stu-id="0bdc3-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="0bdc3-120">Exemples</span><span class="sxs-lookup"><span data-stu-id="0bdc3-120">Examples</span></span>
<span data-ttu-id="0bdc3-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0bdc3-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="0bdc3-122">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="0bdc3-122">Example 1</span></span>

<span data-ttu-id="0bdc3-123">L’exemple suivant indique la version de nuage connecteur du script en cours d’exécution dans votre console PowerShell ouverte :</span><span class="sxs-lookup"><span data-stu-id="0bdc3-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="0bdc3-124">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="0bdc3-124">Example 2</span></span>

<span data-ttu-id="0bdc3-125">L’exemple suivant indique la version de nuage connecteur des binaires déployés sur les ordinateurs virtuels en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="0bdc3-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="0bdc3-126">Vous pouvez voir la version dans les noms d’ordinateur virtuel en cours d’exécution dans le Gestionnaire Hyper-v :</span><span class="sxs-lookup"><span data-stu-id="0bdc3-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="0bdc3-127">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="0bdc3-127">Input Types</span></span>
<span data-ttu-id="0bdc3-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0bdc3-128"></span></span>

<span data-ttu-id="0bdc3-129">Aucun.</span><span class="sxs-lookup"><span data-stu-id="0bdc3-129">None.</span></span> <span data-ttu-id="0bdc3-130">L’applet de commande Get-CcVersion n’accepte pas la saisie de données redirigées.</span><span class="sxs-lookup"><span data-stu-id="0bdc3-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0bdc3-131">Types de retours</span><span class="sxs-lookup"><span data-stu-id="0bdc3-131">Return Types</span></span>
<span data-ttu-id="0bdc3-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0bdc3-132"></span></span>

<span data-ttu-id="0bdc3-133">Aucun.</span><span class="sxs-lookup"><span data-stu-id="0bdc3-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0bdc3-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0bdc3-134">See also</span></span>
<span data-ttu-id="0bdc3-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0bdc3-135"></span></span>

<span data-ttu-id="0bdc3-136">Aucun</span><span class="sxs-lookup"><span data-stu-id="0bdc3-136">None.</span></span>
  

