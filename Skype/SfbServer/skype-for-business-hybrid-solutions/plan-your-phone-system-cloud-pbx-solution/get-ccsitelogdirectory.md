---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: 'L’applet de commande Get-CcSiteLogDirectory montre l’annuaire actuel où les journaux de niveau de site de la version Cloud Connector de Skype Entreprise sont conservés. '
ms.openlocfilehash: c4354920ac25d076e550c5eda3a641eef0c8b900
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886126"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
L’applet de commande Get-CcSiteLogDirectory montre l’annuaire actuel où les journaux de niveau de site de la version Cloud Connector de Skype Entreprise sont conservés.  
  
Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre le dossier actif où sont stockés les fichiers journaux pour le site de connecteur dans le nuage :
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Le dossier par défaut est C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs. Vous pouvez modifier le dossier en exécutant l’applet de commande Set-CcSiteDirectory. Il n’existe pas d’applet de commande distincte qui modifie uniquement l’emplacement du dossier de connexion sans modifier l’annuaire de sites.
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Get-CcSiteLogDirectory n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

La commande renvoie un chemin d’accès de fichier.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

