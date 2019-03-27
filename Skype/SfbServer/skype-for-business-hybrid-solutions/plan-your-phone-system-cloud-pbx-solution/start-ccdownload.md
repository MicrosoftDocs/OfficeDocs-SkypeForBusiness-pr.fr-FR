---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: L’applet de commande Start-CcDownload télécharge le Skype pour bits Édition nuage connecteur et fichier msi de façon synchrone.
ms.openlocfilehash: cc157825df75a4534422cb0a2fd07abb0ae0daea
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893837"
---
# <a name="start-ccdownload"></a><span data-ttu-id="b9e66-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="b9e66-103">Start-CcDownload</span></span>
 
<span data-ttu-id="b9e66-104">L’applet de commande Start-CcDownload télécharge le Skype pour bits Édition nuage connecteur et fichier msi de façon synchrone.</span><span class="sxs-lookup"><span data-stu-id="b9e66-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="b9e66-105">Avec le nuage connecteur version 2.0 et versions ultérieure, vous pouvez également spécifier le paramètre DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="b9e66-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="b9e66-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="b9e66-106">Examples</span></span>
<span data-ttu-id="b9e66-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b9e66-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="b9e66-108">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="b9e66-108">Example 1</span></span>

<span data-ttu-id="b9e66-109">L’exemple suivant télécharge les bits nuage connecteur et le fichier msi de façon synchrone à partir du site de téléchargement public nuage connecteur :</span><span class="sxs-lookup"><span data-stu-id="b9e66-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="b9e66-110">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="b9e66-110">Example 2</span></span>

<span data-ttu-id="b9e66-111">L’exemple suivant télécharge les bits nuage connecteur et le fichier msi de façon synchrone à partir d’un site de téléchargement privée :</span><span class="sxs-lookup"><span data-stu-id="b9e66-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="b9e66-112">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="b9e66-112">Example 3</span></span>

<span data-ttu-id="b9e66-113">Le troisième exemple télécharge les bits nuage connecteur et le fichier msi de façon synchrone à partir d’un site de téléchargement privée.</span><span class="sxs-lookup"><span data-stu-id="b9e66-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="b9e66-114">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="b9e66-114">Detailed Description</span></span>
<span data-ttu-id="b9e66-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b9e66-115"></span></span>

<span data-ttu-id="b9e66-116">Si une nouvelle version est disponible dans le site de téléchargement, Start-CcDownload télécharger et installer le fichier msi à partir du site de téléchargement et puis le télécharger sur le nuage connecteur de façon synchrone.</span><span class="sxs-lookup"><span data-stu-id="b9e66-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="b9e66-117">S’il n’existe aucune nouvelle version du fichier msi, Start-CcDownload télécharge les fichiers binaires dans le nuage connecteur uniquement.</span><span class="sxs-lookup"><span data-stu-id="b9e66-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="b9e66-118">Si les fichiers binaires dans le nuage connecteur sont déjà téléchargés, Start-CcDownload ne s’exécute pas.</span><span class="sxs-lookup"><span data-stu-id="b9e66-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b9e66-119">Paramètres</span><span class="sxs-lookup"><span data-stu-id="b9e66-119">Parameters</span></span>
<span data-ttu-id="b9e66-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b9e66-120"></span></span>

|<span data-ttu-id="b9e66-121">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="b9e66-121">**Parameter**</span></span>|<span data-ttu-id="b9e66-122">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="b9e66-122">**Required**</span></span>|<span data-ttu-id="b9e66-123">**Type**</span><span class="sxs-lookup"><span data-stu-id="b9e66-123">**Type**</span></span>|<span data-ttu-id="b9e66-124">**Description**</span><span class="sxs-lookup"><span data-stu-id="b9e66-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b9e66-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="b9e66-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="b9e66-126">Facultatif </span><span class="sxs-lookup"><span data-stu-id="b9e66-126">Optional</span></span> <br/> |<span data-ttu-id="b9e66-127">System.String</span><span class="sxs-lookup"><span data-stu-id="b9e66-127">System.String</span></span>  <br/> | <span data-ttu-id="b9e66-128">Site de téléchargement de l’URL complète d’une version spécifique du nuage connecteur privées.</span><span class="sxs-lookup"><span data-stu-id="b9e66-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="b9e66-129">Utilisez ce paramètre avec précaution, vérifiez que vous avez pris connaissance de la version du nuage connecteur télécharger.</span><span class="sxs-lookup"><span data-stu-id="b9e66-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="b9e66-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="b9e66-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="b9e66-131">Facultatif</span><span class="sxs-lookup"><span data-stu-id="b9e66-131">Optional</span></span>  <br/> |<span data-ttu-id="b9e66-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="b9e66-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="b9e66-133">Ignorez l’étape pour télécharger et installer MSI à partir du site de téléchargement, télécharger uniquement les bits de nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="b9e66-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="b9e66-134">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="b9e66-134">Input Types</span></span>
<span data-ttu-id="b9e66-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b9e66-135"></span></span>

<span data-ttu-id="b9e66-136">Aucun.</span><span class="sxs-lookup"><span data-stu-id="b9e66-136">None.</span></span> <span data-ttu-id="b9e66-137">L’applet de commande Start-CcDownload n’accepte pas la saisie de données redirigées.</span><span class="sxs-lookup"><span data-stu-id="b9e66-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b9e66-138">Types de retours</span><span class="sxs-lookup"><span data-stu-id="b9e66-138">Return Types</span></span>
<span data-ttu-id="b9e66-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b9e66-139"></span></span>

<span data-ttu-id="b9e66-140">Aucune</span><span class="sxs-lookup"><span data-stu-id="b9e66-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b9e66-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9e66-141">See also</span></span>
<span data-ttu-id="b9e66-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b9e66-142"></span></span>

<span data-ttu-id="b9e66-143">Aucun</span><span class="sxs-lookup"><span data-stu-id="b9e66-143">None</span></span>
  

