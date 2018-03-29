---
title: Exportation-CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporte le Skype pour la configuration du connecteur de Cloud Business Edition à un fichier local sur le Skype pour serveur hôte de connecteur de Cloud Business Edition.
ms.openlocfilehash: dfabf5f486190b13acd18f0ffcf67f9b7e37052c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfiguration"></a>Exportation-CcConfiguration
 
Exporte le Skype pour la configuration du connecteur de Cloud Business Edition à un fichier local sur le Skype pour serveur hôte de connecteur de Cloud Business Edition.
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant définit le paramètre de chemin d’accès sous la forme d’un chemin d’accès complet du fichier et exporte les configurations à ce fichier.
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>Description détaillée
<a name="Examples"> </a>

L’applet de commande exportation-CcConfiguration vous permet d’enregistrer la configuration du connecteur du Cloud dans un fichier dans un chemin d’accès sélectionné. Cette commande a été introduite dans le nuage lien Edition version 2.0.
  
## <a name="parameters"></a>Paramètres
<a name="Examples"> </a>

|**Paramètre**|**Obligatoire**|**Type de**|**Description**|
|:-----|:-----|:-----|:-----|
| Path  <br/> |Obligatoire  <br/> |System.String  <br/> |Chemin complet du fichier où seront stockées les configurations de connecteur de nuage.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="Examples"> </a>

Aucun. L’applet de commande exportation-CcConfiguration n’accepte pas les entrées de pipeline.
  
## <a name="return-types"></a>Types de retours
<a name="Examples"> </a>

Aucun.
  
## <a name="see-also"></a>Voir aussi
<a name="Examples"> </a>

Importation-CcConfiguration
  

