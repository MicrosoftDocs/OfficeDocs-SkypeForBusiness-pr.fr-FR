---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: La cmdlet Set-CcSiteDirectory définit le répertoire dans lequel les fichiers de configuration au niveau du site Skype Entreprise Cloud Connector Edition seront stockés. Le dossier contient les fichiers de configuration vhD de base et Cloud Connector.
ms.openlocfilehash: e5685ac8c203338365141a4a7ba59daa82a06ef0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610531"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
La cmdlet Set-CcSiteDirectory définit le répertoire dans lequel les fichiers de configuration au niveau du site Skype Entreprise Cloud Connector Edition seront stockés. Le dossier contient les fichiers de configuration vhD de base et Cloud Connector.
  
Cette cmdlet s’applique Skype Entreprise Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant définit le répertoire racine du site \\ sur SiteShare\CloudConnector :
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Pour fournir une affinité de passerelle et une haute disponibilité, les appliances Cloud Connector peuvent être combinées dans des sites. Les utilisateurs sont affectés à des sites au lieu d’appliances Cloud Connector. Chaque site possède un dossier partagé dans lequel sont stockés les fichiers d’installation de base de VHD et Cloud Connector. Les appliances utilisent ce dossier pendant le déploiement. Ce dossier doit être partagé avec toutes les autres appliances d’un site Cloud Connector.
  
Le dossier par défaut est C:\Users \% userprofile%\CloudConnector\SiteRoot. Le chemin d’accès peut être vu à l’aide Get-CcSiteDirectory cmdlet.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| Path <br/> | Requis <br/> | System.String <br/> |Fournit le chemin d’accès au dossier dans lequel les fichiers de site Cloud Connector seront stockés.  <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Set-CcSiteDirectory n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

