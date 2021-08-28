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
ms.localizationpriority: medium
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: LEnter-CcUpdate cmdlet prépare le Skype Entreprise Cloud Connector Edition hôte pour le processus de mise à jour en le mettant en mode maintenance. L’appliance arrête immédiatement tous les services, mettant fin à tous les appels en cours et rejetant les nouveaux appels.
ms.openlocfilehash: 26f1874ca6c0b92836716d66031945adc864d0ff
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620760"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

LEnter-CcUpdate cmdlet prépare le Skype Entreprise Cloud Connector Edition hôte pour le processus de mise à jour en le mettant en mode maintenance. L’appliance arrête immédiatement tous les services, mettant fin à tous les appels en cours et rejetant les nouveaux appels.
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant prépare l’appliance pour le processus de mise à jour en entrant en mode maintenance :
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

La cmdlet Enter-CcUpdate arrêtera immédiatement tous les services mettant fin aux appels en cours et l’appliance rejettera les nouveaux appels transférés vers d’autres appliances de production. Vous devez vous assurer que les appliances de production restantes ont une capacité suffisante pour gérer les appels provenant de l’appliance que vous préparez à mettre à jour.
  
Le mode maintenance est utile si la mise à jour automatique de votre appliance est activée, par exemple, et que Microsoft libère un correctif logiciel critique. Le mode maintenance est également utile si vous décidez de désactiver les mises à jour automatiques, mais que vous effectuez des mises à jour manuelles de manière cohérente.
  
Après avoir installé les mises à jour, l’appliance peut revenir en mode production en exécutant Exit-CcUpdate cmdlet.
  
> [!NOTE]
> Si vous décidez de mettre à jour manuellement une appliance Cloud Connector, vous devez la mettre à jour dans les 60 jours suivant la publication de la version suivante par Microsoft. Microsoft prend en charge la version de Cloud Connector publiée précédemment pendant 60 jours après la publication de la nouvelle version. 
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Enter-CCUpdate n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun 
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

