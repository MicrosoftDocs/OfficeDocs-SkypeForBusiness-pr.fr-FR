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
description: La cmdlet Search-CcLog recherche les journaux des appels entrants et sortants dans Skype Entreprise Cloud Connector Edition répertoire des journaux de l’appliance.
ms.openlocfilehash: 5fd062295ac9145660ca9a53f56973f77783cd9730993d958c7348b7761c4387
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306605"
---
# <a name="search-cclog"></a>Search-CcLog
 
La cmdlet Search-CcLog recherche les journaux des appels entrants et sortants dans Skype Entreprise Cloud Connector Edition répertoire des journaux de l’appliance.
  
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

Néant
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

