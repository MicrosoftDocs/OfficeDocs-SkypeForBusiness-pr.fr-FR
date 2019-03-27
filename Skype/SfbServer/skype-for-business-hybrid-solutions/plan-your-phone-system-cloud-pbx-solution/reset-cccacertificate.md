---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: L’applet de commande Reset-CcCACertificate réinstalle le serveur AD de service d’autorité de certification afin de créer un nouveau certificat de l’AC racine.
ms.openlocfilehash: 1ed9aaa8b7caf1edd5324d082094fa247c858853
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898535"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
L’applet de commande Reset-CcCACertificate réinstalle le serveur AD de service d’autorité de certification afin de créer un nouveau certificat de l’AC racine.
  
```
Reset-CcCACertificate
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant réinstalle le serveur AD de service d’autorité de certification afin de créer un nouveau certificat de l’AC racine.
  
```
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Si le certificat de l’AC est compromis ou plus sécurisé, vous devez mettre à jour le certificat de l’AC racine ainsi que tous les certificats délivrés par l’AC racine. L’applet de commande Reset-CcCACertificate révoque tous les certificats, désinstalle et réinstalle l’autorité de certification puis nettoie tous les certificats liés à l’ancien service d’autorité de certification. 
  
Pour plus d’informations, voir « Certificat certificats d’autorité internes émis à CMS, serveur de médiation et serveur de transport Edge sont bientôt expirer ou les certificats sont compromises » dans le dépannage de votre déploiement en nuage connecteur.
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Reset-CcCACertificate n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[CcCACertificate renouveler](renew-cccacertificate.md) Version 1.4.2
  
[CcServerCertificate renouveler](renew-ccservercertificate.md) Version 1.4.2
  
[Mise à jour-CcCACertificate](update-cccacertificate.md) Version 2.0 et versions ultérieure
  
[CcServerCertificate renouveler](renew-ccservercertificate.md) Version 2.0 et versions ultérieure
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

