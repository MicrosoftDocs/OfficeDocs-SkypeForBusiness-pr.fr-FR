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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Renvoie la version de l’appliance Cloud Connector. Get-CCVersion ne peut être utilisé que sur l’ordinateur hôte de Cloud Connector.
ms.openlocfilehash: d3da9813fd67228f8e198cd21edce3cc187ac9359617eb660a352b38c51a95ba
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349506"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Renvoie la version de l’appliance Cloud Connector. Get-CCVersion ne peut être utilisé que sur l’ordinateur hôte de Cloud Connector.
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Description détaillée

Renvoie la version de l’appliance Cloud Connector basée sur les scripts PowerShell installés, les fichiers dans le répertoire Appliance et les machines virtuelles déployées sur le serveur hôte.
  
## <a name="parameters"></a>Paramètres

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Facultatif  <br/> |System.String  <br/> |Type de version. La valeur du paramètre peut être RunningScripts, RunningBits, BackupBits ou All. La valeur par défaut est RunningScripts.  <br/> |
   
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant illustre la version Cloud Connector du script en cours d’exécution dans votre console PowerShell ouverte :
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant montre la version Cloud Connector des binaires en cours d’exécution déployés sur les machines virtuelles. Vous pouvez voir la version dans les noms des ordinateurs virtuels en cours d’exécution dans le Gestionnaire Hyper-v :
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Types d’entrée
<a name="Examples"> </a>

Aucun. La cmdlet Get-CcVersion n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="Examples"> </a>

Aucun.
  
## <a name="see-also"></a>Voir aussi
<a name="Examples"> </a>

Aucun.
  

