---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: La cmdlet Uninstall-CcAppliance désinstalle l’appliance de la version Cloud Connector de Skype Entreprise en cours d’exécution du serveur hôte.
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824138"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
La cmdlet Uninstall-CcAppliance désinstalle l’appliance de la version Cloud Connector de Skype Entreprise en cours d’exécution du serveur hôte. 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant draine et désinstalle l’appliance Cloud Connector du serveur hôte :
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant draine et force la désinstallation de l’appliance Cloud Connector en cours d’exécution sur le serveur hôte, même si le processus de drainage a échoué :
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Exemple 3

L’exemple suivant désinstalle une version de sauvegarde Cloud Connector sans confirmation de l’utilisateur :
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Si vous désinstallez la version actuelle de Cloud Connector, les services de drainage sont d’abord exécutés sur le serveur de médiation et le serveur Edge pour laisser les appels simultanés se terminer avant de désinstaller les machines virtuelles. Si vous désinstallez une version de sauvegarde, le drainage n’est pas effectué.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| Version <br/> | Facultatif <br/> |System.String  <br/> | Version de Cloud Connector qui sera désinstallée du serveur hôte. Si elle n’est pas spécifiée, désinstallez la version en cours d’exécution. <br/> |
|Force  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Si vous désinstallez la version en cours d’exécution, essayez de vider les serveurs sur le serveur de médiation et le serveur Edge avant de désinstaller les ordinateurs virtuels. Si vous spécifiez le commutateur « Force », même si les services de drainage échouent, les machines virtuelles sont désinstallées. Ce paramètre est utilisé uniquement pour désinstaller la version en cours d’exécution.  <br/> |
|Confirmer  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Demandez la confirmation de l’utilisateur pour désinstaller les machines virtuelles. La valeur par défaut est TRUE.  <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Uninstall-CcAppliance n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

