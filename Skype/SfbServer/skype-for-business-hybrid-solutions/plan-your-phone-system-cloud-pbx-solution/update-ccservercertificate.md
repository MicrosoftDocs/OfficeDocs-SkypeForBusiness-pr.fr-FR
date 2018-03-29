---
title: Mise à jour-CcServerCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: L’applet de commande Update-CcServerCertificate renouvelle les certificats pour Skype pour connecteur de nuage professionnel lorsqu’elles sont bientôt expirer ou a déjà expiré.
ms.openlocfilehash: 1971f754a7c850d72a3d870e7181738267c99101
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="update-ccservercertificate"></a>Mise à jour-CcServerCertificate
 
L’applet de commande Update-CcServerCertificate renouvelle les certificats pour Skype pour connecteur de nuage professionnel lorsqu’elles sont bientôt expirer ou a déjà expiré. 
  
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

Connecteur de nuage émis des certificats internes pour le magasin Central de gestion, serveur de médiation et serveur de transport Edge sont valides pendant deux ans après que qu’ils sont émis à partir d’un service de l’autorité de certification. Si les certificats sont près d’expiration ou déjà expiré, exécutez l’applet de commande Update-CcServerCertificate pour renouveler les certificats. 
  
Cette commande remplace l’applet de commande de renouvellement-CcServerCertificate dans le nuage lien 2.0 et versions ultérieures.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type de**|**Description**|
|:-----|:-----|:-----|:-----|
|Rôles  <br/> |Facultatif  <br/> |System.Array  <br/> | Série de rôles des serveurs de Cloud Connector. <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Update-CcServerCertificate n’accepte pas les entrées de pipeline.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Réinitialisation-CcCACertificate](reset-cccacertificate.md)
  
[Renouveler-CcServerCertificate](renew-ccservercertificate.md)
  
[Exportation-CcRootCertificate](export-ccrootcertificate.md)
  

