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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: La cmdlet Reset-CcCACertificate réinstalle le serveur AD du service d’autorité de certification pour créer un certificat d’autorité de certification racine.
ms.openlocfilehash: 8e0cb93e6f10f28df28213579674a6cda6e7e2cd1cf201319f77dc26be69de80
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340720"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
La cmdlet Reset-CcCACertificate réinstalle le serveur AD du service d’autorité de certification pour créer un certificat d’autorité de certification racine.
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant réinstalle le serveur AD du service d’autorité de certification pour créer un certificat d’autorité de certification racine :
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Si le certificat de l’ac racine est compromis ou n’est plus sécurisé, vous devez mettre à jour le certificat de l’ac racine et tous les certificats émis par l’ac racine. La cmdlet Reset-CcCACertificate révoque tous les certificats, désinstalle et réinstalle l’autorité de certification, puis nettoie tous les certificats liés à l’ancien service d’autorité de certification. 
  
Pour plus d’informations, voir « Les certificats d’autorité de certification ou les certificats internes délivrés à CMS, au serveur de médiation et au serveur Edge sont sur le point d’expirer ou compromis » dans La résolution des problèmes de déploiement de Cloud Connector.
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Reset-CcCACertificate n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 uniquement
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 uniquement
  
[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 et ultérieures
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 et ultérieures
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

