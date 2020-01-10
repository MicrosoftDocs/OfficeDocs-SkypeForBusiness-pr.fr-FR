---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: L’applet de commande Stop-CcLogging interrompt la création de journaux d'appels entrants et sortants pour une appliance de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: 4528f7c1458093874f59f347585a736666a9ea08
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003164"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
L’applet de commande Stop-CcLogging interrompt la création de journaux d'appels entrants et sortants pour une appliance de la version Cloud Connector de Skype Entreprise.
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant interrompt la création de journaux d'appels entrants et sortants :  
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant interrompt la création de journaux d'appels entrants et sortants et nettoie les fichiers en mémoire :
  
```powershell
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
  

