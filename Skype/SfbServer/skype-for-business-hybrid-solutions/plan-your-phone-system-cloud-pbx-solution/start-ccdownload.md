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
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: L’applet de connexion Start-CcDownload télécharge les fichiers bits et le fichier MSI de Skype entreprise version Cloud Connector.
ms.openlocfilehash: 184c15d1932a179bb9ae07da515eeacfc115dfae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286942"
---
# <a name="start-ccdownload"></a><span data-ttu-id="66236-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="66236-103">Start-CcDownload</span></span>
 
<span data-ttu-id="66236-104">L’applet de connexion Start-CcDownload télécharge les fichiers bits et le fichier MSI de Skype entreprise version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="66236-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="66236-105">Avec le Cloud Connector version 2,0 et les versions ultérieures, vous pouvez également spécifier le paramètre DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="66236-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="66236-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="66236-106">Examples</span></span>
<span data-ttu-id="66236-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="66236-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="66236-108">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="66236-108">Example 1</span></span>

<span data-ttu-id="66236-109">L’exemple ci-après télécharge les bits et le fichier MSI du Cloud Connector à partir du site de téléchargement public Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="66236-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="66236-110">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="66236-110">Example 2</span></span>

<span data-ttu-id="66236-111">L’exemple suivant télécharge les fichiers msi et de connexion Cloud à partir d’un site de téléchargement privé:</span><span class="sxs-lookup"><span data-stu-id="66236-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="66236-112">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="66236-112">Example 3</span></span>

<span data-ttu-id="66236-113">Le troisième exemple télécharge les fichiers msi et de connexion Cloud à partir d’un site de téléchargement privé.</span><span class="sxs-lookup"><span data-stu-id="66236-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="66236-114">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="66236-114">Detailed Description</span></span>
<span data-ttu-id="66236-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="66236-115"></span></span>

<span data-ttu-id="66236-116">Dans le cas où une nouvelle version est disponible sur le site de téléchargement, Start-CcDownload télécharge et installe le fichier MSI à partir du site de téléchargement, puis télécharge les bits du connecteur Cloud de manière synchrone.</span><span class="sxs-lookup"><span data-stu-id="66236-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="66236-117">S’il n’y a pas de nouvelle version du fichier MSI, Start-CcDownload télécharge uniquement les bits du connecteur Cloud.</span><span class="sxs-lookup"><span data-stu-id="66236-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="66236-118">Si les bits du connecteur Cloud ont déjà été téléchargés, Start-CcDownload ne s’exécute pas.</span><span class="sxs-lookup"><span data-stu-id="66236-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="66236-119">Paramètres</span><span class="sxs-lookup"><span data-stu-id="66236-119">Parameters</span></span>
<span data-ttu-id="66236-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="66236-120"></span></span>

|<span data-ttu-id="66236-121">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="66236-121">**Parameter**</span></span>|<span data-ttu-id="66236-122">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="66236-122">**Required**</span></span>|<span data-ttu-id="66236-123">**Type**</span><span class="sxs-lookup"><span data-stu-id="66236-123">**Type**</span></span>|<span data-ttu-id="66236-124">**Description**</span><span class="sxs-lookup"><span data-stu-id="66236-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="66236-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="66236-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="66236-126">Facultatif </span><span class="sxs-lookup"><span data-stu-id="66236-126">Optional</span></span> <br/> |<span data-ttu-id="66236-127">System.String</span><span class="sxs-lookup"><span data-stu-id="66236-127">System.String</span></span>  <br/> | <span data-ttu-id="66236-128">URL complète d’une version spécifique du Cloud Connector dans le site de téléchargement privé.</span><span class="sxs-lookup"><span data-stu-id="66236-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="66236-129">Utilisez ce paramètre avec précaution; Vérifiez quelle version de Cloud Connector vous téléchargez.</span><span class="sxs-lookup"><span data-stu-id="66236-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="66236-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="66236-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="66236-131">Facultatif</span><span class="sxs-lookup"><span data-stu-id="66236-131">Optional</span></span>  <br/> |<span data-ttu-id="66236-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="66236-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="66236-133">Ignorer l’étape permettant de télécharger et d’installer MSI à partir du site de téléchargement, téléchargez uniquement les bits du connecteur Cloud.</span><span class="sxs-lookup"><span data-stu-id="66236-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="66236-134">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="66236-134">Input Types</span></span>
<span data-ttu-id="66236-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="66236-135"></span></span>

<span data-ttu-id="66236-136">Aucun.</span><span class="sxs-lookup"><span data-stu-id="66236-136">None.</span></span> <span data-ttu-id="66236-137">L’applet de commande Start-CcDownload n’accepte pas les entrées pipelines.</span><span class="sxs-lookup"><span data-stu-id="66236-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="66236-138">Types de retours</span><span class="sxs-lookup"><span data-stu-id="66236-138">Return Types</span></span>
<span data-ttu-id="66236-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="66236-139"></span></span>

<span data-ttu-id="66236-140">Aucune</span><span class="sxs-lookup"><span data-stu-id="66236-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="66236-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="66236-141">See also</span></span>
<span data-ttu-id="66236-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="66236-142"></span></span>

<span data-ttu-id="66236-143">Aucun</span><span class="sxs-lookup"><span data-stu-id="66236-143">None</span></span>
  

