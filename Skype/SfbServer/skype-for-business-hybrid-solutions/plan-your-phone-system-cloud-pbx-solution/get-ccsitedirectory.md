---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: L’applet de commande Get-CcSiteDirectory affiche le répertoire dans lequel sont actuellement conservés les fichiers de configuration de niveau site. Le dossier contient les fichiers d’installation de base de VHD et Skype Entreprise, version Cloud Connector. Ce dossier doit être partagé avec tous les autres équipements d’un site dans le nuage connecteur.
ms.openlocfilehash: d0869f3cbd1c43e523107a0ff8dce6fd769889a8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882396"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
L’applet de commande Get-CcSiteDirectory affiche le répertoire dans lequel sont actuellement conservés les fichiers de configuration de niveau site. Le dossier contient les fichiers d’installation de base de VHD et Skype Entreprise, version Cloud Connector. Ce dossier doit être partagé avec tous les autres équipements d’un site dans le nuage connecteur.
  
Cette applet de commande s’applique à Cloud Connector 1.4.1, 1.4.2.
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre le dossier actif où sont stockés les fichiers de configuration et les machines virtuelles des composants de connecteur dans le nuage :
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Pour fournir une haute disponibilité et l’affinité de passerelle, appliances nuage connecteur peuvent être combinés dans les sites. Les utilisateurs sont affectés à des sites au lieu d’appliances nuage connecteur. Chaque site possède un dossier partagé dans lequel sont conservés les fichiers d’installation de base de VHD et Cloud Connector. Appliances utilisent ce dossier lors du déploiement. Le dossier par défaut est C:\Users\%userprofile%\CloudConnector\SiteRoot. Vous pouvez modifier le chemin d’accès à l’aide de l’applet de commande Set-CcSiteDirectory.
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Get-CcSiteDirectory n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Cette commande renvoie un chemin d’accès.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

