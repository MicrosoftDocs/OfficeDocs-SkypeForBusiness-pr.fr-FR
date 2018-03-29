---
title: Commutateur-CcVersion
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: L’applet de commande du commutateur-CcVersion déconnecte de la solution matérielle-logicielle en cours d’exécution et bascule vers une solution matérielle-logicielle qui vient d’être déployé ou de sauvegarde.
ms.openlocfilehash: 651dad80ef5c9907eb6c182527b646da7aa5acc8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="switch-ccversion"></a>Commutateur-CcVersion
 
L’applet de commande du commutateur-CcVersion déconnecte de la solution matérielle-logicielle en cours d’exécution et bascule vers une solution matérielle-logicielle qui vient d’être déployé ou de sauvegarde. 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant draine les services de l’application en cours d’exécution en cours, puis passe à un matériel nouvellement déployé ou de sauvegarde :
  
```
Switch-CcVersion
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant draine les services de l’application en cours d’exécution en cours et arrête les services force si les services de drainage échoue. La commande passe ensuite à une solution matérielle-logicielle qui vient d’être déployé ou de sauvegarde :
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de commande du commutateur-CcVersion draine les services Cloud connecteur sur le serveur de médiation et d’un serveur de transport Edge. Tous les appels en cours d’exécution seront effectuées, mais la solution matérielle-logicielle rejette tous les appels de nouveau. Après l’écoulement, l’applet de commande déconnecte de la solution matérielle-logicielle en cours d’exécution à partir de l’entreprise et les réseaux Internet, désactive tous les ordinateurs virtuels appartenant à la solution matérielle-logicielle et connecte ensuite l’équipement de sauvegarde à l’entreprise et les réseaux Internet.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type de**|**Description**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Facultatif <br/> |System.Management.Automation.SwitchParameter  <br/> | Arrête les services force si les services de drainage échoue. <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucune
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Aucun
  

