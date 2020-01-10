---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: L’applet de commande Get-CcSiteDirectory affiche le répertoire dans lequel sont actuellement conservés les fichiers de configuration de niveau site. Le dossier contient les fichiers d’installation de base de VHD et Skype Entreprise, version Cloud Connector. Ce dossier doit être partagé avec toutes les autres applications d’un site Cloud Connector.
ms.openlocfilehash: 095776a680fbbcc8c43a8f99700b357175010b5a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003364"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
L’applet de commande Get-CcSiteDirectory affiche le répertoire dans lequel sont actuellement conservés les fichiers de configuration de niveau site. Le dossier contient les fichiers d’installation de base de VHD et Skype Entreprise, version Cloud Connector. Ce dossier doit être partagé avec toutes les autres applications d’un site Cloud Connector.
  
Cette applet de commande s’applique à Cloud Connector 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre le dossier actuel dans lequel se trouvent les fichiers de configuration et d’ordinateurs virtuels des composants Cloud Connector :
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Pour fournir une affinité et une haute disponibilité de la passerelle, les appareils de connexion Cloud peuvent être combinés dans les sites. Les utilisateurs sont affectés à des sites au lieu de périphériques Cloud Connector. Chaque site possède un dossier partagé dans lequel sont conservés les fichiers d’installation de base de VHD et Cloud Connector. Les appareils utilisent ce dossier lors du déploiement. Le dossier par défaut est\%C:\Users UserProfile%\CloudConnector\SiteRoot. Vous pouvez modifier le chemin d’accès à l’aide de l’applet de commande Set-CcSiteDirectory.
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Get-CcSiteDirectory n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Cette commande renvoie un chemin d’accès.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

