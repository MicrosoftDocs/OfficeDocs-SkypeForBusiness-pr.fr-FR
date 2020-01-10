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
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: L’applet de commande Search-CcLog recherche les journaux d’appels sortants et entrants dans l’annuaire d’appliances de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: c248720931ef1c15d633c51bb6daa6c414631a18
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003234"
---
# <a name="search-cclog"></a>Search-CcLog
 
L’applet de commande Search-CcLog recherche les journaux d’appels sortants et entrants dans l’annuaire d’appliances de la version Cloud Connector de Skype Entreprise.
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant recherche les journaux d’appels sortants et entrants dans l’annuaire d’appliances en utilisant le nom du fichier de défaut.
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant recherche les journaux d’appels sortants et entrants en utilisant le chemin d’accès et le nom du fichier donné :
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de commande  Search-CsClsLogging fournit une option de ligne de commande pour rechercher les fichiers journaux générés par le service de journalisation centralisée.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | Obligatoire <br/> |System.Datetime  <br/> | Date et heure de début des entrées de journal à rechercher. Spécifiées dans le fuseau horaire local. <br/> |
|EndTime  <br/> |Obligatoire  <br/> |System.Datetime  <br/> |Date et heure de fin des entrées de journal à rechercher. Spécifiées dans le fuseau horaire local.  <br/> |
|FileName  <br/> |Obligatoire  <br/> |System.String  <br/> |Spécifie le chemin d’accès complet du fichier texte contenant les résultats de la recherche.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Search-CcLog n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

