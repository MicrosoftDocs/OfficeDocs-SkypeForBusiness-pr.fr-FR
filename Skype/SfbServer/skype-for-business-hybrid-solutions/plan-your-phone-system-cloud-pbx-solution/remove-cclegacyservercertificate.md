---
title: Supprimer-CcLegacyServerCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: L’applet de commande Remove-CcLegacyServerCertificate supprime les certificats de l’ancien serveur sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des applets de commande Renew-CcCACertificate ou Renew CcServerCertificate.
ms.openlocfilehash: f23a753df1a5c9f81b81bc0f1d7d33c01020b489
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="remove-cclegacyservercertificate"></a>Supprimer-CcLegacyServerCertificate
 
L’applet de commande Remove-CcLegacyServerCertificate supprime les certificats de l’ancien serveur sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des applets de commande Renew-CcCACertificate ou Renew CcServerCertificate.
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant supprime les anciens certificats délivrés pour le magasin central de gestion, le serveur de médiation et le serveur Edge après le renouvellement des certificats :
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant supprime les certificats délivrés pour le serveur de médiation et le serveur Edge après le renouvellement des certificats :  
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 

```

## <a name="parameters"></a>Paramètres
<a name="Examples"> </a>

|**Paramètre**|**Obligatoire**|**Type de**|**Description**|
|:-----|:-----|:-----|:-----|
| Rôles <br/> |Facultatif  <br/> |System.Array  <br/> | Série de rôles des serveurs de Cloud Connector. <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Remove-CcLegacyServerCertificate n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Renouveler-CcServerCertificate](renew-ccservercertificate.md)
  
[Réinitialisation-CcCACertificate](reset-cccacertificate.md)
  
[Renouveler-CcCACertificate](renew-cccacertificate.md)
  
[Mise à jour-CcCACertificate](update-cccacertificate.md)
  

