---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: L’applet de commande Remove-CcLegacyServerCertificate supprime les certificats de l’ancien serveur sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des applets de commande Renew-CcCACertificate ou Renew CcServerCertificate.
ms.openlocfilehash: f22a57a3a366c621a1c035881c886190055b15e6
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003284"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
L’applet de commande Remove-CcLegacyServerCertificate supprime les certificats de l’ancien serveur sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des applets de commande Renew-CcCACertificate ou Renew CcServerCertificate.
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant supprime les anciens certificats délivrés pour le magasin central de gestion, le serveur de médiation et le serveur Edge après le renouvellement des certificats :
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant supprime les certificats délivrés pour le serveur de médiation et le serveur Edge après le renouvellement des certificats :  
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>Paramètres
<a name="Examples"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| Rôles <br/> |Facultatif  <br/> |System.Array  <br/> | Série de rôles des serveurs de Cloud Connector. <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Remove-CcLegacyServerCertificate n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

