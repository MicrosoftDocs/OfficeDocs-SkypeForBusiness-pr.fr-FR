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
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: L’applet de commande Unregister-CcAppliance annule l’inscription de l’appliance actuelle de la version Cloud Connector de Skype Entreprise à partir d’un site RTC dans la configuration client en ligne.
ms.openlocfilehash: 2bd8f3a3ef4ac2b29ab9e7d766836d7a3555c0f4
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003134"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
L’applet de commande Unregister-CcAppliance annule l’inscription de l’appliance actuelle de la version Cloud Connector de Skype Entreprise à partir d’un site RTC dans la configuration client en ligne.
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant annule l’inscription d’une appliance actuelle à partir de la configuration client en ligne :
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant vérifie la configuration d’annulation d’inscription sans connexion à une configuration client en ligne :
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>Exemple 3

L’exemple suivant annule l’inscription de l’appliance actuelle avec le nom « Appliance1 » vers le site RTC « Site1 » :
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Identique à l’applet de commande Register-CcAppliance, SiteName associé au FQDN externe du serveur Edge dans le fichier .ini de CloudConnector est considéré comme une identité de site RTC. De même, ApplianceName associé au FQDN du serveur de médiation dans le fichier .ini de CloudConnector est considéré comme une identité d’appliance.
  
Après l’annulation de l’inscription de l’application, redémarrez le service de gestion des connecteurs Cloud et connectez-vous en tant que compte NetworkService.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |Facultatif   <br/> |System.String  <br/> |Le nom du site RTC où l’appliance est enregistrée. La valeur par défaut est la valeur SiteName dans le fichier CloudConnector.ini.  <br/> |
|ApplianceName  <br/> |Facultatif   <br/> |System.String  <br/> |Nom de l’appliance actuelle. La valeur par défaut est le nom de l’ordinateur du serveur hôte.  <br/> |
|Local  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Vérifiez la configuration d’inscription locale sans connexion à une configuration client en ligne.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Unregister-CcAppliance n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

