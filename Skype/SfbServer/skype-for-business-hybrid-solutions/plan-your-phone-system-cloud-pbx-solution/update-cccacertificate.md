---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: L’applet de commande Update-CcCACertificate renouvelle le Skype pour certificat d’autorité de certification racine nuage connecteur édition bientôt expirer ou déjà arrivé à expiration.
ms.openlocfilehash: d123474240fb18ffcb6c1c037cc5407eb4c6c4e3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877932"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
L’applet de commande Update-CcCACertificate renouvelle le Skype pour certificat d’autorité de certification racine nuage connecteur édition bientôt expirer ou déjà arrivé à expiration. 
  
```
Update-CcCACertificate
```

## <a name="parameters"></a>Paramètres

Aucun.
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant renouvelle le certificat de l’AC racine ::   
  
```
Update-CcCACertificate 
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Le certificat de l’AC racine de Cloud Connector est valide cinq ans à partir de la date d’installation du service d’autorité de certification.
  
Si le certificat racine est proche d’expiration ou déjà expirés, exécutez l’applet de commande Update-CcCACertificate pour renouveler le certificat. Après le renouvellement du certificat racine, le serveur AD, le magasin central de gestion et le serveur Edge fournissent automatiquement de nouveaux certificats.
  
S’il existe plusieurs applications dans le même site PSTN, exécutez l’applet de commande Update-CcCACertificate dans tous les appareils du même site PSTN.
  
Comme dernière étape, exécutez Export-CcRootCertificate afin d’exporter le certificat racine vers un fichier local dans la première appliance, puis copiez et installez le certificat exporté vers vos passerelles RTC.
  
Cette commande remplace l’applet de commande renouveler-CcCACertificate dans le nuage connecteur 2.0 et versions ultérieures.
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Update-CcCACertificate n’accepte pas la saisie de données redirigées.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun. 
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

