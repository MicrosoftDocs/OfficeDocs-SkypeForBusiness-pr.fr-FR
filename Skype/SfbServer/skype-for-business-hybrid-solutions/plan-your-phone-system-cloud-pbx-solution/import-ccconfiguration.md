---
title: Importation-CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importe le Skype pour la configuration du connecteur de Cloud Business Edition à partir d’un fichier local sur le serveur hôte de connecteur de nuage.
ms.openlocfilehash: 46f4099258ce4090fa23ec980801e55f7300895f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="import-ccconfiguration"></a>Importation-CcConfiguration
 
Importe le Skype pour la configuration du connecteur de Cloud Business Edition à partir d’un fichier local sur le serveur hôte de connecteur de nuage.
  
```

Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant copie le CloudConnector.ini à partir du répertoire de la solution matérielle-logicielle de l’instance du connecteur de Cloud dans le répertoire de %SystemDrive%\ProgramData\CloudConnector :
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a>Description détaillée
<a name="Examples"> </a>

Cette applet de commande copie les CloudConnector.ini à partir du répertoire de la solution matérielle-logicielle de la solution matérielle-logicielle connecteur du Cloud dans le répertoire %SystemDrive%\ProgramData\CloudConnector. L’annuaire d’appliances est précisé en utilisant l’applet de commande Set-CcApplianceDirectory cmdlet. L’applet de commande remplace tout fichier existant dans % SystemDrive%\ProgramData\CloudConnector. Cette commande s’applique au nuage connecteur Edition version 2.0.1 et versions ultérieures.
  
## <a name="parameters"></a>Paramètres
<a name="Examples"> </a>

|**Paramètre**|**Obligatoire**|**Type de**|**Description**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Remplacer le fichier existant dans la %SystemDrive%\ProgramData\CloudConnector sans notification.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="Examples"> </a>

Aucun. La cmdlet Import-CcConfiguration n’accepte pas les entrées de pipeline.
  
## <a name="return-types"></a>Types de retours
<a name="Examples"> </a>

Aucun.
  
## <a name="see-also"></a>Voir aussi
<a name="Examples"> </a>

Exportation-CcConfiguration
  

