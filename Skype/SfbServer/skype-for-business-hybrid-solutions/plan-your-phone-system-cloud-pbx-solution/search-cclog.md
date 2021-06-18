---
title: Search-CcLog
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: La cmdlet Search-CcLog recherche les journaux des appels entrants et sortants dans le répertoire des journaux des appliances de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: a512d715f1640184217ce07e0b666954a6541fd2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824230"
---
# <a name="search-cclog"></a>Search-CcLog
 
La cmdlet Search-CcLog recherche les journaux des appels entrants et sortants dans le répertoire des journaux des appliances de la version Cloud Connector de Skype Entreprise.
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant recherche les journaux des appels entrants et sortants dans le répertoire des journaux de l’appliance à l’aide du nom de fichier par défaut :
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant recherche les journaux des appels entrants et sortants à l’aide du chemin d’accès et du nom de fichier donnés :
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de commande Search-CsClsLogging fournit une option de ligne de commande pour rechercher les fichiers journaux générés par le service de journalisation centralisée.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | Obligatoire <br/> |System.Datetime  <br/> | Date et heure de début des entrées de journal à rechercher. Spécifiées dans le fuseau horaire local. <br/> |
|EndTime  <br/> |Obligatoire  <br/> |System.Datetime  <br/> |Date et heure de fin des entrées de journal à rechercher. Spécifiées dans le fuseau horaire local.  <br/> |
|FileName  <br/> |Obligatoire  <br/> |System.String  <br/> |Spécifie le chemin d’accès complet du fichier texte contenant les résultats de la recherche.  <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Search-CcLog n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

