---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importe la configuration de la version Cloud Connector de Skype Entreprise à partir d’un fichier local vers le serveur hôte Cloud Connector.
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799854"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Importe la configuration de la version Cloud Connector de Skype Entreprise à partir d’un fichier local vers le serveur hôte Cloud Connector.
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant copie le CloudConnector.ini du répertoire d’appliances de l’instance Cloud Connector dans le répertoire %SystemDrive%\ProgramData\CloudConnector :
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>Description détaillée
<a name="Examples"> </a>

Cette cmdlet copie le CloudConnector.ini du répertoire d’appliances de l’appliance Cloud Connector vers le répertoire %SystemDrive%\ProgramData\CloudConnector. Le répertoire de l’appliance est spécifié à l’aide Set-CcApplianceDirectory cmdlet. L’cmdlet va supprimer tout fichier existant dans %SystemDrive%\ProgramData\CloudConnector. Cette commande s’applique aux versions 2.0.1 et ultérieures de Cloud Connector.
  
## <a name="parameters"></a>Paramètres
<a name="Examples"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.  <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="Examples"> </a>

Aucun. La cmdlet Import-CcConfiguration n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="Examples"> </a>

Aucun.
  
## <a name="see-also"></a>Voir aussi
<a name="Examples"> </a>

Export-CcConfiguration
  

