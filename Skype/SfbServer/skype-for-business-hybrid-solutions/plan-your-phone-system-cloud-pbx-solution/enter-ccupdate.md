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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: L’applet de connexion Enter-CcUpdate prépare le serveur hôte Cloud Connector Skype entreprise pour le processus de mise à jour en le plaçant en mode de maintenance. L’application arrête immédiatement tous les services, fin des appels en cours et rejette tout nouvel appel.
ms.openlocfilehash: 25d2fbc56bd4de6a08985de18c178d5a8f993492
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802174"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

L’applet de connexion Enter-CcUpdate prépare le serveur hôte Cloud Connector Skype entreprise pour le processus de mise à jour en le plaçant en mode de maintenance. L’application arrête immédiatement tous les services, fin des appels en cours et rejette tout nouvel appel.
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant prépare l’appliance au processus de mise à jour en entrant en mode maintenance.
  
```powershell
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
  

