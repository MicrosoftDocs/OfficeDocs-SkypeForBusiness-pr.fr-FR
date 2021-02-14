---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: LRemove-CcLegacyServerCertificate cmdlet supprime les certificats de serveur hérités sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.
ms.openlocfilehash: f3fe17e8c6c559d1a2c8ab14543807f82c4b6813
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824280"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
LRemove-CcLegacyServerCertificate cmdlet supprime les certificats de serveur hérités sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant supprime les certificats hérités émis pour le magasin central de gestion, le serveur de médiation et le serveur Edge après avoir renouvelé les certificats :
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant supprime les certificats émis pour le serveur de médiation et le serveur Edge après avoir renouvelé les certificats : 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>Paramètres
<a name="Examples"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| Rôles <br/> |Facultatif  <br/> |System.Array  <br/> | Tableau des rôles serveur Cloud Connector. <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Remove-CcLegacyServerCertificate n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

