---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: LRenew-CcServerCertificate cmdlet renouvelle les certificats pour skype entreprise, version Cloud Connector lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré. Cette commande a été modifiée Update-CcServerCertificate dans Cloud Connector 2.0 et les version ultérieures.
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824260"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
LRenew-CcServerCertificate cmdlet renouvelle les certificats pour skype entreprise, version Cloud Connector lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré. Cette commande a été modifiée Update-CcServerCertificate dans Cloud Connector 2.0 et les version ultérieures. 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant renouvelle les certificats pour le magasin central de gestion, le serveur de médiation et le serveur Edge lorsque les certificats sont sur le point d’expirer ou ont déjà expiré :
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant renouvelle les certificats pour le serveur de médiation et le serveur Edge lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré :
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Les certificats internes Cloud Connector délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont valides pendant deux ans après leur émission à partir d’un service d’autorité de certification. Si les certificats sont sur le point d’expirer ou ont déjà expiré, exécutez la cmdlet Renew-CcServerCertificate pour renouveler les certificats. 
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|Rôles  <br/> |Facultatif  <br/> |System.Array  <br/> | Tableau des rôles serveur Cloud Connector. <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Renew-CcServerCertificate n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

