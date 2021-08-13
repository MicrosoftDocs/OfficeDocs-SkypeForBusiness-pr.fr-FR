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
description: La cmdlet Update-CcCACertificate renouvele le certificat d Skype Entreprise Cloud Connector Edition’ac racine qui est sur le point d’expirer ou qui a déjà expiré.
ms.openlocfilehash: 640ca982cd005e9805d7214212d847edcc6856456b6995fe1ae689778da58f61
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344533"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
La cmdlet Update-CcCACertificate renouvele le certificat d Skype Entreprise Cloud Connector Edition’ac racine qui est sur le point d’expirer ou qui a déjà expiré. 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a>Paramètres

Aucun.
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant renouvelle le certificat d’ac racine : 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Le certificat de l’autorité de certification racine Cloud Connector est valide pendant cinq ans à partir de la date d’installation du service d’autorité de certification.
  
Si le certificat racine est sur le point d’expirer ou s’il a déjà expiré, exécutez la cmdlet Update-CcCACertificate pour renouveler le certificat. Une fois le certificat racine renouvelé, le serveur AD, le magasin central de gestion et le serveur Edge sont automatiquement émis.
  
S’il existe plusieurs appliances dans le même site PSTN, exécutez l'Update-CcCACertificate cmdlet dans toutes les appliances du même site PSTN.
  
Lors de la dernière étape, exécutez Export-CcRootCertificate pour exporter le certificat racine vers un fichier local dans la première appliance, puis copiez et installez le certificat exporté sur vos passerelles PSTN.
  
Cette commande remplace la cmdlet Renew-CcCACertificate dans Cloud Connector 2.0 et les version ultérieures.
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Update-CcCACertificate n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun. 
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

