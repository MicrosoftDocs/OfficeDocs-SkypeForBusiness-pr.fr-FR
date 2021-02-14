---
title: Switch-CcVersion
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
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: LSwitch-CcVersion cmdlet déconnecte l’appliance en cours d’exécution et bascule vers une appliance nouvellement déployée ou de sauvegarde.
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824148"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
LSwitch-CcVersion cmdlet déconnecte l’appliance en cours d’exécution et bascule vers une appliance nouvellement déployée ou de sauvegarde. 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant draine les services de l’appliance en cours d’exécution, puis bascule vers une appliance récemment déployée ou de sauvegarde :
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant draine les services de l’appliance en cours d’exécution et arrête les services de force en cas d’échec du drainage des services. La commande bascule ensuite vers une appliance nouvellement déployée ou de sauvegarde :
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

La cmdlet Switch-CcVersion draine les services Cloud Connector sur le serveur de médiation et le serveur Edge. Tous les appels en cours d’exécution seront terminés, mais l’appliance rejettera les nouveaux appels. Après le drainage, l’cmdlet déconnecte l’appliance en cours d’exécution des réseaux d’entreprise et Internet, dés éteint toutes les machines virtuelles appartenant à l’appliance, puis connecte l’appliance de sauvegarde aux réseaux d’entreprise et Internet.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Facultatif <br/> |System.Management.Automation.SwitchParameter  <br/> | Arrête les services de force en cas d’échec du drainage des services. <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Aucun
  

