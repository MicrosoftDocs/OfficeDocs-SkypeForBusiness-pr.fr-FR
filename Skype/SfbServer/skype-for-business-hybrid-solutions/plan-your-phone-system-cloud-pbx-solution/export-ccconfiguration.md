---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporte la configuration de Skype entreprise version Cloud Connector vers un fichier local sur le serveur hôte Cloud Connector Skype entreprise.
ms.openlocfilehash: cd0745081e3f069aaf58c9ffdbf24494bfb3ece1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801464"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Exporte la configuration de Skype entreprise version Cloud Connector vers un fichier local sur le serveur hôte Cloud Connector Skype entreprise.
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant définit le paramètre path pour le chemin d’accès complet au fichier et exporte les configurations vers ce fichier.
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>Description détaillée
<a name="Examples"> </a>

L’applet de connexion Export-CcConfiguration vous permet d’enregistrer la configuration du connecteur Cloud dans un fichier dans un chemin sélectionné. Cette commande a été introduite dans la version 2,0 d’édition Cloud Connector.
  
## <a name="parameters"></a>Paramètres
<a name="Examples"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| Path  <br/> |Obligatoire  <br/> |System.String  <br/> |Chemin d’accès complet du fichier dans lequel les configurations du connecteur Cloud seront stockées.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="Examples"> </a>

Aucun. L’applet de commande Export-CcConfiguration n’accepte pas les entrées pipelines.
  
## <a name="return-types"></a>Types de retours
<a name="Examples"> </a>

Aucun.
  
## <a name="see-also"></a>Voir aussi
<a name="Examples"> </a>

Import-CcConfiguration
  

