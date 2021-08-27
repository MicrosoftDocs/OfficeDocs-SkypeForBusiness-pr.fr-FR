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
ms.localizationpriority: medium
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: LGet-CcCredential cmdlet renvoie les informations d’identification du déploiement Skype Entreprise Cloud Connector Edition actuel.
ms.openlocfilehash: 158f6e35f667410a0070e2f7030932bd6fc35ade
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596358"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
LGet-CcCredential cmdlet renvoie les informations d’identification du déploiement Skype Entreprise Cloud Connector Edition actuel. 
  
Avec les versions 2.0 et ultérieures, vous pouvez également utiliser le paramètre -DisplayPassword pour afficher les mots de passe pour TenantAdmin, DomainAdmin et VMAdmin.
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant renvoie les informations d’identification de l’administrateur de domaine du domaine de la machine virtuelle Cloud Connector :
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

La cmdlet Get-CcCredential renvoie les informations d’identification sur le type de compte spécifié. Ces informations d’identification sont spécifiées par l’administrateur qui exécute les cmdlets Register-CcAppliance et Install-CcAppliance lors du déploiement de l’appliance actuelle. 
  
LGet-CcCredential cmdlet renvoie une instance de l’objet System.Management.Automation.PSCredential. La propriété de mot de passe de l’objet de retour est System.Security.SecureString.
  
Si vous souhaitez obtenir le texte clair du mot de passe de l’administrateur de domaine, assurez-vous que le mot de passe est entrée par votre compte d’ouverture de messagerie actuel sur le serveur hôte, puis ouvrez une console PowerShell en tant qu’administrateur et exécutez le script ci-dessous :
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |Requis  <br/> | System.String <br/> | La valeur AccountType peut être l’une des suivantes : <br/>  VmAdmin : administrateur local des machines virtuelles Cloud Connector. <br/>  DomainAdmin : administrateur de domaine du domaine de machine virtuelle Cloud Connector. <br/>  SafeModeAdmin : SafeModeAdmin du contrôleur de domaine de machine virtuelle Cloud Connector. <br/>  ExternalCert : compte de certificat externe installé sur le serveur Edge. <br/>  TenantAdmin : administrateur du client O365. <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Get-CcCredential n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

LGet-CcCredential cmdlet renvoie une instance de l’objet System.Management.Automation.PSCredential.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

