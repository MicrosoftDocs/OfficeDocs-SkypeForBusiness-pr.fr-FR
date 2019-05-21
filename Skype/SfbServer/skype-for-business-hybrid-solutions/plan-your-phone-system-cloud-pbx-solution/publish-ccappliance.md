---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: 'L’applet de commande Publish-CcAppliance apporte des informations haute disponibilité à partir de la configuration client en ligne et les publie dans l’appliance du serveur hôte de la version Cloud Connector de Skype Entreprise. '
ms.openlocfilehash: 2fd17e2afdceabc8fbfb44a808b7e6c9ce6bd894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287159"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
L’applet de commande Publish-CcAppliance apporte des informations haute disponibilité à partir de la configuration client en ligne et les publie dans l’appliance du serveur hôte de la version Cloud Connector de Skype Entreprise.  
  
```
Publish-CcAppliance
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant obtient des informations de haute disponibilité dans la configuration de client en ligne et la publie sur le périphérique Cloud Connector sur le serveur hôte:
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Les informations sur la haute disponibilité contiennent les noms de domaine complets du serveur de médiation et les adresses IP du site RTC. Les nouveaux enregistrements DNS A sont ajoutés au serveur AD pour les adresses IP du serveur de médiation. Les options de la nouvelle topologie sont mises à jour dans le magasin central de gestion pour les noms de domaine complets et les adresses IP du serveur de médiation.  
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Publish-CcAppliance n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

