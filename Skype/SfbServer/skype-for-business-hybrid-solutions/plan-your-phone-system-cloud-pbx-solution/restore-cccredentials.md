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
ms.localizationpriority: medium
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: La cmdlet Restore Cc-Credentials restaure toutes les informations d’identification du déploiement Skype Entreprise Cloud Connector Edition actuel.
ms.openlocfilehash: 050c4265bff7673a7db620ff41a56a2735d6b4a7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588436"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
La cmdlet Restore Cc-Credentials restaure toutes les informations d’identification du déploiement Skype Entreprise Cloud Connector Edition actuel. 
  
Cette cmdlet s’applique Skype Entreprise Cloud Connector Edition 2.1.
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Description détaillée

LRestore-CcCredentials cmdlet nettoie toutes les informations d’identification et vous invite à entrer à nouveau toutes les informations d’identification utilisées pour le déploiement actuel Skype Entreprise Cloud Connector.
  
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
  

