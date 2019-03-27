---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: L’applet de commande Renew-CcServerCertificate renouvelle les certificats pour la version Cloud Connector de Skype Entreprise lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré. Cette commande a été modifiée pour la mise à jour-CcServerCertificate dans le nuage connecteur 2.0 et versions ultérieures.
ms.openlocfilehash: ad366bdf7f6c27552a8e7621ee9244762dd864eb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894816"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
L’applet de commande Renew-CcServerCertificate renouvelle les certificats pour la version Cloud Connector de Skype Entreprise lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré. Cette commande a été modifiée pour la mise à jour-CcServerCertificate dans le nuage connecteur 2.0 et versions ultérieures. 
  
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

Nuage connecteur internes certificats émis vers le magasin Central de gestion, le serveur de médiation et le serveur de périphérie sont valides pour les deux ans après que qu’ils sont émis à partir d’un service de l’autorité de certification. Si les certificats sont sur le point d’expirer ou qu’ils ont déjà expiré, exécutez l’applet de commande Renew-CcServerCertificate afin de les renouveler. 
  
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
  

