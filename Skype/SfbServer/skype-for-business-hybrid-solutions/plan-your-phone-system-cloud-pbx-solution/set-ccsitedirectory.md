---
title: Ensemble-CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: L’applet de commande Set-CcSiteDirectory définit le répertoire dans lequel les fichiers de configuration de niveau site pour la version Cloud Connector de Skype Entreprise sont conservés. Le dossier contient les fichiers de configuration de base de VHD et Cloud Connector.
ms.openlocfilehash: d34945a17f32c275240e2cef0435f6e0ca3e63a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccsitedirectory"></a>Ensemble-CcSiteDirectory
 
L’applet de commande Set-CcSiteDirectory définit le répertoire dans lequel les fichiers de configuration de niveau site pour la version Cloud Connector de Skype Entreprise sont conservés. Le dossier contient les fichiers de configuration de base de VHD et Cloud Connector.
  
Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant définit le répertoire racine du site \\SiteShare\CloudConnector :
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Pour fournir une affinité de passerelle et de haute disponibilité, appareils de nuage connecteur peuvent être combinés dans des sites. Les utilisateurs sont affectés à des sites plutôt que des appareils de connecteur de nuage. Chaque site possède un dossier partagé dans lequel sont conservés les fichiers d’installation de base de VHD et Cloud Connector. Appliances utilisent ce dossier pendant le déploiement. Ce dossier doit être partagé avec tous les autres équipements dans un site connecteur du nuage.
  
Le dossier par défaut est C:\Users\%userprofile%\CloudConnector\SiteRoot. Le chemin d’accès est visible à l’aide de l’applet de commande Get-CcSiteDirectory.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type de**|**Description**|
|:-----|:-----|:-----|:-----|
|  Path <br/> | Obligatoire <br/> | System.String <br/> |Fournit le chemin d’accès au dossier où seront stockés les fichiers du site connecteur du nuage.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Set-CcSiteDirectory n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

