---
title: Entrez-CcUpdate
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: L’applet de commande Enter-CcUpdate prépare le serveur hôte de la version Cloud Connector de Skype Entreprise au processus de mise à jour en le mettant en mode maintenance. La solution matérielle-logicielle isdrained — autrement dit, tous les appels existants seront effectue, mais les nouveaux appels sont rejetés.
ms.openlocfilehash: ed9f3f614829cd5b6bc2cd5499c6889258d67531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enter-ccupdate"></a>Entrez-CcUpdate
 
L’applet de commande Enter-CcUpdate prépare le serveur hôte de la version Cloud Connector de Skype Entreprise au processus de mise à jour en le mettant en mode maintenance. La solution matérielle-logicielle est « purgé » — autrement dit, tous les appels existants seront effectue, mais les nouveaux appels sont rejetés. 
  
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

L’applet de commande entrée-CcUpdate permet de garantir que tous les appels en cours d’exécution sur un matériel de connecteur de Cloud seront effectue, mais rejette tout nouveaux appels, qui sont transférées à d’autres applications de production. Cette applet de commande vous permet de mettre à jour une appliance sans que cela ait une incidence sur la fin des appels d’utilisateurs. Vous devez vous assurer que les appliances de production restantes possèdent une capacité suffisante pour supporter les appels de l’appliance que vous vous apprêtez à mettre à jour.
  
Le mode maintenance est utile si votre appliance possède une mise à jour automatique, par exemple, et si Microsoft possède un correctif d’intervention. Le mode maintenance est également utile si vous décidez d’interrompre les mises à jour automatiques mais que vous effectuez systématiquement des mises à jour manuelles.
  
Après avoir installé les mises à jour, l’appliance peut à nouveau être mise en mode production en exécutant l’applet de commande Exit-CcUpdate.
  
> [!NOTE]
> Si vous décidez de mettre à jour manuellement une application Connecteur de nuage, vous devez mettre à jour dans les 60 jours, une fois que Microsoft publie la prochaine version. Microsoft prend en charge la version précédemment publiée du connecteur de nuage pendant 60 jours après la publication de la nouvelle version 
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Enter-CCUpdate n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun 
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Quitter-CcUpdate](exit-ccupdate.md)
  

