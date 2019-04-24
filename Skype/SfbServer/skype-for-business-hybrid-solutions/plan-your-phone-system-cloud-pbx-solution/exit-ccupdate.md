---
title: Exit-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: 'L’applet de commande Exit-CcUpdate effectue un mode maintenance de la mise à jour sur le serveur hôte de la version Cloud Connector de Skype Entreprise. '
ms.openlocfilehash: 7ac36e9cbab8e479a4ec7b070b773b3585370e8f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234040"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
L’applet de commande Exit-CcUpdate effectue un mode maintenance de la mise à jour sur le serveur hôte de la version Cloud Connector de Skype Entreprise.  
  
Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2. 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

La commande suivante remet l’appliance en mode production :  
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Si vous disposez d’appliances que vous avez mises en mode maintenance en spécifiant l’applet de commande Enter-CcUpdate, l'applet de commande Exit-CcUpdate les mettra à nouveau en mode production.  
  
Pour plus d’informations sur la manière de mettre les appliances en mode maintenance, reportez-vous à la rubrique Enter-CcUpdate.
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Exit-CcUpdate n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun 
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

