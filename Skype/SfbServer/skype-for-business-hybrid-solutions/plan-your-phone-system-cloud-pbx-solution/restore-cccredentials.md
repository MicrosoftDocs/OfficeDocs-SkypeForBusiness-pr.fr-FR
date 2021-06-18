---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: La cmdlet Restore Cc-Credentials restaure toutes les informations d’identification du déploiement actuel de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: b2cd35b284bcd7e49aabbaa3055c397915565d09
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824240"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
La cmdlet Restore Cc-Credentials restaure toutes les informations d’identification du déploiement actuel de la version Cloud Connector de Skype Entreprise. 
  
Cette cmdlet s’applique à Skype Entreprise, version Cloud Connector 2.1.
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Description détaillée

LRestore-CcCredentials cmdlet nettoie toutes les informations d’identification et vous invite à entrer à nouveau toutes les informations d’identification utilisées pour le déploiement actuel de Skype Entreprise Cloud Connector.
  
## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="input-types"></a>Types d’entrée

Aucun. La cmdlet Restore-CcCredentials n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retours

Aucun.
  
## <a name="example"></a>Exemple

L’exemple suivant restaure toutes les informations d’identification du déploiement Cloud Connector actuel :
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Voir aussi

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

