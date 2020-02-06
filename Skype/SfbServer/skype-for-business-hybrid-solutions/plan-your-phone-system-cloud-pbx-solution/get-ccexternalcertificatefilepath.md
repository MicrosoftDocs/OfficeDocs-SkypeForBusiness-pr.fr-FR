---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: L’applet de commande Get-CcExternalCertificateFilePath renvoie le chemin d’accès du fichier du certificat externe pour le déploiement de Skype Entreprise, version Cloud Connector. L’utilisateur prépare ce certificat.
ms.openlocfilehash: 143595d30bb71756544a16ad464da05a229f476d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799904"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="4e622-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="4e622-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="4e622-p102">L’applet de commande Get-CcExternalCertificateFilePath renvoie le chemin d’accès du fichier du certificat externe pour le déploiement de Skype Entreprise, version Cloud Connector. L’utilisateur prépare ce certificat.</span><span class="sxs-lookup"><span data-stu-id="4e622-p102">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment. The user prepares this certificate.</span></span>
  
<span data-ttu-id="4e622-107">Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="4e622-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="4e622-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="4e622-108">Examples</span></span>
<span data-ttu-id="4e622-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4e622-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="4e622-110">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="4e622-110">Example 1</span></span>

<span data-ttu-id="4e622-111">L’exemple suivant montre le chemin d’accès du certificat pour le serveur Edge :</span><span class="sxs-lookup"><span data-stu-id="4e622-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="4e622-112">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="4e622-112">Example 2</span></span>

<span data-ttu-id="4e622-113">L’exemple suivant montre le certificat pour le serveur de médiation :</span><span class="sxs-lookup"><span data-stu-id="4e622-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="4e622-114">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="4e622-114">Detailed Description</span></span>
<span data-ttu-id="4e622-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4e622-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="4e622-p103">Pendant le déploiement ou la modification de la typologie, vous devez spécifier le chemin d’accès pour le certificat du serveur Edge et éventuellement pour le serveur de médiation. Le certificat pour le serveur de médiation est obligatoire si TLS est utilisé entre la passerelle et le serveur de médiation. Pour changer le chemin d’accès, utilisez l’applet de commande Set-CcExternalCertificateFilePath.</span><span class="sxs-lookup"><span data-stu-id="4e622-p103">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server. The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server. To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="4e622-119">Paramètres</span><span class="sxs-lookup"><span data-stu-id="4e622-119">Parameters</span></span>
<span data-ttu-id="4e622-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4e622-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="4e622-121">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="4e622-121">**Parameter**</span></span>|<span data-ttu-id="4e622-122">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="4e622-122">**Required**</span></span>|<span data-ttu-id="4e622-123">**Type**</span><span class="sxs-lookup"><span data-stu-id="4e622-123">**Type**</span></span>|<span data-ttu-id="4e622-124">**Description**</span><span class="sxs-lookup"><span data-stu-id="4e622-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4e622-125">Cible</span><span class="sxs-lookup"><span data-stu-id="4e622-125">Target</span></span>  <br/> |<span data-ttu-id="4e622-126">Facultatif</span><span class="sxs-lookup"><span data-stu-id="4e622-126">Optional</span></span>  <br/> | <span data-ttu-id="4e622-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="4e622-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="4e622-p104">Type de chemin d’accès de fichier requis. Les types comprennent :</span><span class="sxs-lookup"><span data-stu-id="4e622-p104">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="4e622-130">Le serveur Edge (défaut)</span><span class="sxs-lookup"><span data-stu-id="4e622-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="4e622-131">Le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="4e622-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="4e622-132">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="4e622-132">Input Types</span></span>
<span data-ttu-id="4e622-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4e622-133"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="4e622-134">L’applet de commande Get-CcExternalCertificateFilePath n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="4e622-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4e622-135">Types de retours</span><span class="sxs-lookup"><span data-stu-id="4e622-135">Return Types</span></span>
<span data-ttu-id="4e622-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4e622-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="4e622-137">La commande renvoie un chemin d’accès de fichier.</span><span class="sxs-lookup"><span data-stu-id="4e622-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4e622-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4e622-138">See also</span></span>
<span data-ttu-id="4e622-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4e622-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="4e622-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="4e622-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  

