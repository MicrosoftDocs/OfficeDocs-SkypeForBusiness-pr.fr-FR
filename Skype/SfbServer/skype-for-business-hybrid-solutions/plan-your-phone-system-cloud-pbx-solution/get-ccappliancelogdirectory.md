---
title: Get-CcApplianceLogDirectory
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
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: LGet-CcApplianceLogDirectory cmdlet affiche l’annuaire actuel dans lequel sont stockés les journaux d’une appliance de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800824"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
LGet-CcApplianceLogDirectory cmdlet affiche l’annuaire actuel dans lequel sont stockés les journaux d’une appliance de la version Cloud Connector de Skype Entreprise.
  
Cette cmdlet s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre le dossier actuel dans lequel les journaux de l’appliance actuelle de Cloud Connector sont stockés :
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

LGet-CcApplianceLogDirectory cmdlet affiche le répertoire actuel dans lequel les journaux d’une appliance Cloud Connector sont stockés. Le dossier par défaut est C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs. 
  
Vous pouvez modifier le répertoire à l’aide de Set-CcApplianceDirectory cmdlet. 
  
Remarque : aucune cmdlet ne modifie uniquement l’emplacement du dossier journal sans modifier le répertoire de l’appliance.
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Get-CcApplianceLogDirectory n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Cette commande renvoie un chemin d’accès au fichier.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

