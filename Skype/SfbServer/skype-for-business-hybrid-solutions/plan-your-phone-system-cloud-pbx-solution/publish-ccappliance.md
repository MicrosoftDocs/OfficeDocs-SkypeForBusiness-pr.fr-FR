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
ms.openlocfilehash: da9135f669cb5b8cbe127295b20d82fd1632a3d3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003084"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
L’applet de commande Publish-CcAppliance apporte des informations haute disponibilité à partir de la configuration client en ligne et les publie dans l’appliance du serveur hôte de la version Cloud Connector de Skype Entreprise.  
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant obtient des informations de haute disponibilité dans la configuration de client en ligne et la publie sur le périphérique Cloud Connector sur le serveur hôte :
  
```powershell
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
  

