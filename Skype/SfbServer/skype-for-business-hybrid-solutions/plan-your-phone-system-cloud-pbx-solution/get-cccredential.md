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
description: LGet-CcCredential cmdlet renvoie les informations d’identification du déploiement actuel de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: c4e2d47ffc31eb7afef76c710fc93024ce2c593e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800394"
---
# <a name="get-cccredential"></a><span data-ttu-id="7d17b-103">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="7d17b-103">Get-CcCredential</span></span>
 
<span data-ttu-id="7d17b-104">LGet-CcCredential cmdlet renvoie les informations d’identification du déploiement actuel de la version Cloud Connector de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="7d17b-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="7d17b-105">Avec les versions 2.0 et ultérieures, vous pouvez également utiliser le paramètre -DisplayPassword pour afficher les mots de passe pour TenantAdmin, DomainAdmin et VMAdmin.</span><span class="sxs-lookup"><span data-stu-id="7d17b-105">With Version 2.0 and later, you can also use the -DisplayPassword parameter to show the passwords for TenantAdmin, DomainAdmin, and VMAdmin.</span></span>
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="7d17b-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="7d17b-106">Examples</span></span>
<span data-ttu-id="7d17b-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7d17b-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="7d17b-108">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="7d17b-108">Example 1</span></span>

<span data-ttu-id="7d17b-109">L’exemple suivant renvoie les informations d’identification de l’administrateur de domaine du domaine de la machine virtuelle Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="7d17b-109">The following example returns the credential of the domain administrator of the Cloud Connector virtual machine domain:</span></span>
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a><span data-ttu-id="7d17b-110">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="7d17b-110">Detailed Description</span></span>
<span data-ttu-id="7d17b-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7d17b-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="7d17b-112">La cmdlet Get-CcCredential renvoie les informations d’identification sur le type de compte spécifié.</span><span class="sxs-lookup"><span data-stu-id="7d17b-112">The Get-CcCredential cmdlet returns the credential information about the specified account type.</span></span> <span data-ttu-id="7d17b-113">Ces informations d’identification sont spécifiées par l’administrateur qui exécute les cmdlets Register-CcAppliance et Install-CcAppliance lors du déploiement de l’appliance actuelle.</span><span class="sxs-lookup"><span data-stu-id="7d17b-113">These credentials are specified by the administrator who runs the Register-CcAppliance and Install-CcAppliance cmdlets when deploying the current appliance.</span></span> 
  
<span data-ttu-id="7d17b-114">LGet-CcCredential cmdlet renvoie une instance de l’objet System.Management.Automation.PSCredential.</span><span class="sxs-lookup"><span data-stu-id="7d17b-114">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span> <span data-ttu-id="7d17b-115">La propriété de mot de passe de l’objet de retour est System.Security.SecureString.</span><span class="sxs-lookup"><span data-stu-id="7d17b-115">The password property of the return object is System.Security.SecureString.</span></span>
  
<span data-ttu-id="7d17b-116">Si vous souhaitez obtenir le texte clair du mot de passe de l’administrateur de domaine, assurez-vous que le mot de passe est entrée par votre compte d’ouverture de messagerie actuel sur le serveur hôte, puis ouvrez une console PowerShell en tant qu’administrateur et exécutez le script ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="7d17b-116">If you want to get the clear text of the domain administrator password, be sure the password is input by your current logon account on the host server, and then open a PowerShell console as administrator and run the below script:</span></span>
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a><span data-ttu-id="7d17b-117">Paramètres</span><span class="sxs-lookup"><span data-stu-id="7d17b-117">Parameters</span></span>
<span data-ttu-id="7d17b-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7d17b-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="7d17b-119">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="7d17b-119">**Parameter**</span></span>|<span data-ttu-id="7d17b-120">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="7d17b-120">**Required**</span></span>|<span data-ttu-id="7d17b-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="7d17b-121">**Type**</span></span>|<span data-ttu-id="7d17b-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="7d17b-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7d17b-123">AccountType</span><span class="sxs-lookup"><span data-stu-id="7d17b-123">AccountType</span></span> <br/> |<span data-ttu-id="7d17b-124">Requis</span><span class="sxs-lookup"><span data-stu-id="7d17b-124">Required</span></span>  <br/> | <span data-ttu-id="7d17b-125">System.String</span><span class="sxs-lookup"><span data-stu-id="7d17b-125">System.String</span></span> <br/> | <span data-ttu-id="7d17b-126">La valeur AccountType peut être l’une des suivantes :</span><span class="sxs-lookup"><span data-stu-id="7d17b-126">AccountType value can be one of the following:</span></span> <br/>  <span data-ttu-id="7d17b-127">VmAdmin : administrateur local des machines virtuelles Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7d17b-127">VmAdmin: the local administrator of Cloud Connector virtual machines.</span></span> <br/>  <span data-ttu-id="7d17b-128">DomainAdmin : administrateur de domaine du domaine de machine virtuelle Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7d17b-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span></span> <br/>  <span data-ttu-id="7d17b-129">SafeModeAdmin : SafeModeAdmin du contrôleur de domaine de machine virtuelle Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7d17b-129">SafeModeAdmin: SafeModeAdmin of Cloud Connector virtual machine domain controller.</span></span> <br/>  <span data-ttu-id="7d17b-130">ExternalCert : compte de certificat externe installé sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="7d17b-130">ExternalCert: Account of external certificate installed on the Edge Server.</span></span> <br/>  <span data-ttu-id="7d17b-131">TenantAdmin : administrateur du client O365.</span><span class="sxs-lookup"><span data-stu-id="7d17b-131">TenantAdmin: Administrator of the O365 tenant.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="7d17b-132">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="7d17b-132">Input Types</span></span>
<span data-ttu-id="7d17b-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7d17b-133"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="7d17b-134">Aucun.</span><span class="sxs-lookup"><span data-stu-id="7d17b-134">None.</span></span> <span data-ttu-id="7d17b-135">La cmdlet Get-CcCredential n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="7d17b-135">The Get-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7d17b-136">Types de retour</span><span class="sxs-lookup"><span data-stu-id="7d17b-136">Return Types</span></span>
<span data-ttu-id="7d17b-137"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7d17b-137"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="7d17b-138">LGet-CcCredential cmdlet renvoie une instance de l’objet System.Management.Automation.PSCredential.</span><span class="sxs-lookup"><span data-stu-id="7d17b-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7d17b-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7d17b-139">See also</span></span>
<span data-ttu-id="7d17b-140"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7d17b-140"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="7d17b-141">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="7d17b-141">Set-CcCredential</span></span>](set-cccredential.md)
  

