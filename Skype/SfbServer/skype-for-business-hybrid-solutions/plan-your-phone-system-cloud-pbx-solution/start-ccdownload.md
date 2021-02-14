---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: La cmdlet Start-CcDownload télécharge les bits et le fichier msi de la version Cloud Connector de Skype Entreprise de manière synchrone.
ms.openlocfilehash: 3298b02fbb792392860f05ebb15a9221b45e47b4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824178"
---
# <a name="start-ccdownload"></a><span data-ttu-id="b2a31-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="b2a31-103">Start-CcDownload</span></span>
 
<span data-ttu-id="b2a31-104">La cmdlet Start-CcDownload télécharge les bits et le fichier msi de la version Cloud Connector de Skype Entreprise de manière synchrone.</span><span class="sxs-lookup"><span data-stu-id="b2a31-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="b2a31-105">Avec Cloud Connector version 2.0 et versions ultérieures, vous pouvez également spécifier le paramètre DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="b2a31-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="b2a31-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="b2a31-106">Examples</span></span>
<span data-ttu-id="b2a31-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b2a31-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="b2a31-108">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="b2a31-108">Example 1</span></span>

<span data-ttu-id="b2a31-109">L’exemple suivant télécharge les bits et le fichier msi Cloud Connector de manière synchrone à partir du site de téléchargement public Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="b2a31-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="b2a31-110">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="b2a31-110">Example 2</span></span>

<span data-ttu-id="b2a31-111">L’exemple suivant télécharge les bits et le fichier msi Cloud Connector de manière synchrone à partir d’un site de téléchargement privé :</span><span class="sxs-lookup"><span data-stu-id="b2a31-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="b2a31-112">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="b2a31-112">Example 3</span></span>

<span data-ttu-id="b2a31-113">Le troisième exemple télécharge les bits et le fichier msi Cloud Connector de manière synchrone à partir d’un site de téléchargement privé.</span><span class="sxs-lookup"><span data-stu-id="b2a31-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="b2a31-114">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="b2a31-114">Detailed Description</span></span>
<span data-ttu-id="b2a31-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b2a31-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="b2a31-116">S’il existe une nouvelle version disponible sur le site de téléchargement, Start-CcDownload télécharge et installe le fichier msi à partir du site de téléchargement, puis télécharge les bits Cloud Connector de manière synchrone.</span><span class="sxs-lookup"><span data-stu-id="b2a31-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="b2a31-117">S’il n’existe aucune nouvelle version du fichier msi, Start-CcDownload téléchargera uniquement les bits Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="b2a31-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="b2a31-118">Si les bits Cloud Connector sont déjà téléchargés, Start-CcDownload ne s’exécute pas.</span><span class="sxs-lookup"><span data-stu-id="b2a31-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b2a31-119">Paramètres</span><span class="sxs-lookup"><span data-stu-id="b2a31-119">Parameters</span></span>
<span data-ttu-id="b2a31-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b2a31-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="b2a31-121">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="b2a31-121">**Parameter**</span></span>|<span data-ttu-id="b2a31-122">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="b2a31-122">**Required**</span></span>|<span data-ttu-id="b2a31-123">**Type**</span><span class="sxs-lookup"><span data-stu-id="b2a31-123">**Type**</span></span>|<span data-ttu-id="b2a31-124">**Description**</span><span class="sxs-lookup"><span data-stu-id="b2a31-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b2a31-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="b2a31-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="b2a31-126">Facultatif</span><span class="sxs-lookup"><span data-stu-id="b2a31-126">Optional</span></span> <br/> |<span data-ttu-id="b2a31-127">System.String</span><span class="sxs-lookup"><span data-stu-id="b2a31-127">System.String</span></span>  <br/> | <span data-ttu-id="b2a31-128">URL complète d’une version spécifique de Cloud Connector dans le site de téléchargement privé.</span><span class="sxs-lookup"><span data-stu-id="b2a31-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="b2a31-129">Utilisez ce paramètre avec précaution, assurez-vous de connaître la version de Cloud Connector que vous téléchargez.</span><span class="sxs-lookup"><span data-stu-id="b2a31-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="b2a31-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="b2a31-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="b2a31-131">Facultatif</span><span class="sxs-lookup"><span data-stu-id="b2a31-131">Optional</span></span>  <br/> |<span data-ttu-id="b2a31-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="b2a31-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="b2a31-133">Ignorez l’étape de téléchargement et d’installation de MSI à partir du site de téléchargement, téléchargez uniquement les bits Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="b2a31-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="b2a31-134">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="b2a31-134">Input Types</span></span>
<span data-ttu-id="b2a31-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b2a31-135"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="b2a31-136">Aucun.</span><span class="sxs-lookup"><span data-stu-id="b2a31-136">None.</span></span> <span data-ttu-id="b2a31-137">La cmdlet Start-CcDownload n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="b2a31-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b2a31-138">Types de retour</span><span class="sxs-lookup"><span data-stu-id="b2a31-138">Return Types</span></span>
<span data-ttu-id="b2a31-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b2a31-139"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="b2a31-140">Aucun</span><span class="sxs-lookup"><span data-stu-id="b2a31-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b2a31-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2a31-141">See also</span></span>
<span data-ttu-id="b2a31-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b2a31-142"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="b2a31-143">Aucun</span><span class="sxs-lookup"><span data-stu-id="b2a31-143">None</span></span>
  

