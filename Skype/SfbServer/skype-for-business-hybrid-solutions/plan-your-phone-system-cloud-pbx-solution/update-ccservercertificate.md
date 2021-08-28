---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: La cmdlet Update-CcServerCertificate renouvele les certificats pour les Skype Entreprise Cloud Connector Edition lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré.
ms.openlocfilehash: 1e8afb05d691a1e3e696b619c816cfc45dd26f1e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623376"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
La cmdlet Update-CcServerCertificate renouvele les certificats pour les Skype Entreprise Cloud Connector Edition lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré. 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant renouvelle les certificats pour le magasin central de gestion, le serveur de médiation et le serveur Edge lorsque les certificats sont sur le point d’expirer ou ont déjà expiré :
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant renouvelle les certificats pour le serveur de médiation et le serveur Edge lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré :
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Les certificats internes Cloud Connector délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont valides pendant deux ans après leur émission à partir d’un service d’autorité de certification. Si les certificats sont sur le point d’expirer ou ont déjà expiré, exécutez la cmdlet Update-CcServerCertificate pour renouveler les certificats. 
  
Cette commande remplace la cmdlet Renew-CcServerCertificate dans Cloud Connector 2.0 et les version ultérieures.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|Rôles  <br/> |Facultatif  <br/> |System.Array  <br/> | Tableau des rôles serveur Cloud Connector. <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Update-CcServerCertificate n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

