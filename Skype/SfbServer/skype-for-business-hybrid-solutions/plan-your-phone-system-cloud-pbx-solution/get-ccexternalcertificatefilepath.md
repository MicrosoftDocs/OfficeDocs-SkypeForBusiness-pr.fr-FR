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
description: LGet-CcExternalCertificateFilePath cmdlet renvoie le chemin d’accès du fichier de certificat externe pour le déploiement de Skype Entreprise, version Cloud Connector. L’utilisateur prépare ce certificat.
ms.openlocfilehash: 143595d30bb71756544a16ad464da05a229f476d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799904"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="41962-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="41962-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="41962-105">LGet-CcExternalCertificateFilePath cmdlet renvoie le chemin d’accès du fichier de certificat externe pour le déploiement de Skype Entreprise, version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="41962-105">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="41962-106">L’utilisateur prépare ce certificat.</span><span class="sxs-lookup"><span data-stu-id="41962-106">The user prepares this certificate.</span></span>
  
<span data-ttu-id="41962-107">Cette cmdlet s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="41962-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="41962-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="41962-108">Examples</span></span>
<span data-ttu-id="41962-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="41962-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="41962-110">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="41962-110">Example 1</span></span>

<span data-ttu-id="41962-111">L’exemple suivant montre le chemin d’accès du certificat pour le serveur Edge :</span><span class="sxs-lookup"><span data-stu-id="41962-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="41962-112">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="41962-112">Example 2</span></span>

<span data-ttu-id="41962-113">L’exemple suivant montre le jeu de certificats pour le serveur de médiation :</span><span class="sxs-lookup"><span data-stu-id="41962-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="41962-114">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="41962-114">Detailed Description</span></span>
<span data-ttu-id="41962-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="41962-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="41962-116">Pendant le déploiement ou lors de la modification de la topologie, vous devez spécifier le chemin d’accès du certificat du serveur Edge et, éventuellement, du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="41962-116">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server.</span></span> <span data-ttu-id="41962-117">Le certificat pour le serveur de médiation est requis si TLS est utilisé entre la ou les passerelles et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="41962-117">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="41962-118">Pour modifier le chemin d’accès, utilisez Set-CcExternalCertificateFilePath cmdlet.</span><span class="sxs-lookup"><span data-stu-id="41962-118">To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="41962-119">Paramètres</span><span class="sxs-lookup"><span data-stu-id="41962-119">Parameters</span></span>
<span data-ttu-id="41962-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="41962-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="41962-121">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="41962-121">**Parameter**</span></span>|<span data-ttu-id="41962-122">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="41962-122">**Required**</span></span>|<span data-ttu-id="41962-123">**Type**</span><span class="sxs-lookup"><span data-stu-id="41962-123">**Type**</span></span>|<span data-ttu-id="41962-124">**Description**</span><span class="sxs-lookup"><span data-stu-id="41962-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41962-125">Target</span><span class="sxs-lookup"><span data-stu-id="41962-125">Target</span></span>  <br/> |<span data-ttu-id="41962-126">Facultatif</span><span class="sxs-lookup"><span data-stu-id="41962-126">Optional</span></span>  <br/> | <span data-ttu-id="41962-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="41962-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="41962-128">Type de chemin d’accès au fichier demandé.</span><span class="sxs-lookup"><span data-stu-id="41962-128">Type of file path requested.</span></span> <span data-ttu-id="41962-129">Les types sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="41962-129">Types include:</span></span>  <br/> <span data-ttu-id="41962-130">EdgeServer (par défaut)</span><span class="sxs-lookup"><span data-stu-id="41962-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="41962-131">MediationServer</span><span class="sxs-lookup"><span data-stu-id="41962-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="41962-132">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="41962-132">Input Types</span></span>
<span data-ttu-id="41962-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="41962-133"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="41962-134">La cmdlet Get-CcExternalCertificateFilePath n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="41962-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="41962-135">Types de retour</span><span class="sxs-lookup"><span data-stu-id="41962-135">Return Types</span></span>
<span data-ttu-id="41962-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="41962-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="41962-137">La commande renvoie un chemin d’accès au fichier.</span><span class="sxs-lookup"><span data-stu-id="41962-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="41962-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="41962-138">See also</span></span>
<span data-ttu-id="41962-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="41962-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="41962-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="41962-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  

