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
description: La cmdlet Get-CcApplianceLogDirectory affiche le répertoire actuel dans lequel les journaux d’une Skype Entreprise Cloud Connector Edition’appareil sont stockés.
ms.openlocfilehash: 75f3ba3a5de5198456e053bd51ef567df1a0ae43461e9888e87294d3af406288
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318657"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
La cmdlet Get-CcApplianceLogDirectory affiche le répertoire actuel dans lequel les journaux d’une Skype Entreprise Cloud Connector Edition’appareil sont stockés.
  
Cette cmdlet s’applique Skype Entreprise Cloud Connector Edition 1.4.1, 1.4.2.
  
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
  
Remarque : il n’existe aucune cmdlet qui modifie uniquement l’emplacement du dossier journal sans modifier le répertoire de l’appliance.
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Get-CcApplianceLogDirectory n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Cette commande renvoie un chemin d’accès au fichier.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

