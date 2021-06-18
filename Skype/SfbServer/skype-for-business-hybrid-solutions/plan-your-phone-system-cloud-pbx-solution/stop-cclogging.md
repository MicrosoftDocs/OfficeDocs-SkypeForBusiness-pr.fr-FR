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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: LStop-CcLogging cmdlet arrête de générer le journal des appels entrants et sortants pour une appliance de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824158"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
LStop-CcLogging cmdlet arrête de générer le journal des appels entrants et sortants pour une appliance de la version Cloud Connector de Skype Entreprise.
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant arrête de générer le journal des appels entrants et sortants : 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant arrête de générer le journal des appels entrants et sortants et nettoie les fichiers cache :
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

La cmdlet Stop-CcLogging la journalisation des appels entrants et sortants sur une appliance. Par défaut, la journalisation s’arrête automatiquement après quatre heures.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | Facultatif <br/> | System.Management.Automation.SwitchParameter <br/> |Supprime les fichiers de cache de journalisation.  <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Stop-CcLogging n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

