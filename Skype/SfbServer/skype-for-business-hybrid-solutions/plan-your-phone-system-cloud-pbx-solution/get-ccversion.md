---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Renvoie la version de l’application Cloud Connector. Get-CCVersion ne peut être utilisé que sur l’ordinateur hôte de Cloud Connector.
ms.openlocfilehash: b002b4a9f0cae34a2cdd7b8817e86a3e4ec2eb9a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287250"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Renvoie la version de l’application Cloud Connector. Get-CCVersion ne peut être utilisé que sur l’ordinateur hôte de Cloud Connector.
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Description détaillée

Retourne la version de l’application Cloud Connector basée sur les scripts PowerShell installés, des fichiers dans l’annuaire de l’application et des machines virtuelles déployées sur le serveur hôte.
  
## <a name="parameters"></a>Paramètres

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Facultatif  <br/> |System.String  <br/> |Type de version. La valeur du paramètre peut être RunningScripts, RunningBits, BackupBits ou All. La valeur par défaut est RunningScripts.  <br/> |
   
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre la version Cloud Connector du script en cours d’exécution dans votre console PowerShell ouverte:
  
```
Get-CcVersion
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant montre la version Cloud Connector du binaire en cours d’exécution déployée sur les machines virtuelles. Vous pouvez voir la version dans les noms des machines virtuelles exécutées dans Hyper-v Manager:
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Types d’entrées
<a name="Examples"> </a>

Aucun. L’applet de commande Get-CcVersion n’accepte pas les entrées pipelines.
  
## <a name="return-types"></a>Types de retours
<a name="Examples"> </a>

Aucun.
  
## <a name="see-also"></a>Voir aussi
<a name="Examples"> </a>

Aucun
  

