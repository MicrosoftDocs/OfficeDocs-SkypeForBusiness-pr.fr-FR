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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: LPublish-CcAppliance cmdlet obtient les informations de haute disponibilité de la configuration du client en ligne et les publie dans l’appliance Cloud Connector de Skype Entreprise sur le serveur hôte.
ms.openlocfilehash: 159247614733261cac4b3381e35d8dd297cf9a23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824310"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
LPublish-CcAppliance cmdlet obtient les informations de haute disponibilité de la configuration du client en ligne et les publie dans l’appliance Cloud Connector de Skype Entreprise sur le serveur hôte. 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant obtient les informations de haute disponibilité de la configuration du client en ligne et les publie dans l’appliance Cloud Connector sur le serveur hôte :
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Les informations de haute disponibilité contiennent les FQDN du serveur de médiation et les adresses IP du site PSTN. De nouveaux enregistrements DNS A sont ajoutés au serveur AD pour les adresses IP du serveur de médiation. Les nouveaux éléments de topologie sont mis à jour dans le magasin central de gestion pour les noms de service et les adresses IP du serveur de médiation. 
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Publish-CcAppliance n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

