---
title: Switch-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: L’applet de commande commutateur-CcVersion déconnecte l’application en cours d’exécution et bascule vers un appareil nouvellement déployé ou de sauvegarde.
ms.openlocfilehash: 73ae9b4f93a2488dea29f3271565ac3d25759fd1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872858"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
L’applet de commande commutateur-CcVersion déconnecte l’application en cours d’exécution et bascule vers un appareil nouvellement déployé ou de sauvegarde. 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant draine les services de l’application en cours d’exécution en cours, puis bascule vers un appareil nouvellement déployé ou de sauvegarde :
  
```
Switch-CcVersion
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant draine les services de l’application en cours d’exécution en cours et arrête les services force en cas d’échec de drainage les services. La commande bascule alors vers un appareil nouvellement déployé ou de sauvegarde :
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de commande commutateur-CcVersion draine les services de nuage connecteur sur le serveur de médiation et le serveur de périphérie. Tous les appels en cours d’exécution seront effectuées, mais rejette les nouveaux appels. Après l’écoulement, l’applet de commande déconnecte l’application en cours d’exécution de l’entreprise et les réseaux Internet, désactive tous les ordinateurs virtuels appartenant à l’application et connecte ensuite l’équipement de sauvegarde à l’entreprise et les réseaux Internet.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Facultatif <br/> |System.Management.Automation.SwitchParameter  <br/> | Arrête les services force si les services de drainage échoue. <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucune
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Aucun
  

