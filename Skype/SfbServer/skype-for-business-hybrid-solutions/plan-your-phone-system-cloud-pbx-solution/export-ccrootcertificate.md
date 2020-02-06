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
description: "L'applet de commande Export-CcRootCertificate exporte le certificat de l'AC racine dans un fichier local sur le serveur hôte de la version Cloud Connector de Skype Entreprise. "
ms.openlocfilehash: 2b252eba4688deb790d85b0c3663b09a9e85e7b9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800914"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="c96d0-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="c96d0-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="c96d0-104">L'applet de commande Export-CcRootCertificate exporte le certificat de l'AC racine dans un fichier local sur le serveur hôte de la version Cloud Connector de Skype Entreprise. </span><span class="sxs-lookup"><span data-stu-id="c96d0-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="c96d0-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="c96d0-105">Examples</span></span>
<span data-ttu-id="c96d0-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c96d0-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="c96d0-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="c96d0-107">Example 1</span></span>

<span data-ttu-id="c96d0-p101">L'exemple suivant définit le paramètre Path en tant que chemin de répertoire, non chemin de fichier. Il génère le fichier c:\test\CCERootCertificates.p7b.</span><span class="sxs-lookup"><span data-stu-id="c96d0-p101">The following example sets the Path parameter as a directory path—not a file path. It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="c96d0-110">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="c96d0-110">Detailed Description</span></span>
<span data-ttu-id="c96d0-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c96d0-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="c96d0-p102">L'applet de commande Export-CcRootCertificate permet d'enregistrer les certificats racine et intermédiaires sur le chemin de fichier. Ceci peut être utile en cas de récupération d’urgence. </span><span class="sxs-lookup"><span data-stu-id="c96d0-p102">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path. This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="c96d0-114">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c96d0-114">Parameters</span></span>
<span data-ttu-id="c96d0-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c96d0-115"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="c96d0-116">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="c96d0-116">**Parameter**</span></span>|<span data-ttu-id="c96d0-117">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="c96d0-117">**Required**</span></span>|<span data-ttu-id="c96d0-118">**Type**</span><span class="sxs-lookup"><span data-stu-id="c96d0-118">**Type**</span></span>|<span data-ttu-id="c96d0-119">**Description**</span><span class="sxs-lookup"><span data-stu-id="c96d0-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c96d0-120"> Path</span><span class="sxs-lookup"><span data-stu-id="c96d0-120">Path</span></span>  <br/> |<span data-ttu-id="c96d0-121">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="c96d0-121">Required</span></span>  <br/> |<span data-ttu-id="c96d0-122">System.String</span><span class="sxs-lookup"><span data-stu-id="c96d0-122">System.String</span></span>  <br/> |<span data-ttu-id="c96d0-123">Chemin de fichier dans lequel le certificat est stocké. </span><span class="sxs-lookup"><span data-stu-id="c96d0-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c96d0-124">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="c96d0-124">Input Types</span></span>
<span data-ttu-id="c96d0-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c96d0-125"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="c96d0-p103">Aucun. L'applet de commande Export-CcRootCertificate n'accepte pas l'entrée redirigée. </span><span class="sxs-lookup"><span data-stu-id="c96d0-p103">None. The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="c96d0-128">Types de retours</span><span class="sxs-lookup"><span data-stu-id="c96d0-128">Return Types</span></span>
<span data-ttu-id="c96d0-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c96d0-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="c96d0-130">Aucune</span><span class="sxs-lookup"><span data-stu-id="c96d0-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c96d0-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c96d0-131">See also</span></span>
<span data-ttu-id="c96d0-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c96d0-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="c96d0-133">Aucun</span><span class="sxs-lookup"><span data-stu-id="c96d0-133">None</span></span>
  

