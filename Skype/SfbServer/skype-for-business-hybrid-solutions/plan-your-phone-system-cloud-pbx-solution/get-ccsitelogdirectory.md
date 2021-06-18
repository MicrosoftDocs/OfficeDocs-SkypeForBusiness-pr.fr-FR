---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: La cmdlet Get-CcSiteLogDirectory affiche l’annuaire actuel dans lequel sont stockés les journaux au niveau du site pour Skype Entreprise, version Cloud Connector.
ms.openlocfilehash: cace3ce3757294adbb3c55db24c619925f55ce5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799884"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
La cmdlet Get-CcSiteLogDirectory affiche l’annuaire actuel dans lequel sont stockés les journaux au niveau du site pour Skype Entreprise, version Cloud Connector. 
  
Cette cmdlet s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre le dossier actuel dans lequel les fichiers journaux du site Cloud Connector sont stockés :
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Le dossier par défaut est C:\Users \% userprofile%\CloudConnector\SiteRoot\Logs. Vous pouvez modifier le dossier en exécutant l'Set-CcSiteDirectory cmdlet. Il n’existe aucune cmdlet distincte qui modifie uniquement l’emplacement du dossier journal sans modifier l’annuaire de sites.
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Get-CcSiteLogDirectory n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

La commande renvoie un chemin d’accès au fichier.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

