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
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Permet d’importer la configuration de Skype entreprise version Cloud Connector à partir d’un fichier local sur le serveur hôte du Cloud Connector.
ms.openlocfilehash: c72a72351ecb6936832bc5d6a2493c5fa8dfe324
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003334"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Permet d’importer la configuration de Skype entreprise version Cloud Connector à partir d’un fichier local sur le serveur hôte du Cloud Connector.
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

Dans l’exemple suivant, la CloudConnector. ini est copiée à partir de l’annuaire d’application de l’instance Cloud Connector vers l’annuaire%SystemDrive%\ProgramData\CloudConnector :
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>Description détaillée
<a name="Examples"> </a>

Cette applet de connexion copie le CloudConnector. ini du répertoire de l’application Cloud Connector vers le répertoire%SystemDrive%\ProgramData\CloudConnector. L’annuaire d’appliances est précisé en utilisant l’applet de commande Set-CcApplianceDirectory cmdlet. L’applet de lecture écrasera tout fichier existant dans%SystemDrive%\ProgramData\CloudConnector. Cette commande s’applique à la version 2.0.1 et versions ultérieures de l’édition Cloud Connector.
  
## <a name="parameters"></a>Paramètres
<a name="Examples"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Remplacez le fichier existant dans%SystemDrive%\ProgramData\CloudConnector sans notification.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="Examples"> </a>

Aucun. L’applet de commande Import-CcConfiguration n’accepte pas les entrées pipelines.
  
## <a name="return-types"></a>Types de retours
<a name="Examples"> </a>

Aucun.
  
## <a name="see-also"></a>Voir aussi
<a name="Examples"> </a>

Export-CcConfiguration
  

