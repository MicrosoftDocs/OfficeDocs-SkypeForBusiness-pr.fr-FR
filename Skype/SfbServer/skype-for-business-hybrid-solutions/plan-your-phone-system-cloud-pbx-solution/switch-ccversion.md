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
ms.localizationpriority: medium
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: LSwitch-CcVersion cmdlet déconnecte l’appliance en cours d’exécution et bascule vers une appliance nouvellement déployée ou de sauvegarde.
ms.openlocfilehash: 9b15310956f80a9269c8fb611a0f7c6c06f561e7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580328"
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

Aucune
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucune
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Néant
  

