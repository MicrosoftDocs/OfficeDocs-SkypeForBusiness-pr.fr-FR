---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporte le Skype pour la configuration du connecteur du nuage Professionnel vers un fichier local sur le Skype pour le serveur hôte de nuage connecteur édition.
ms.openlocfilehash: 8afca55e6727c84c579957de9e2010e84a72fb15
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234055"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Exporte le Skype pour la configuration du connecteur du nuage Professionnel vers un fichier local sur le Skype pour le serveur hôte de nuage connecteur édition.
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant définit le paramètre de chemin d’accès sous la forme d’un chemin d’accès complet et exporte les configurations dans ce fichier.
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>Description détaillée
<a name="Examples"> </a>

L’applet de commande Export-CcConfiguration vous permet d’enregistrer la configuration du connecteur du nuage vers un fichier dans un chemin d’accès sélectionné. Cette commande a été introduite dans le nuage connecteur Edition version 2.0.
  
## <a name="parameters"></a>Paramètres
<a name="Examples"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| Path  <br/> |Obligatoire  <br/> |System.String  <br/> |Chemin d’accès complet du fichier où seront stockées les configurations de connecteur dans le nuage.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="Examples"> </a>

Aucun. L’applet de commande Export-CcConfiguration n’accepte pas la saisie de données redirigées.
  
## <a name="return-types"></a>Types de retours
<a name="Examples"> </a>

Aucun.
  
## <a name="see-also"></a>Voir aussi
<a name="Examples"> </a>

Import-CcConfiguration
  

