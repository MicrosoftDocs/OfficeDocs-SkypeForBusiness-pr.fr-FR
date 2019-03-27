---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: "L'applet de commande Export-CcRootCertificate exporte le certificat de l'AC racine dans un fichier local sur le serveur hôte de la version Cloud Connector de Skype Entreprise. "
ms.openlocfilehash: c2647baa9ab6762feb8f550e0d726b18ab5d3090
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889223"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="2f999-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="2f999-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="2f999-104">L'applet de commande Export-CcRootCertificate exporte le certificat de l'AC racine dans un fichier local sur le serveur hôte de la version Cloud Connector de Skype Entreprise. </span><span class="sxs-lookup"><span data-stu-id="2f999-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="2f999-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="2f999-105">Examples</span></span>
<span data-ttu-id="2f999-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2f999-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="2f999-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="2f999-107">Example 1</span></span>

<span data-ttu-id="2f999-p101">L'exemple suivant définit le paramètre Path en tant que chemin de répertoire, non chemin de fichier. Il génère le fichier c:\test\CCERootCertificates.p7b.</span><span class="sxs-lookup"><span data-stu-id="2f999-p101">The following example sets the Path parameter as a directory path—not a file path. It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="2f999-110">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="2f999-110">Detailed Description</span></span>
<span data-ttu-id="2f999-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2f999-111"></span></span>

<span data-ttu-id="2f999-p102">L'applet de commande Export-CcRootCertificate permet d'enregistrer les certificats racine et intermédiaires sur le chemin de fichier. Ceci peut être utile en cas de récupération d’urgence. </span><span class="sxs-lookup"><span data-stu-id="2f999-p102">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path. This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="2f999-114">Paramètres</span><span class="sxs-lookup"><span data-stu-id="2f999-114">Parameters</span></span>
<span data-ttu-id="2f999-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2f999-115"></span></span>

|<span data-ttu-id="2f999-116">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="2f999-116">**Parameter**</span></span>|<span data-ttu-id="2f999-117">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="2f999-117">**Required**</span></span>|<span data-ttu-id="2f999-118">**Type**</span><span class="sxs-lookup"><span data-stu-id="2f999-118">**Type**</span></span>|<span data-ttu-id="2f999-119">**Description**</span><span class="sxs-lookup"><span data-stu-id="2f999-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2f999-120"> Path</span><span class="sxs-lookup"><span data-stu-id="2f999-120">Path</span></span>  <br/> |<span data-ttu-id="2f999-121">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2f999-121">Required</span></span>  <br/> |<span data-ttu-id="2f999-122">System.String</span><span class="sxs-lookup"><span data-stu-id="2f999-122">System.String</span></span>  <br/> |<span data-ttu-id="2f999-123">Chemin de fichier dans lequel le certificat est stocké. </span><span class="sxs-lookup"><span data-stu-id="2f999-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2f999-124">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="2f999-124">Input Types</span></span>
<span data-ttu-id="2f999-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2f999-125"></span></span>

<span data-ttu-id="2f999-p103">Aucun. L'applet de commande Export-CcRootCertificate n'accepte pas l'entrée redirigée. </span><span class="sxs-lookup"><span data-stu-id="2f999-p103">None. The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="2f999-128">Types de retours</span><span class="sxs-lookup"><span data-stu-id="2f999-128">Return Types</span></span>
<span data-ttu-id="2f999-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2f999-129"></span></span>

<span data-ttu-id="2f999-130">Aucune</span><span class="sxs-lookup"><span data-stu-id="2f999-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2f999-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f999-131">See also</span></span>
<span data-ttu-id="2f999-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2f999-132"></span></span>

<span data-ttu-id="2f999-133">Aucun</span><span class="sxs-lookup"><span data-stu-id="2f999-133">None</span></span>
  

