---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: L’applet de commande Update-CcServerCertificate renouvelle les certificats pour Skype pour l’édition de connecteur Business Cloud lorsqu’ils sont bientôt expirer ou déjà arrivé à expiration.
ms.openlocfilehash: 92f914db04d3a3621624efd5b6a72e249b3eb19e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899658"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
L’applet de commande Update-CcServerCertificate renouvelle les certificats pour Skype pour l’édition de connecteur Business Cloud lorsqu’ils sont bientôt expirer ou déjà arrivé à expiration. 
  
```
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant renouvelle les certificats pour le magasin central de gestion, le serveur de médiation et le serveur Edge lorsque les certificats sont sur le point d’expirer ou qu’ils ont déjà expiré :
  
```
Update-CcServerCertificate
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant renouvelle les certificats pour le serveur de médiation et le serveur Edge lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré :
  
```
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Nuage connecteur internes certificats émis vers le magasin Central de gestion, le serveur de médiation et le serveur de périphérie sont valides pour les deux ans après que qu’ils sont émis à partir d’un service de l’autorité de certification. Si les certificats sont près d’expiration ou déjà expirés, exécutez l’applet de commande Update-CcServerCertificate pour renouveler les certificats. 
  
Cette commande remplace l’applet de commande renouveler-CcServerCertificate dans le nuage connecteur 2.0 et versions ultérieures.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|Rôles  <br/> |Facultatif  <br/> |System.Array  <br/> | Série de rôles des serveurs de Cloud Connector. <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Update-CcServerCertificate n’accepte pas la saisie de données redirigées.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

