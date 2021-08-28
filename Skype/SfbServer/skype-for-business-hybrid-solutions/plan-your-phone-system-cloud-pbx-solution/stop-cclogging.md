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
ms.localizationpriority: medium
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: La cmdlet Stop-CcLogging arrête de générer le journal des appels entrants et sortants pour une appliance Skype Entreprise Cloud Connector Edition’appareil.
ms.openlocfilehash: cfa07602f8465ce3c931010f835f52acc44e2ee2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580339"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
La cmdlet Stop-CcLogging arrête de générer le journal des appels entrants et sortants pour une appliance Skype Entreprise Cloud Connector Edition’appareil.
  
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

Aucune
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

