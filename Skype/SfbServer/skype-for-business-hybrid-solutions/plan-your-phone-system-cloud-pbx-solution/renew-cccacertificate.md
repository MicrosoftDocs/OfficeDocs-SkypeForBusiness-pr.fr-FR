---
title: Renew-CcCACertificate
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
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: LRenew-CcCACertificate de la cmdlet renouvelle le certificat de l’ac racine de la version Cloud Connector de Skype Entreprise qui est sur le point d’expirer ou qui a déjà expiré. Cette commande a été modifiée Update-CcCACertificate dans Cloud Connector 2.0 et les version ultérieures.
ms.openlocfilehash: e92709cd1da0ffccd2b356000dbd2345ba56a1d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824270"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
LRenew-CcCACertificate de la cmdlet renouvelle le certificat de l’ac racine de la version Cloud Connector de Skype Entreprise qui est sur le point d’expirer ou qui a déjà expiré. Cette commande a été modifiée Update-CcCACertificate dans Cloud Connector 2.0 et les version ultérieures.
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant renouvelle le certificat d’ac racine : 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Le certificat de l’autorité de certification racine Cloud Connector est valide pendant cinq ans à partir de la date d’installation du service d’autorité de certification.
  
Si le certificat racine est sur le point d’expirer ou s’il a déjà expiré, exécutez la cmdlet Renew-CcCACertificate pour renouveler le certificat. Une fois le certificat racine renouvelé, le serveur AD, le magasin central de gestion et le serveur Edge sont automatiquement émis.
  
S’il existe plusieurs appliances dans le même site PSTN, exécutez l'Renew-CcCACertificate cmdlet dans toutes les appliances du même site PSTN.
  
Lors de la dernière étape, exécutez Export-CcRootCertificate pour exporter le certificat racine vers un fichier local dans la première appliance, puis copiez et installez le certificat exporté sur vos passerelles PSTN.
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Renew-CcCACertificate n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

