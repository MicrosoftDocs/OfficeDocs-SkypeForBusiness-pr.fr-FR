---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: L’applet de commande Set-CcApplianceDirectory définit l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichiers de déploiement sont recensés dans cet annuaire.
ms.openlocfilehash: 16c9c858d770b7d4a74c9030ebdc760f5a9f25e9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250838"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
L’applet de commande Set-CcApplianceDirectory définit l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichiers de déploiement sont recensés dans cet annuaire.
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant définit le répertoire de travail sur le serveur hôte sur c:\cloudconnector\applianceroot :
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>Paramètres
<a name="Examples"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|  Path <br/> | Obligatoire <br/> |System.String  <br/> |  Spécifie le chemin de stockage de tous les fichiers de déploiement. <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Set-CcApplianceDirectory n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucune
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Aucun
  

