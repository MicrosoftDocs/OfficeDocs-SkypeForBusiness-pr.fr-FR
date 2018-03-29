---
title: Renouveler-CcCACertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: L’applet de commande Renew-CcCACertificate renouvelle le certificat de l’AC racine de Skype Entreprise, version Cloud Connector, qui est sur le point d’expirer ou qui a déjà expiré. Cette commande a été modifiée en CcCACertificate-mise à jour dans le nuage lien 2.0 et versions ultérieures.
ms.openlocfilehash: bfcf7c69e27af8ebf83c85a8c90cc46491fbc454
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="renew-cccacertificate"></a>Renouveler-CcCACertificate
 
L’applet de commande Renew-CcCACertificate renouvelle le certificat de l’AC racine de Skype Entreprise, version Cloud Connector, qui est sur le point d’expirer ou qui a déjà expiré. Cette commande a été modifiée en CcCACertificate-mise à jour dans le nuage lien 2.0 et versions ultérieures.
  
```
Renew-CcCACertificate
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant renouvelle le certificat de l’AC racine ::   
  
```
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Le certificat de l’AC racine de Cloud Connector est valide cinq ans à partir de la date d’installation du service d’autorité de certification.
  
Si le certificat racine est sur le point d’expirer ou a déjà expiré, exécutez l’applet de commande Renew-CcCACertificate afin de renouveler le certificat. Après le renouvellement du certificat racine, le serveur AD, le magasin central de gestion et le serveur Edge fournissent automatiquement de nouveaux certificats.
  
S’il existe plusieurs appliances dans le même site RTC, exécutez l’applet de commande Renew-CcCACertificate dans toutes les appliances du même site RTC.
  
Comme dernière étape, exécutez Export-CcRootCertificate afin d’exporter le certificat racine vers un fichier local dans la première appliance, puis copiez et installez le certificat exporté vers vos passerelles RTC.
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Renew-CcCACertificate n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Réinitialisation-CcCACertificate](reset-cccacertificate.md)
  
[Renouveler-CcServerCertificate](renew-ccservercertificate.md)
  
[Exportation-CcRootCertificate](export-ccrootcertificate.md)
  

