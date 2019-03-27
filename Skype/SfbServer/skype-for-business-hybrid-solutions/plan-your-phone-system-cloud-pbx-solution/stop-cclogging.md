---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: L’applet de commande Stop-CcLogging interrompt la création de journaux d'appels entrants et sortants pour une appliance de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: eaccde49421cd22e32b23b89d8b5ea42dd073912
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879622"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
L’applet de commande Stop-CcLogging interrompt la création de journaux d'appels entrants et sortants pour une appliance de la version Cloud Connector de Skype Entreprise.
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant interrompt la création de journaux d'appels entrants et sortants :  
  
```
Stop-CcLogging
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant interrompt la création de journaux d'appels entrants et sortants et nettoie les fichiers en mémoire :
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de commande Stop-CcLogging interrompt la création de journaux d'appels entrants et sortants sur une appliance. Par défaut, les journaux sont automatiquement interrompus après quatre heures.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | Facultatif <br/> | System.Management.Automation.SwitchParameter <br/> |Suppression des fichiers de journaux en mémoire.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Stop-CcLogging n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

