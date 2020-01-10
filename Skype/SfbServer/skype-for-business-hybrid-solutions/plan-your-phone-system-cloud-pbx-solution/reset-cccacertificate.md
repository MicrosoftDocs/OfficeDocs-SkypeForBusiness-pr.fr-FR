---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: L’applet de commande Reset-CcCACertificate réinstalle le serveur AD de service d’autorité de certification afin de créer un nouveau certificat de l’AC racine.
ms.openlocfilehash: 50c3b1afc29503b2b292ce578ea01b03aeeba368
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003254"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
L’applet de commande Reset-CcCACertificate réinstalle le serveur AD de service d’autorité de certification afin de créer un nouveau certificat de l’AC racine.
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant réinstalle le serveur AD de service d’autorité de certification afin de créer un nouveau certificat de l’AC racine.
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Si le certificat de l’AC est compromis ou plus sécurisé, vous devez mettre à jour le certificat de l’AC racine ainsi que tous les certificats délivrés par l’AC racine. L’applet de commande Reset-CcCACertificate révoque tous les certificats, désinstalle et réinstalle l’autorité de certification puis nettoie tous les certificats liés à l’ancien service d’autorité de certification. 
  
Pour plus d’informations, reportez-vous à la section « certificats d’autorité de certification ou certificats internes émis au SSFM, serveur de médiation et serveur Edge » est proche de la date d’expiration ou de la compromission» dans résolution des problèmes de déploiement de votre Cloud Connector.
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Reset-CcCACertificate n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Renouveler-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 uniquement
  
[Renouveler-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 uniquement
  
[Update-CcCACertificate](update-cccacertificate.md) Version 2,0 et versions ultérieures
  
[Renouveler-CcServerCertificate](renew-ccservercertificate.md) Version 2,0 et versions ultérieures
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

