---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: 'L’applet de commande Get-CcCredential renvoie les informations du déploiement de la version Cloud Connector de Skype Entreprise. '
ms.openlocfilehash: c4e2d47ffc31eb7afef76c710fc93024ce2c593e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800394"
---
# <a name="get-cccredential"></a><span data-ttu-id="56577-103">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="56577-103">Get-CcCredential</span></span>
 
<span data-ttu-id="56577-104">L’applet de commande Get-CcCredential renvoie les informations du déploiement de la version Cloud Connector de Skype Entreprise. </span><span class="sxs-lookup"><span data-stu-id="56577-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="56577-105">Avec la version 2,0 et les versions ultérieures, vous pouvez également utiliser le paramètre-DisplayPassword pour afficher les mots de passe relatifs à TenantAdmin, DomainAdmin et VMAdmin.</span><span class="sxs-lookup"><span data-stu-id="56577-105">With Version 2.0 and later, you can also use the -DisplayPassword parameter to show the passwords for TenantAdmin, DomainAdmin, and VMAdmin.</span></span>
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="56577-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="56577-106">Examples</span></span>
<span data-ttu-id="56577-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="56577-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="56577-108">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="56577-108">Example 1</span></span>

<span data-ttu-id="56577-109">L’exemple suivant renvoie les informations de l’administrateur de domaine du domaine de la machine virtuelle de Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="56577-109">The following example returns the credential of the domain administrator of the Cloud Connector virtual machine domain:</span></span>
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a><span data-ttu-id="56577-110">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="56577-110">Detailed Description</span></span>
<span data-ttu-id="56577-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="56577-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="56577-p101">L’applet de commande Get-CcCredential renvoie les informations sur le type spécifique de compte. Ces informations sont spécifiées par l’administrateur qui exécute les applets de commande Register-CcAppliance et Install-CcAppliance lors du déploiement de l’appliance actuelle. </span><span class="sxs-lookup"><span data-stu-id="56577-p101">The Get-CcCredential cmdlet returns the credential information about the specified account type. These credentials are specified by the administrator who runs the Register-CcAppliance and Install-CcAppliance cmdlets when deploying the current appliance.</span></span> 
  
<span data-ttu-id="56577-p102">L’applet de commande Get-CcCredential renvoie une instance de l’objet System.Management.Automation.PSCredential. La propriété de mot de passe de l’objet retour est System.Security.SecureString.</span><span class="sxs-lookup"><span data-stu-id="56577-p102">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object. The password property of the return object is System.Security.SecureString.</span></span>
  
<span data-ttu-id="56577-116">Si vous souhaitez obtenir le texte en clair du mot de passe de l’administrateur du domaine, assurez-vous que le mot de passe est enregistré par votre compte de connexion sur le serveur hôte, puis ouvrez une console PowerShell en tant qu’administrateur et exécutez le script suivant :</span><span class="sxs-lookup"><span data-stu-id="56577-116">If you want to get the clear text of the domain administrator password, be sure the password is input by your current logon account on the host server, and then open a PowerShell console as administrator and run the below script:</span></span>
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a><span data-ttu-id="56577-117">Paramètres</span><span class="sxs-lookup"><span data-stu-id="56577-117">Parameters</span></span>
<span data-ttu-id="56577-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="56577-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="56577-119">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="56577-119">**Parameter**</span></span>|<span data-ttu-id="56577-120">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="56577-120">**Required**</span></span>|<span data-ttu-id="56577-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="56577-121">**Type**</span></span>|<span data-ttu-id="56577-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="56577-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="56577-123">AccountType</span><span class="sxs-lookup"><span data-stu-id="56577-123">AccountType</span></span> <br/> |<span data-ttu-id="56577-124">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="56577-124">Required</span></span>  <br/> | <span data-ttu-id="56577-125">System.String</span><span class="sxs-lookup"><span data-stu-id="56577-125">System.String</span></span> <br/> | <span data-ttu-id="56577-126">La valeur AccountType peut être l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="56577-126">AccountType value can be one of the following:</span></span> <br/>  <span data-ttu-id="56577-127">VmAdmin : l’administrateur local des machines virtuelles du Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="56577-127">VmAdmin: the local administrator of Cloud Connector virtual machines.</span></span> <br/>  <span data-ttu-id="56577-128">DomainAdmin : L’administrateur de domaine du domaine de machine virtuelle de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="56577-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span></span> <br/>  <span data-ttu-id="56577-129">SafeModeAdmin : SafeModeAdmin du contrôleur de domaine de machine virtuelle de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="56577-129">SafeModeAdmin: SafeModeAdmin of Cloud Connector virtual machine domain controller.</span></span> <br/>  <span data-ttu-id="56577-130">ExternalCert : Compte du certificat externe installé sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="56577-130">ExternalCert: Account of external certificate installed on the Edge Server.</span></span> <br/>  <span data-ttu-id="56577-131">TenantAdmin : Administrateur du client O365.</span><span class="sxs-lookup"><span data-stu-id="56577-131">TenantAdmin: Administrator of the O365 tenant.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="56577-132">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="56577-132">Input Types</span></span>
<span data-ttu-id="56577-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="56577-133"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="56577-p103">Aucun. L’applet de commande Get-CcCredential n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="56577-p103">None. The Get-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="56577-136">Types de retours</span><span class="sxs-lookup"><span data-stu-id="56577-136">Return Types</span></span>
<span data-ttu-id="56577-137"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="56577-137"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="56577-138">L’applet de commande Get-CcCredential renvoie une instance de l’objet System.Management.Automation.PSCredential.</span><span class="sxs-lookup"><span data-stu-id="56577-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="56577-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="56577-139">See also</span></span>
<span data-ttu-id="56577-140"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="56577-140"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="56577-141">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="56577-141">Set-CcCredential</span></span>](set-cccredential.md)
  

