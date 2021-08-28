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
ms.localizationpriority: medium
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: LPublish-CcAppliance cmdlet obtient les informations de haute disponibilité de la configuration du client en ligne et les publie sur l’appliance Skype Entreprise Cloud Connector Edition sur le serveur hôte.
ms.openlocfilehash: d1cd8d3ff9a47d10089ee3ea64d0db576845a708
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589988"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
LPublish-CcAppliance cmdlet obtient les informations de haute disponibilité de la configuration du client en ligne et les publie sur l’appliance Skype Entreprise Cloud Connector Edition sur le serveur hôte. 
  
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

Aucune
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

