---
title: Get-CcVersion
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Retourne la version de la solution matérielle-logicielle connecteur de nuage. Get-CCVersion est réservée sur l’ordinateur hôte du connecteur de nuage.
ms.openlocfilehash: 8391264603a73e3f594122dcdd2eb62b9ba19978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Retourne la version de la solution matérielle-logicielle connecteur de nuage. Get-CCVersion est réservée sur l’ordinateur hôte du connecteur de nuage.
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Description détaillée

Retourne la version de la solution matérielle-logicielle de connecteur de nuage reposant sur des scripts PowerShell installés, les fichiers dans le répertoire de la solution matérielle-logicielle et les ordinateurs virtuels déployés sur le serveur hôte.
  
## <a name="parameters"></a>Paramètres

|**Paramètre**|**Obligatoire**|**Type de**|**Description**|
|:-----|:-----|:-----|:-----|
|TypeDeVersion  <br/> |Facultatif  <br/> |System.String  <br/> |Type de version. Valeur du paramètre peut être RunningScripts, RunningBits, BackupBits ou tous. Valeur par défaut est RunningScripts.  <br/> |
   
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre la version de connecteur de nuage du script en cours d’exécution dans votre console PowerShell ouverte :
  
```
Get-CcVersion
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant montre la version de connecteur de nuage des binaires déployés sur les ordinateurs virtuels en cours d’exécution. Vous pouvez voir la version dans les noms de machine virtuelle en cours d’exécution dans le Gestionnaire Hyper-v :
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Types d’entrées
<a name="Examples"> </a>

Aucun. L’applet de commande Get-CcVersion n’accepte pas les entrées de pipeline.
  
## <a name="return-types"></a>Types de retours
<a name="Examples"> </a>

Aucun.
  
## <a name="see-also"></a>Voir aussi
<a name="Examples"> </a>

Aucun
  

