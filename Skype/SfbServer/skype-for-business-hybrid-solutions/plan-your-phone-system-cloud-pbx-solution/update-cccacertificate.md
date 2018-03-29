---
title: Mise à jour-CcCACertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: L’applet de commande Update-CcCACertificate renouvelle le Skype pour le certificat d’autorité de certification de racine Business Edition de connecteur de nuage qui se trouve à proximité d’expiration ou a déjà expiré.
ms.openlocfilehash: f23298f1be30ab96b3e77ff0625ff6e3b419e111
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="update-cccacertificate"></a>Mise à jour-CcCACertificate
 
L’applet de commande Update-CcCACertificate renouvelle le Skype pour le certificat d’autorité de certification de racine Business Edition de connecteur de nuage qui se trouve à proximité d’expiration ou a déjà expiré. 
  
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
  
Si le certificat racine se trouve à proximité d’expiration ou déjà expiré, exécutez l’applet de commande Update-CcCACertificate pour renouveler le certificat. Après le renouvellement du certificat racine, le serveur AD, le magasin central de gestion et le serveur Edge fournissent automatiquement de nouveaux certificats.
  
S’il y a plusieurs applications sur le même site RTPC, exécutez l’applet de commande Update-CcCACertificate dans tous les appareils du même site RTPC.
  
Comme dernière étape, exécutez Export-CcRootCertificate afin d’exporter le certificat racine vers un fichier local dans la première appliance, puis copiez et installez le certificat exporté vers vos passerelles RTC.
  
Cette commande remplace l’applet de commande de renouvellement-CcCACertificate dans le nuage lien 2.0 et versions ultérieures.
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Update-CcCACertificate n’accepte pas les entrées de pipeline.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun. 
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Réinitialisation-CcCACertificate](reset-cccacertificate.md)
  
[Renouveler-CcServerCertificate](renew-ccservercertificate.md)
  
[Exportation-CcRootCertificate](export-ccrootcertificate.md)
  

