---
title: Import-CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importe le Skype pour la configuration du connecteur du nuage Professionnel à partir d’un fichier local vers le serveur hôte nuage connecteur.
ms.openlocfilehash: c48ce321b4cf40626cc67de8ff32107bf08e5443
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569725"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Importe le Skype pour la configuration du connecteur du nuage Professionnel à partir d’un fichier local vers le serveur hôte nuage connecteur.
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant copie la CloudConnector.ini à partir du répertoire d’application de l’instance du nuage connecteur au répertoire %SystemDrive%\ProgramData\CloudConnector :
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a>Description détaillée
<a name="Examples"> </a>

Cette applet de commande copie la CloudConnector.ini à partir du répertoire d’application de la solution de nuage connecteur dans le répertoire %SystemDrive%\ProgramData\CloudConnector. L’annuaire d’appliances est précisé en utilisant l’applet de commande Set-CcApplianceDirectory cmdlet. L’applet de commande remplace tous les fichiers existants dans % SystemDrive%\ProgramData\CloudConnector. Cette commande s’applique à nuage connecteur Edition version 2.0.1 et versions ultérieures.
  
## <a name="parameters"></a>Paramètres
<a name="Examples"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Remplacer un fichier existant dans %SystemDrive%\ProgramData\CloudConnector sans notification.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="Examples"> </a>

Aucun. La cmdlet Import-CcConfiguration n’accepte pas la saisie de données redirigées.
  
## <a name="return-types"></a>Types de retours
<a name="Examples"> </a>

Aucun.
  
## <a name="see-also"></a>Voir aussi
<a name="Examples"> </a>

Export-CcConfiguration
  

