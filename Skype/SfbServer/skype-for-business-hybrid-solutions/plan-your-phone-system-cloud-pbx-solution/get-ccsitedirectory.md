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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: La cmdlet Get-CcSiteDirectory affiche le répertoire actuel dans lequel les fichiers de configuration au niveau du site sont stockés. Le dossier contient le disque dur vhd de base et Skype Entreprise Cloud Connector Edition d’installation. Ce dossier doit être partagé avec toutes les autres appliances d’un site Cloud Connector.
ms.openlocfilehash: 04b1460b9743c3d19ca4db77f67d057d400f400b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616370"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
La cmdlet Get-CcSiteDirectory affiche le répertoire actuel dans lequel les fichiers de configuration au niveau du site sont stockés. Le dossier contient le disque dur vhd de base et Skype Entreprise Cloud Connector Edition d’installation. Ce dossier doit être partagé avec toutes les autres appliances d’un site Cloud Connector.
  
Cette cmdlet s’applique à Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre le dossier actuel dans lequel sont stockés les fichiers de configuration et de machines virtuelles des composants Cloud Connector :
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Pour fournir une affinité de passerelle et une haute disponibilité, les appliances Cloud Connector peuvent être combinées dans des sites. Les utilisateurs sont affectés à des sites au lieu d’appliances Cloud Connector. Chaque site possède un dossier partagé dans lequel sont stockés les fichiers d’installation de base de VHD et Cloud Connector. Les appliances utilisent ce dossier pendant le déploiement. Le dossier par défaut est C:\Users \% userprofile%\CloudConnector\SiteRoot. Vous pouvez modifier le chemin d’accès à l’aide Set-CcSiteDirectory cmdlet.
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Get-CcSiteDirectory n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Cette commande renvoie un chemin d’accès au fichier.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

