---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: 'L’applet de connexion Enter-CcUpdate prépare le serveur hôte Cloud Connector Skype entreprise pour le processus de mise à jour en le plaçant en mode de maintenance. L’appliance isdrained: tous les appels existants seront exécutés, mais les nouveaux appels seront refusés.'
ms.openlocfilehash: be57261b35cf5b5e6e8118c2a751eee1c8b5f2a7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287439"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate
 
L’applet de connexion Enter-CcUpdate prépare le serveur hôte Cloud Connector Skype entreprise pour le processus de mise à jour en le plaçant en mode de maintenance. L’application est «drainée», c’est-à-dire que tous les appels existants sont terminés, mais les nouveaux appels sont refusés. 
  
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

L’applet de commande Enter-CcUpdate arrête immédiatement tous les services mettant fin à des appels en cours et l’application refusera tout nouveau appel, qui sont transférés vers d’autres appareils de production. Vous devez vous assurer que les autres appareils de production ne disposent pas de capacités suffisantes pour gérer les appels à partir de l’appareil que vous préparez à mettre à jour.
  
Le mode maintenance est utile si votre appliance possède une mise à jour automatique, par exemple, et si Microsoft possède un correctif d’intervention. Le mode maintenance est également utile si vous décidez d’interrompre les mises à jour automatiques mais que vous effectuez systématiquement des mises à jour manuelles.
  
Après l’installation des mises à jour, l’application peut être rétablie en mode de production en exécutant l’applet de passe Exit-CcUpdate.
  
> [!NOTE]
> Si vous décidez de mettre à jour manuellement un appareil de connexion Cloud, vous devez le mettre à jour dans 60 jours après la publication de la prochaine version par Microsoft. Microsoft prend en charge la version précédemment publiée du Cloud Connector pour 60 jours après la sortie de la nouvelle version 
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Enter-CCUpdate n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun 
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

