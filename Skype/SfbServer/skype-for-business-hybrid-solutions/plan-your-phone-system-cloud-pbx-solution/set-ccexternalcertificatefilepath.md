---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: LSet-CcExternalCertificateFilePath cmdlet spécifie le chemin d’accès où le certificat pour le serveur de médiation ou le serveur Edge est stocké.
ms.openlocfilehash: 9216b82626da7160d6e1bfa8d611757321a2683a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824198"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="ee751-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="ee751-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="ee751-104">LSet-CcExternalCertificateFilePath cmdlet spécifie le chemin d’accès où le certificat pour le serveur de médiation ou le serveur Edge est stocké.</span><span class="sxs-lookup"><span data-stu-id="ee751-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="ee751-105">Ce certificat est requis lors du déploiement ou lors de l’ajout de nouvelles appliances de Skype Entreprise, version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ee751-105">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="ee751-106">La commande permet également d’importer un nouveau certificat pour le serveur de médiation après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="ee751-106">The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="ee751-107">Cette cmdlet s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="ee751-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="ee751-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="ee751-108">Examples</span></span>
<span data-ttu-id="ee751-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ee751-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="ee751-110">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="ee751-110">Example 1</span></span>

<span data-ttu-id="ee751-111">L’exemple suivant définit le chemin d’accès du certificat pour le serveur Edge :</span><span class="sxs-lookup"><span data-stu-id="ee751-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="ee751-112">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="ee751-112">Example 2</span></span>

<span data-ttu-id="ee751-113">L’exemple suivant définit le chemin d’accès du certificat pour le serveur de médiation :</span><span class="sxs-lookup"><span data-stu-id="ee751-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="ee751-114">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="ee751-114">Example 3</span></span>

<span data-ttu-id="ee751-115">L’exemple suivant met à jour le certificat pour le serveur de médiation :</span><span class="sxs-lookup"><span data-stu-id="ee751-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="ee751-116">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="ee751-116">Detailed Description</span></span>
<span data-ttu-id="ee751-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ee751-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="ee751-118">Pendant le déploiement ou lors de la modification de la topologie, vous devez spécifier le chemin d’accès pour le certificat de serveur Edge et éventuellement pour le certificat de serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="ee751-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="ee751-119">Le certificat pour le serveur de médiation est requis si TLS est utilisé entre la ou les passerelles et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="ee751-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="ee751-120">Lorsque vous déployez une appliance Cloud Connector et que vous souhaitez déployer TLS, vous ne pouvez spécifier que le chemin d’accès au certificat qui sera déployé sur le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="ee751-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="ee751-121">Toutefois, si vous souhaitez mettre à jour le certificat de médiation sur une appliance déjà déployée, vous devez spécifier le chemin d’accès et le paramètre -Import.</span><span class="sxs-lookup"><span data-stu-id="ee751-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="ee751-122">Pour voir le chemin d’accès, utilisez Get-CCExternalCertificateFilePath cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ee751-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="ee751-123">Paramètres</span><span class="sxs-lookup"><span data-stu-id="ee751-123">Parameters</span></span>
<span data-ttu-id="ee751-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ee751-124"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="ee751-125">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="ee751-125">**Parameter**</span></span>|<span data-ttu-id="ee751-126">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="ee751-126">**Required**</span></span>|<span data-ttu-id="ee751-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="ee751-127">**Type**</span></span>|<span data-ttu-id="ee751-128">**Description**</span><span class="sxs-lookup"><span data-stu-id="ee751-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ee751-129">Target</span><span class="sxs-lookup"><span data-stu-id="ee751-129">Target</span></span> <br/> | <span data-ttu-id="ee751-130">Requis</span><span class="sxs-lookup"><span data-stu-id="ee751-130">Required</span></span> <br/> |<span data-ttu-id="ee751-131">System.String</span><span class="sxs-lookup"><span data-stu-id="ee751-131">System.String</span></span>  <br/> |<span data-ttu-id="ee751-132">Type de chemin d’accès au fichier demandé.</span><span class="sxs-lookup"><span data-stu-id="ee751-132">Type of file path requested.</span></span> <span data-ttu-id="ee751-133">Les types sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="ee751-133">Types include:</span></span>  <br/> <span data-ttu-id="ee751-134">EdgeServer (par défaut)</span><span class="sxs-lookup"><span data-stu-id="ee751-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="ee751-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="ee751-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="ee751-136">Importation</span><span class="sxs-lookup"><span data-stu-id="ee751-136">Import</span></span>  <br/> |<span data-ttu-id="ee751-137">Facultatif</span><span class="sxs-lookup"><span data-stu-id="ee751-137">Optional</span></span>  <br/> |<span data-ttu-id="ee751-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="ee751-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="ee751-139">Indique que le certificat doit être importé sur le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="ee751-139">Indicates that the certificate must be imported to the Mediation Server.</span></span> <span data-ttu-id="ee751-140">Ce paramètre n’est pas nécessaire si vous déployez une appliance pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="ee751-140">This parameter is not needed if you deploy an appliance for first time.</span></span> <span data-ttu-id="ee751-141">Le paramètre est obligatoire si vous souhaitez modifier le certificat existant sur une version déjà déployée.</span><span class="sxs-lookup"><span data-stu-id="ee751-141">The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ee751-142">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="ee751-142">Input Types</span></span>
<span data-ttu-id="ee751-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ee751-143"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="ee751-144">La cmdlet Set-CcExternalCertificateFilePath n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="ee751-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ee751-145">Types de retour</span><span class="sxs-lookup"><span data-stu-id="ee751-145">Return Types</span></span>
<span data-ttu-id="ee751-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ee751-146"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="ee751-147">Aucun</span><span class="sxs-lookup"><span data-stu-id="ee751-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ee751-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee751-148">See also</span></span>
<span data-ttu-id="ee751-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ee751-149"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="ee751-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="ee751-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

