---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: L’applet de commande entrée-CcUpdate prépare la Skype pour le serveur hôte de nuage connecteur édition pour le processus de mise à jour en lui appliquant en mode maintenance. L’appliance isdrained — autrement dit, tous les appels en cours seront termine, mais les nouveaux appels sont rejetés.
ms.openlocfilehash: 42c8f7fa668fa94040276e7749e93b5832d511cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929430"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate
 
L’applet de commande entrée-CcUpdate prépare la Skype pour le serveur hôte de nuage connecteur édition pour le processus de mise à jour en lui appliquant en mode maintenance. Le matériel est « drainée » — autrement dit, tous les appels en cours seront termine, mais les nouveaux appels sont rejetés. 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant prépare l’appliance au processus de mise à jour en entrant en mode maintenance.
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de commande entrée-CcUpdate s’arrête immédiatement tous les services de fin des appels en cours et rejette les nouveaux appels, qui sont transférés à d’autres applications de production. Vous devez vous assurer que les appareils de production restants possède une capacité suffisante pour traiter les appels à partir de l’application que vous préparez à mettre à jour.
  
Le mode maintenance est utile si votre appliance possède une mise à jour automatique, par exemple, et si Microsoft possède un correctif d’intervention. Le mode maintenance est également utile si vous décidez d’interrompre les mises à jour automatiques mais que vous effectuez systématiquement des mises à jour manuelles.
  
Après avoir installé les mises à jour, l’appliance peut être ramené vers le mode de production en exécutant l’applet de commande Exit-CcUpdate.
  
> [!NOTE]
> Si vous décidez de mettre à jour manuellement une solution de nuage connecteur, vous devez mettre à jour dans les 60 jours après que Microsoft publie la prochaine version. Microsoft prend en charge la version précédemment du nuage connecteur pendant 60 jours après la publication de la nouvelle version 
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Enter-CCUpdate n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun 
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

