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
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: L’applet de commande Set-CcExternalCertificateFilePath spécifie le chemin d’accès dans lequel le certificat pour le serveur de médiation ou le serveur Edge est enregistré.
ms.openlocfilehash: bc22771c20277d9de99660551864d600f06b3acc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286984"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="48ce7-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="48ce7-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="48ce7-104">L’applet de commande Set-CcExternalCertificateFilePath spécifie le chemin d’accès dans lequel le certificat pour le serveur de médiation ou le serveur Edge est enregistré.</span><span class="sxs-lookup"><span data-stu-id="48ce7-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="48ce7-p101">Ce certificat est requis pendant le déploiement ou lors de l’ajout de nouvelles appliances de la version Cloud Connector de Skype Entreprise. La commande permet également d’importer un nouveau certificat pour le serveur de médiation après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="48ce7-p101">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition. The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="48ce7-107">Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="48ce7-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="48ce7-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="48ce7-108">Examples</span></span>
<span data-ttu-id="48ce7-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="48ce7-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="48ce7-110">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="48ce7-110">Example 1</span></span>

<span data-ttu-id="48ce7-111">L'exemple suivant configure le chemin d’accès du certificat pour le serveur Edge :</span><span class="sxs-lookup"><span data-stu-id="48ce7-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="48ce7-112">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="48ce7-112">Example 2</span></span>

<span data-ttu-id="48ce7-113">L’exemple suivant configure le chemin d’accès du certificat pour le serveur de médiation :</span><span class="sxs-lookup"><span data-stu-id="48ce7-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="48ce7-114">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="48ce7-114">Example 3</span></span>

<span data-ttu-id="48ce7-115">L'exemple suivant met à jour le certificat pour le serveur de médiation :</span><span class="sxs-lookup"><span data-stu-id="48ce7-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="48ce7-116">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="48ce7-116">Detailed Description</span></span>
<span data-ttu-id="48ce7-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="48ce7-117"></span></span>

<span data-ttu-id="48ce7-118">Lors du déploiement ou de la modification de la typologie, vous devez spécifier le chemin d’accès pour le certificat du serveur Edge et éventuellement pour le certificat du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="48ce7-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="48ce7-119">Le certificat pour le serveur de médiation est requis si TLS est utilisé entre la ou les passerelle(s) et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="48ce7-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="48ce7-120">Lorsque vous déployez un dispositif de connexion Cloud et que vous souhaitez déployer le protocole TLS, vous ne pouvez spécifier que le chemin d’accès au certificat qui sera déployé sur le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="48ce7-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="48ce7-121">Cependant, si vous souhaitez mettre à jour le certificat de médiation sur une appliance déjà déployée, vous devez spécifier le chemin d’accès et le paramètre Importation.</span><span class="sxs-lookup"><span data-stu-id="48ce7-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="48ce7-122">Pour voir le chemin d’accès, utilisez l’applet de commande Get-CCExternalCertificateFilePath.</span><span class="sxs-lookup"><span data-stu-id="48ce7-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="48ce7-123">Paramètres</span><span class="sxs-lookup"><span data-stu-id="48ce7-123">Parameters</span></span>
<span data-ttu-id="48ce7-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="48ce7-124"></span></span>

|<span data-ttu-id="48ce7-125">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="48ce7-125">**Parameter**</span></span>|<span data-ttu-id="48ce7-126">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="48ce7-126">**Required**</span></span>|<span data-ttu-id="48ce7-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="48ce7-127">**Type**</span></span>|<span data-ttu-id="48ce7-128">**Description**</span><span class="sxs-lookup"><span data-stu-id="48ce7-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="48ce7-129">Cible</span><span class="sxs-lookup"><span data-stu-id="48ce7-129">Target</span></span> <br/> | <span data-ttu-id="48ce7-130">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="48ce7-130">Required</span></span> <br/> |<span data-ttu-id="48ce7-131">System.String</span><span class="sxs-lookup"><span data-stu-id="48ce7-131">System.String</span></span>  <br/> |<span data-ttu-id="48ce7-p103">Type de chemin d’accès de fichier requis. Les types comprennent :</span><span class="sxs-lookup"><span data-stu-id="48ce7-p103">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="48ce7-134">Le serveur Edge (défaut)</span><span class="sxs-lookup"><span data-stu-id="48ce7-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="48ce7-135">Le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="48ce7-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="48ce7-136">Importation</span><span class="sxs-lookup"><span data-stu-id="48ce7-136">Import</span></span>  <br/> |<span data-ttu-id="48ce7-137">Facultatif</span><span class="sxs-lookup"><span data-stu-id="48ce7-137">Optional</span></span>  <br/> |<span data-ttu-id="48ce7-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="48ce7-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="48ce7-p104">Indique que le certificat doit être importé vers le serveur de médiation. Ce paramètre n'est pas requis si vous déployez une appliance pour la première fois. Le paramètre est requis si vous souhaitez changer le certificat existant sur une version déjà déployée.</span><span class="sxs-lookup"><span data-stu-id="48ce7-p104">Indicates that the certificate must be imported to the Mediation Server. This parameter is not needed if you deploy an appliance for first time. The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="48ce7-142">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="48ce7-142">Input Types</span></span>
<span data-ttu-id="48ce7-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="48ce7-143"></span></span>

<span data-ttu-id="48ce7-144">L’applet de commande Set-CcExternalCertificateFilePath n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="48ce7-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="48ce7-145">Types de retours</span><span class="sxs-lookup"><span data-stu-id="48ce7-145">Return Types</span></span>
<span data-ttu-id="48ce7-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="48ce7-146"></span></span>

<span data-ttu-id="48ce7-147">Aucun</span><span class="sxs-lookup"><span data-stu-id="48ce7-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="48ce7-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="48ce7-148">See also</span></span>
<span data-ttu-id="48ce7-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="48ce7-149"></span></span>

[<span data-ttu-id="48ce7-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="48ce7-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

