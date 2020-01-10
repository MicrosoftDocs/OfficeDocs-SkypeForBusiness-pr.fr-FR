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
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: 'L’applet de connexion de restauration des informations d’identification cc : restaure toutes les informations d’identification du déploiement actuel de Skype entreprise version Cloud Connector.'
ms.openlocfilehash: adac3f0b9ca6cf392b537a9c5d0f2095021c7120
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003244"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
L’applet de connexion de restauration des informations d’identification cc : restaure toutes les informations d’identification du déploiement actuel de Skype entreprise version Cloud Connector. 
  
Cette cmdlet s’applique à Skype entreprise version Cloud Connector 2,1.
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Description détaillée

L’applet de commande Restore-CcCredentials nettoie toutes les informations d’identification et vous invite à entrer à nouveau toutes les informations d’identification utilisées pour le déploiement actuel de Skype entreprise Cloud Connector.
  
## <a name="parameters"></a>Paramètres

Aucune
  
## <a name="input-types"></a>Types d’entrées

Aucun L’applet de commande Restore-CcCredentials n’accepte pas les entrées pipelines.
  
## <a name="return-types"></a>Types de retours

Aucun.
  
## <a name="example"></a>Exemple

L’exemple suivant restaure toutes les informations d’identification du déploiement actuel du connecteur Cloud :
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Voir aussi

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

