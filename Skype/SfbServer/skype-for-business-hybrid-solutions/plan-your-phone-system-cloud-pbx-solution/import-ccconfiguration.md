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
description: Importe la configuration Skype Entreprise Cloud Connector Edition d’un fichier local vers le serveur hôte Cloud Connector.
ms.openlocfilehash: 4ac32f460c2c493f5d78f1a38adcdd0728763bbbcf57a67470823fb88d407d09
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349496"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Importe la configuration Skype Entreprise Cloud Connector Edition d’un fichier local vers le serveur hôte Cloud Connector.
  
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
  

