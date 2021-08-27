---
title: Unregister-CcAppliance
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
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: La cmdlet Unregister-CcAppliance désinsère l’appliance Skype Entreprise Cloud Connector Edition jour à partir d’un site PSTN dans la configuration du client en ligne.
ms.openlocfilehash: c48a7b53d757dab446a8939a3e3203d8e66fccab
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603653"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
La cmdlet Unregister-CcAppliance désinsère l’appliance Skype Entreprise Cloud Connector Edition jour à partir d’un site PSTN dans la configuration du client en ligne.
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant désinsère une appliance actuelle de la configuration du client en ligne :
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant vérifie la configuration pour la désinsister localement sans se connecter à la configuration du client en ligne :
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>Exemple 3

L’exemple suivant désinsère l’appliance actuelle avec le nom « Appliance1 » sur le site PSTN « Site1 » :
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

À l'Register-CcAppliance, SiteName associé au nom de groupe externe du serveur Edge dans le fichier CloudConnector.ini est considéré comme une identité de site PSTN. De même, ApplianceName combiné au nom de CloudConnector.ini serveur de médiation est considéré comme une identité d’appliance.
  
Une fois l’appliance désinsérée, redémarrez le service de gestion Cloud Connector et connectez-vous en tant que compte NetworkService.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |Facultatif  <br/> |System.String  <br/> |Nom du site PSTN où l’appliance est inscrite. La valeur par défaut est La valeur SiteName dans CloudConnector.ini fichier.  <br/> |
|ApplianceName  <br/> |Facultatif  <br/> |System.String  <br/> |Nom de l’appliance actuelle. La valeur par défaut est le nom de l’ordinateur du serveur hôte.  <br/> |
|Local  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Vérifiez la configuration de l’inscription localement sans vous connecter à une configuration client en ligne.  <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Unregister-CcAppliance n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

