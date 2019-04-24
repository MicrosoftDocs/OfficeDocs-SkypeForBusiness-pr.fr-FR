---
title: Set-CcSiteDirectory
ms.reviewer: ''
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
ms.openlocfilehash: 1c03d0f91b3a724df6ce61d216138bb281fb0b87
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32251456"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
L’applet de commande Set-CcSiteDirectory définit le répertoire dans lequel les fichiers de configuration de niveau site pour la version Cloud Connector de Skype Entreprise sont conservés. Le dossier contient les fichiers de configuration de base de VHD et Cloud Connector.
  
Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant définit le répertoire racine du site \\SiteShare\CloudConnector :
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Pour fournir une haute disponibilité et l’affinité de passerelle, appliances nuage connecteur peuvent être combinés dans les sites. Les utilisateurs sont affectés à des sites au lieu d’appliances nuage connecteur. Chaque site possède un dossier partagé dans lequel sont conservés les fichiers d’installation de base de VHD et Cloud Connector. Appliances utilisent ce dossier lors du déploiement. Ce dossier doit être partagé avec tous les autres équipements dans un site dans le nuage connecteur.
  
Le dossier par défaut est C:\Users\%userprofile%\CloudConnector\SiteRoot. Le chemin d’accès est visible à l’aide de l’applet de commande Get-CcSiteDirectory.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|  Path <br/> | Obligatoire <br/> | System.String <br/> |Fournit le chemin d’accès au dossier où seront stockés les fichiers du site dans le nuage connecteur.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Set-CcSiteDirectory n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

