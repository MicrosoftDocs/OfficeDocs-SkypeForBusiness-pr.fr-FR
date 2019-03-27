---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: 'L’applet de commande Get-CcCredential renvoie les informations du déploiement de la version Cloud Connector de Skype Entreprise. '
ms.openlocfilehash: 651190f31ad44e0bb2375bbf4a70951c2011e1a7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898394"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
L’applet de commande Get-CcCredential renvoie les informations du déploiement de la version Cloud Connector de Skype Entreprise.  
  
Avec la Version 2.0 et versions ultérieures, vous pouvez également utiliser le paramètre - DisplayPassword pour afficher les mots de passe pour associer, DomainAdmin et VMAdmin.
  
```
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant renvoie les informations de l’administrateur de domaine du domaine de la machine virtuelle de Cloud Connector :
  
```
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de commande Get-CcCredential renvoie les informations sur le type spécifique de compte. Ces informations sont spécifiées par l’administrateur qui exécute les applets de commande Register-CcAppliance et Install-CcAppliance lors du déploiement de l’appliance actuelle.  
  
L’applet de commande Get-CcCredential renvoie une instance de l’objet System.Management.Automation.PSCredential. La propriété de mot de passe de l’objet retour est System.Security.SecureString.
  
Si vous souhaitez obtenir le texte en clair du mot de passe de l’administrateur du domaine, assurez-vous que le mot de passe est enregistré par votre compte de connexion sur le serveur hôte, puis ouvrez une console PowerShell en tant qu’administrateur et exécutez le script suivant :
  
```
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
| AccountType <br/> |Obligatoire  <br/> | System.String <br/> | La valeur AccountType peut être l’une des valeurs suivantes : <br/>  VmAdmin : l’administrateur local d’ordinateurs virtuels de nuage connecteur. <br/>  DomainAdmin : L’administrateur de domaine du domaine de machine virtuelle de Cloud Connector. <br/>  SafeModeAdmin : SafeModeAdmin du contrôleur de domaine de machine virtuelle de Cloud Connector. <br/>  ExternalCert : Compte du certificat externe installé sur le serveur Edge. <br/>  TenantAdmin : Administrateur du client O365. <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Get-CcCredential n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

L’applet de commande Get-CcCredential renvoie une instance de l’objet System.Management.Automation.PSCredential.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

