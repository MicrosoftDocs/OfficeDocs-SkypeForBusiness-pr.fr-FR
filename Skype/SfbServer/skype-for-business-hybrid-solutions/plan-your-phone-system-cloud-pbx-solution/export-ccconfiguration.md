---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporte la configuration Skype Entreprise Cloud Connector Edition vers un fichier local sur Skype Entreprise Cloud Connector Edition serveur hôte.
ms.openlocfilehash: b2b3ea0171b68701b47b8ae2ed239f2e0495855b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625006"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Exporte la configuration Skype Entreprise Cloud Connector Edition vers un fichier local sur Skype Entreprise Cloud Connector Edition serveur hôte.
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant définit le paramètre Path comme chemin d’accès complet et exporte les configurations dans ce fichier.
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>Description détaillée
<a name="Examples"> </a>

LExport-CcConfiguration cmdlet vous permet d’enregistrer la configuration Cloud Connector dans un fichier dans un chemin d’accès sélectionné. Cette commande a été introduite dans la version 2.0 de Cloud Connector.
  
## <a name="parameters"></a>Paramètres
<a name="Examples"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|Path  <br/> |Requis  <br/> |System.String  <br/> |Chemin d’accès complet au fichier dans lequel les configurations Cloud Connector seront stockées.  <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="Examples"> </a>

Aucun. La cmdlet Export-CcConfiguration n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="Examples"> </a>

Aucun.
  
## <a name="see-also"></a>Voir aussi
<a name="Examples"> </a>

Import-CcConfiguration
  

