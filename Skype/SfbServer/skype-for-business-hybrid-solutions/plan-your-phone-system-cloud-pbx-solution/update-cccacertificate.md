---
title: Update-CcCACertificate
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
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: L’applet de connexion Update-CcCACertificate renouvelle le certificat de l’autorité de certification racine Skype entreprise Cloud Connector qui est proche de l’expiration ou qui est déjà expiré.
ms.openlocfilehash: 9a99e80e166b7c8624867594fa02243d9d70537e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824118"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
L’applet de connexion Update-CcCACertificate renouvelle le certificat de l’autorité de certification racine Skype entreprise Cloud Connector qui est proche de l’expiration ou qui est déjà expiré. 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a>Paramètres

Aucun.
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant renouvelle le certificat de l’AC racine ::   
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Le certificat de l’AC racine de Cloud Connector est valide cinq ans à partir de la date d’installation du service d’autorité de certification.
  
Si le certificat racine est proche de l’expiration ou a déjà expiré, exécutez l’applet de certification Update-CcCACertificate pour renouveler le certificat. Après le renouvellement du certificat racine, le serveur AD, le magasin central de gestion et le serveur Edge fournissent automatiquement de nouveaux certificats.
  
S’il existe plusieurs applications sur le même site RTC, exécutez l’applet de l’applet de mise à jour-CcCACertificate dans tous les appareils du même site PSTN.
  
Comme dernière étape, exécutez Export-CcRootCertificate afin d’exporter le certificat racine vers un fichier local dans la première appliance, puis copiez et installez le certificat exporté vers vos passerelles RTC.
  
Cette commande remplace l’applet de commande Renew-CcCACertificate dans Cloud Connector 2,0 et les versions ultérieures.
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Update-CcCACertificate n’accepte pas les entrées pipelines.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun. 
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

