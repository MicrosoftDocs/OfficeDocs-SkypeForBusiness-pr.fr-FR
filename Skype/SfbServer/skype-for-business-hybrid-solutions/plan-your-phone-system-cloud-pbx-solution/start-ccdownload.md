---
title: Démarrer-CcDownload
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: L’applet de commande Start-CcDownload télécharge le Skype pour connecteur de nuage Professionnel & fichier msi de façon synchrone.
ms.openlocfilehash: aec8d5c1848e7e55d6ed4b7e4d3633942f74ab55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="start-ccdownload"></a><span data-ttu-id="2c1f3-103">Démarrer-CcDownload</span><span class="sxs-lookup"><span data-stu-id="2c1f3-103">Start-CcDownload</span></span>
 
<span data-ttu-id="2c1f3-104">L’applet de commande Start-CcDownload télécharge le Skype pour connecteur de nuage Professionnel & fichier msi de façon synchrone.</span><span class="sxs-lookup"><span data-stu-id="2c1f3-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="2c1f3-105">Avec connecteur de nuage version 2.0 et ultérieure, vous pouvez également spécifier le paramètre DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="2c1f3-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="2c1f3-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="2c1f3-106">Examples</span></span>
<span data-ttu-id="2c1f3-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1f3-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="2c1f3-108">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="2c1f3-108">Example 1</span></span>

<span data-ttu-id="2c1f3-109">L’exemple suivant télécharge les bits du connecteur du nuage et le fichier msi de façon synchrone à partir du site de téléchargement public Cloud connecteur :</span><span class="sxs-lookup"><span data-stu-id="2c1f3-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="2c1f3-110">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="2c1f3-110">Example 2</span></span>

<span data-ttu-id="2c1f3-111">L’exemple suivant télécharge les bits du connecteur du nuage et le fichier msi de façon synchrone à partir d’un site de téléchargement privée :</span><span class="sxs-lookup"><span data-stu-id="2c1f3-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="2c1f3-112">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="2c1f3-112">Example 3</span></span>

<span data-ttu-id="2c1f3-113">Le troisième exemple télécharge les bits du connecteur du nuage et le fichier msi de façon synchrone à partir d’un site de téléchargement privée.</span><span class="sxs-lookup"><span data-stu-id="2c1f3-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="2c1f3-114">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="2c1f3-114">Detailed Description</span></span>
<span data-ttu-id="2c1f3-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1f3-115"></span></span>

<span data-ttu-id="2c1f3-116">Si une nouvelle version est disponible sur le site de téléchargement, début-CcDownload télécharger et installer le fichier msi à partir du site de téléchargement et puis télécharger les bits de connecteur de nuage de façon synchrone.</span><span class="sxs-lookup"><span data-stu-id="2c1f3-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="2c1f3-117">S’il n’existe aucune nouvelle version du fichier msi, début-CcDownload télécharge uniquement les bits du connecteur de nuage.</span><span class="sxs-lookup"><span data-stu-id="2c1f3-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="2c1f3-118">Si les bits du connecteur du nuage sont déjà téléchargés, début-CcDownload ne s’exécute pas.</span><span class="sxs-lookup"><span data-stu-id="2c1f3-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="2c1f3-119">Paramètres</span><span class="sxs-lookup"><span data-stu-id="2c1f3-119">Parameters</span></span>
<span data-ttu-id="2c1f3-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1f3-120"></span></span>

|<span data-ttu-id="2c1f3-121">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="2c1f3-121">**Parameter**</span></span>|<span data-ttu-id="2c1f3-122">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="2c1f3-122">**Required**</span></span>|<span data-ttu-id="2c1f3-123">**Type de**</span><span class="sxs-lookup"><span data-stu-id="2c1f3-123">**Type**</span></span>|<span data-ttu-id="2c1f3-124">**Description**</span><span class="sxs-lookup"><span data-stu-id="2c1f3-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c1f3-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="2c1f3-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="2c1f3-126">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2c1f3-126">Optional</span></span> <br/> |<span data-ttu-id="2c1f3-127">System.String</span><span class="sxs-lookup"><span data-stu-id="2c1f3-127">System.String</span></span>  <br/> | <span data-ttu-id="2c1f3-128">Site de téléchargement de l’URL complète d’une version spécifique du connecteur du Cloud dans le privé.</span><span class="sxs-lookup"><span data-stu-id="2c1f3-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="2c1f3-129">Utilisez ce paramètre avec prudence — Vérifiez que vous êtes conscient de la version du connecteur de Cloud vous téléchargez.</span><span class="sxs-lookup"><span data-stu-id="2c1f3-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="2c1f3-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="2c1f3-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="2c1f3-131">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2c1f3-131">Optional</span></span>  <br/> |<span data-ttu-id="2c1f3-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="2c1f3-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="2c1f3-133">Ignorez l’étape pour télécharger et installer le MSI à partir du site de téléchargement, télécharger uniquement les bits du connecteur de nuage.</span><span class="sxs-lookup"><span data-stu-id="2c1f3-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2c1f3-134">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="2c1f3-134">Input Types</span></span>
<span data-ttu-id="2c1f3-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1f3-135"></span></span>

<span data-ttu-id="2c1f3-136">Aucun.</span><span class="sxs-lookup"><span data-stu-id="2c1f3-136">None.</span></span> <span data-ttu-id="2c1f3-137">L’applet de commande Start-CcDownload n’accepte pas les entrées de pipeline.</span><span class="sxs-lookup"><span data-stu-id="2c1f3-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2c1f3-138">Types de retours</span><span class="sxs-lookup"><span data-stu-id="2c1f3-138">Return Types</span></span>
<span data-ttu-id="2c1f3-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1f3-139"></span></span>

<span data-ttu-id="2c1f3-140">Aucun</span><span class="sxs-lookup"><span data-stu-id="2c1f3-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2c1f3-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c1f3-141">See also</span></span>
<span data-ttu-id="2c1f3-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1f3-142"></span></span>

<span data-ttu-id="2c1f3-143">Aucun</span><span class="sxs-lookup"><span data-stu-id="2c1f3-143">None</span></span>
  

