---
title: Exit-CcUpdate
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
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: LExit-CcUpdate cmdlet quitte le mode maintenance de mise à jour Skype Entreprise Cloud Connector Edition serveur hôte.
ms.openlocfilehash: d55004f071caa67492d5368e36007d9c3c307b90aabbc33d79d1feeb4aa37356
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288834"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
LExit-CcUpdate cmdlet quitte le mode maintenance de mise à jour Skype Entreprise Cloud Connector Edition serveur hôte. 
  
Cette cmdlet s’applique Skype Entreprise Cloud Connector Edition 1.4.1, 1.4.2. 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

La commande suivante place l’appliance sur laquelle elle s’exécute à nouveau en mode production : 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Si vous avez des appliances que vous avez mises en mode maintenance en spécifiant l'Enter-CcUpdate cmdlet, l'Exit-CcUpdate les place en mode production. 
  
Pour plus d’informations sur la mise en mode maintenance des appliances, voir Enter-CcUpdate.
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Exit-CcUpdate n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Néant 
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

