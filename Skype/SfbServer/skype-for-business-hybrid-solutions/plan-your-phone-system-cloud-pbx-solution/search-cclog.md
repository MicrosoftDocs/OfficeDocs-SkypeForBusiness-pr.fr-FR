---
title: Recherche-CcLog
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: L’applet de commande Search-CcLog recherche les journaux d’appels sortants et entrants dans l’annuaire d’appliances de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: 3d7d34f2e069b9c4ed728dcc805af5ccf9d13067
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="search-cclog"></a>Recherche-CcLog
 
L’applet de commande Search-CcLog recherche les journaux d’appels sortants et entrants dans l’annuaire d’appliances de la version Cloud Connector de Skype Entreprise.
  
```
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant recherche les journaux d’appels sortants et entrants dans l’annuaire d’appliances en utilisant le nom du fichier de défaut.
  
```
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant recherche les journaux d’appels sortants et entrants en utilisant le chemin d’accès et le nom du fichier donné :
  
```
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de commande  Search-CsClsLogging fournit une option de ligne de commande pour rechercher les fichiers journaux générés par le service de journalisation centralisée.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type de**|**Description**|
|:-----|:-----|:-----|:-----|
|Heure de début  <br/> | Obligatoire <br/> |System.Datetime  <br/> | Date et heure de début des entrées de journal à rechercher. Spécifiées dans le fuseau horaire local. <br/> |
|Heure de fin  <br/> |Obligatoire  <br/> |System.Datetime  <br/> |Date et heure de fin des entrées de journal à rechercher. Spécifiées dans le fuseau horaire local.  <br/> |
|Nom de fichier  <br/> |Obligatoire  <br/> |System.String  <br/> |Spécifie le chemin d’accès complet du fichier texte contenant les résultats de la recherche.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Search-CcLog n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Démarrer-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

