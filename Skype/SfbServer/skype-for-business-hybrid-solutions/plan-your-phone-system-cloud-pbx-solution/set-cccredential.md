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
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'L’applet de commande Set-CcCredential définit les informations du déploiement de la version Cloud Connector de Skype Entreprise.  '
ms.openlocfilehash: bcb88f11fb78d995e6d8271593c2e09bb0b11d22
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003214"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
L’applet de commande Set-CcCredential définit les informations du déploiement de la version Cloud Connector de Skype Entreprise.   
  
Avec le Cloud Connector version 2,0 et les versions ultérieures, cette applet de contrôle peut également définir les informations de compte de l’administrateur de l’ordinateur virtuel et de l’administrateur du domaine.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant spécifie le nom et le mot de passe du compte de l’administrateur de client :
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de commande Set-CcCredential définit le nom et le mot de passe du compte de l’administrateur de client. Pour les versions antérieures à 2,0, cet administrateur doit être un administrateur général Office 365. Le Cloud Connector utilise ce compte pour obtenir les informations de configuration, définir les paramètres de configuration et mettre à jour l’état de l’appareil sur la configuration du client Office 365. Avec la version 2,0 et les versions ultérieures, vous pouvez également utiliser cette applet de cmdlet pour mettre à jour les mots de passe des comptes VmAdmin et DomainAdmin.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Obligatoire <br/> |System.String  <br/> | La valeur du paramètre doit être « TenantAdmin », « VmAdmin » ou « DomainAdmin ». <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Set-CcCredential n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

