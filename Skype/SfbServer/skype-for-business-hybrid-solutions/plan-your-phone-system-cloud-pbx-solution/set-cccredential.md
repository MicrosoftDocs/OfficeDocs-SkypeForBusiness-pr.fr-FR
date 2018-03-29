---
title: Ensemble-CcCredential
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'L’applet de commande Set-CcCredential définit les informations du déploiement de la version Cloud Connector de Skype Entreprise.  '
ms.openlocfilehash: 7680f863ccf082ddb8359c7d3fcefc2c058b6a40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="set-cccredential"></a>Ensemble-CcCredential
 
L’applet de commande Set-CcCredential définit les informations du déploiement de la version Cloud Connector de Skype Entreprise.   
  
Avec connecteur de nuage version 2.0 et ultérieure, cette applet de commande peut également définir les informations de compte de l’administrateur de la machine virtuelle et de l’administrateur de domaine.
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant spécifie le nom et le mot de passe du compte de l’administrateur de client :
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de commande Set-CcCredential définit le nom et le mot de passe du compte de l’administrateur de client. Pour les versions antérieures à 2.0, cet administrateur doit être un administrateur Global de Office 365. Connecteur de nuage utilise ce compte pour obtenir les informations de configuration, de définir les paramètres de configuration et d’état d’application de mise à jour à la configuration de clients Office 365. Avec la version 2.0 et ultérieure, vous pouvez également utiliser cette applet de commande pour mettre à jour les mots de passe pour les comptes VmAdmin et DomainAdmin.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type de**|**Description**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Obligatoire <br/> |System.String  <br/> | Valeur du paramètre doit être « Associer », « VmAdmin » ou « DomainAdmin ». <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Set-CcCredential n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

