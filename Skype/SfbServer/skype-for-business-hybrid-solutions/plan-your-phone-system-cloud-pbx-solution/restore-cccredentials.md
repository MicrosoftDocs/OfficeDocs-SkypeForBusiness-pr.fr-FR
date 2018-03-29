---
title: Restauration-CcCredentials
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: L’applet de commande Cc-informations d’identification restauration restaure toutes informations d’identification de la Skype en cours pour le déploiement de connecteur de Cloud Business Edition.
ms.openlocfilehash: 045d7f651408b1cbdbd508966da3272ac61d7c04
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="restore-cccredentials"></a>Restauration-CcCredentials
 
L’applet de commande Cc-informations d’identification restauration restaure toutes informations d’identification de la Skype en cours pour le déploiement de connecteur de Cloud Business Edition. 
  
Cette applet de commande s’applique à Skype Business Cloud connecteur Édition 2.1.
  
```

Restore-CcCredentials 
```

## <a name="detailed-description"></a>Description détaillée

L’applet de commande Restore-CcCredentials nettoie toutes informations d’identification et vous invite à entrer à nouveau toutes les informations d’identification utilisées pour le Skype en cours pour le déploiement de Cloud de Business Connector.
  
## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="input-types"></a>Types d’entrées

Aucun. L’applet de commande Restore-CcCredentials n’accepte pas les entrées de pipeline.
  
## <a name="return-types"></a>Types de retours

Aucun.
  
## <a name="example"></a>Exemple

L’exemple suivant restaure toutes informations d’identification de l’actuel déploiement de connecteur de nuage :
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Voir aussi

[Get-CcCredential](get-cccredential.md)
  
[Ensemble-CcCredential](set-cccredential.md)
  

