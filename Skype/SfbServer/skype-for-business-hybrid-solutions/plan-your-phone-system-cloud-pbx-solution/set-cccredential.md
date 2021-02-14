---
title: Set-CcCredential
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
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: La cmdlet Set-CcCredential définit les informations d’identification du déploiement actuel de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: 3717eb0dcaa46bb6708f40ecb7f94869f24774a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221568"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
La cmdlet Set-CcCredential définit les informations d’identification du déploiement actuel de la version Cloud Connector de Skype Entreprise. 
  
Avec Cloud Connector version 2.0 et versions ultérieures, cette cmdlet peut également définir les informations de compte pour l’administrateur de la machine virtuelle et pour l’administrateur de domaine.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant spécifie le nom de compte et le mot de passe de l’administrateur client :
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

La cmdlet Set-CcCredential définit le nom de compte et le mot de passe de l’administrateur client. Pour les publication antérieures à la version 2.0, cet administrateur doit être administrateur général. Cloud Connector utilise ce compte pour obtenir des informations de configuration, définir des paramètres de configuration et mettre à jour l’état de l’appliance sur la configuration de l’organisation Microsoft 365 ou Office 365. Avec la version 2.0 et les ultérieures, vous pouvez également utiliser cette cmdlet pour mettre à jour les mots de passe des comptes VmAdmin et DomainAdmin.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Requis <br/> |System.String  <br/> | La valeur du paramètre doit être « TenantAdmin », « VmAdmin » ou « DomainAdmin ». <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Set-CcCredential n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

