---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: La cmdlet Export-CcRootCertificate exporte le certificat d’ac racine vers un fichier local sur le serveur hôte de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: 2b252eba4688deb790d85b0c3663b09a9e85e7b9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800914"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="a1683-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="a1683-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="a1683-104">La cmdlet Export-CcRootCertificate exporte le certificat d’ac racine vers un fichier local sur le serveur hôte de la version Cloud Connector de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a1683-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="a1683-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="a1683-105">Examples</span></span>
<span data-ttu-id="a1683-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a1683-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="a1683-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="a1683-107">Example 1</span></span>

<span data-ttu-id="a1683-108">L’exemple suivant définit le paramètre Path en tant que chemin d’accès au répertoire, et non en tant que chemin d’accès de fichier.</span><span class="sxs-lookup"><span data-stu-id="a1683-108">The following example sets the Path parameter as a directory path—not a file path.</span></span> <span data-ttu-id="a1683-109">Il génère le fichier c:\test\CCERootCertificates.p7b.</span><span class="sxs-lookup"><span data-stu-id="a1683-109">It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="a1683-110">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="a1683-110">Detailed Description</span></span>
<span data-ttu-id="a1683-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a1683-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="a1683-112">LExport-CcRootCertificate cmdlet vous permet d’enregistrer les certificats racine et intermédiaires dans un chemin d’accès au fichier.</span><span class="sxs-lookup"><span data-stu-id="a1683-112">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path.</span></span> <span data-ttu-id="a1683-113">Cela peut être utile en cas de scénario de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="a1683-113">This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="a1683-114">Paramètres</span><span class="sxs-lookup"><span data-stu-id="a1683-114">Parameters</span></span>
<span data-ttu-id="a1683-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a1683-115"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="a1683-116">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="a1683-116">**Parameter**</span></span>|<span data-ttu-id="a1683-117">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="a1683-117">**Required**</span></span>|<span data-ttu-id="a1683-118">**Type**</span><span class="sxs-lookup"><span data-stu-id="a1683-118">**Type**</span></span>|<span data-ttu-id="a1683-119">**Description**</span><span class="sxs-lookup"><span data-stu-id="a1683-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a1683-120">Path</span><span class="sxs-lookup"><span data-stu-id="a1683-120">Path</span></span>  <br/> |<span data-ttu-id="a1683-121">Requis</span><span class="sxs-lookup"><span data-stu-id="a1683-121">Required</span></span>  <br/> |<span data-ttu-id="a1683-122">System.String</span><span class="sxs-lookup"><span data-stu-id="a1683-122">System.String</span></span>  <br/> |<span data-ttu-id="a1683-123">Chemin d’accès au fichier où le certificat sera stocké.</span><span class="sxs-lookup"><span data-stu-id="a1683-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a1683-124">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="a1683-124">Input Types</span></span>
<span data-ttu-id="a1683-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a1683-125"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="a1683-126">Aucun.</span><span class="sxs-lookup"><span data-stu-id="a1683-126">None.</span></span> <span data-ttu-id="a1683-127">La cmdlet Export-CcRootCertificate n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="a1683-127">The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="a1683-128">Types de retour</span><span class="sxs-lookup"><span data-stu-id="a1683-128">Return Types</span></span>
<span data-ttu-id="a1683-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a1683-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="a1683-130">Aucun</span><span class="sxs-lookup"><span data-stu-id="a1683-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a1683-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a1683-131">See also</span></span>
<span data-ttu-id="a1683-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a1683-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="a1683-133">Aucun</span><span class="sxs-lookup"><span data-stu-id="a1683-133">None</span></span>
  

