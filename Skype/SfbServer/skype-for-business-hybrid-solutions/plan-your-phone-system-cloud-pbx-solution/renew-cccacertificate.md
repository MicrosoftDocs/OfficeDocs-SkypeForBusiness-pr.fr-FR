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
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: L’applet de commande Renew-CcCACertificate renouvelle le certificat de l’AC racine de Skype Entreprise, version Cloud Connector, qui est sur le point d’expirer ou qui a déjà expiré. Cette commande a été remplacée par Update-CcCACertificate dans Cloud Connector 2,0 et versions ultérieures.
ms.openlocfilehash: 493b733eab9cbd8331a93d72dc4a865f3574fbe8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003274"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
L’applet de commande Renew-CcCACertificate renouvelle le certificat de l’AC racine de Skype Entreprise, version Cloud Connector, qui est sur le point d’expirer ou qui a déjà expiré. Cette commande a été remplacée par Update-CcCACertificate dans Cloud Connector 2,0 et versions ultérieures.
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant renouvelle le certificat de l’AC racine ::   
  
```powershell
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

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

