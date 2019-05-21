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
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: L’applet de commande Renew-CcServerCertificate renouvelle les certificats pour la version Cloud Connector de Skype Entreprise lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré. Cette commande a été remplacée par Update-CcServerCertificate dans Cloud Connector 2,0 et versions ultérieures.
ms.openlocfilehash: 611eeb648c88411afa5d74cc7564703a5e37e9bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287061"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
L’applet de commande Renew-CcServerCertificate renouvelle les certificats pour la version Cloud Connector de Skype Entreprise lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré. Cette commande a été remplacée par Update-CcServerCertificate dans Cloud Connector 2,0 et versions ultérieures. 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant renouvelle les certificats pour le magasin central de gestion, le serveur de médiation et le serveur Edge lorsque les certificats sont sur le point d’expirer ou qu’ils ont déjà expiré :
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant renouvelle les certificats pour le serveur de médiation et le serveur Edge lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré :
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Les certificats internes du Cloud Connector émis sur le magasin de gestion central, le serveur de médiation et le serveur Edge sont valides pendant deux ans après leur émission par le biais d’un service d’autorité de certification. Si les certificats sont sur le point d’expirer ou qu’ils ont déjà expiré, exécutez l’applet de commande Renew-CcServerCertificate afin de les renouveler. 
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|Rôles  <br/> |Facultatif  <br/> |System.Array  <br/> | Série de rôles des serveurs de Cloud Connector. <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Renew-CcServerCertificate n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

