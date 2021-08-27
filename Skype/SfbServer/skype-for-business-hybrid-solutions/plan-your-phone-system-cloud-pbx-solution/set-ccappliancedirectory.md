---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: La cmdlet Set-CcApplianceDirectory définit le répertoire de travail sur Skype Entreprise Cloud Connector Edition serveur hôte. Tous les fichiers de déploiement sont stockés dans ce répertoire.
ms.openlocfilehash: 0f64fbb52cd12020104e98051564379d1fbc4985
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617666"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
La cmdlet Set-CcApplianceDirectory définit le répertoire de travail sur Skype Entreprise Cloud Connector Edition serveur hôte. Tous les fichiers de déploiement sont stockés dans ce répertoire.
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant définit le répertoire de travail sur le serveur hôte sur c:\cloudconnector\applianceroot :
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>Paramètres
<a name="Examples"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| Path <br/> | Requis <br/> |System.String  <br/> | Spécifie le chemin d’accès où sont stockés tous les fichiers de déploiement. <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Set-CcApplianceDirectory n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Aucun
  

