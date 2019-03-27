---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Retourne la version de la solution de nuage connecteur. Get-CCVersion utilisable uniquement sur l’ordinateur hôte du nuage connecteur.
ms.openlocfilehash: 5e5428e53d53eec66bafa9eb566059ef1b5a5833
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881332"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Retourne la version de la solution de nuage connecteur. Get-CCVersion utilisable uniquement sur l’ordinateur hôte du nuage connecteur.
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Description détaillée

Renvoie la version de l’appliance nuage connecteur basés sur des scripts PowerShell installés, les fichiers dans le répertoire de l’application et les ordinateurs virtuels déployés sur le serveur hôte.
  
## <a name="parameters"></a>Paramètres

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Facultatif  <br/> |System.String  <br/> |Type de version. Valeur du paramètre peut être RunningScripts, RunningBits, BackupBits ou tous. Valeur par défaut est RunningScripts.  <br/> |
   
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant indique la version de nuage connecteur du script en cours d’exécution dans votre console PowerShell ouverte :
  
```
Get-CcVersion
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant indique la version de nuage connecteur des binaires déployés sur les ordinateurs virtuels en cours d’exécution. Vous pouvez voir la version dans les noms d’ordinateur virtuel en cours d’exécution dans le Gestionnaire Hyper-v :
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Types d’entrées
<a name="Examples"> </a>

Aucun. L’applet de commande Get-CcVersion n’accepte pas la saisie de données redirigées.
  
## <a name="return-types"></a>Types de retours
<a name="Examples"> </a>

Aucun.
  
## <a name="see-also"></a>Voir aussi
<a name="Examples"> </a>

Aucun
  

