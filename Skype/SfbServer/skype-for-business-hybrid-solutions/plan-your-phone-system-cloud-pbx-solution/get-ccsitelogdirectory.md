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
ms.localizationpriority: medium
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: LGet-CcSiteLogDirectory cmdlet affiche le répertoire actuel dans lequel les journaux au niveau du site pour Skype Entreprise Cloud Connector Edition sont stockés.
ms.openlocfilehash: 65d99093f6390eade15e9783bd286bc438ede23d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616360"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
LGet-CcSiteLogDirectory cmdlet affiche le répertoire actuel dans lequel les journaux au niveau du site pour Skype Entreprise Cloud Connector Edition sont stockés. 
  
Cette cmdlet s’applique Skype Entreprise Cloud Connector Edition 1.4.1, 1.4.2.
  
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
  

