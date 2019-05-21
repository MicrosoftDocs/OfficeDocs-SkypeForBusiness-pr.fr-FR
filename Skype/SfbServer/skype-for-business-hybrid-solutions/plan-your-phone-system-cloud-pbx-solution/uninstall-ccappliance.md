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
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'L’applet de commande Uninstall-CcAppliance désinstalle l’exécution de l’appliance de la version Cloud Connector de Skype Entreprise à partir du serveur hôte. '
ms.openlocfilehash: 337c5c489846facb1da3c177cac7a965d7550ae5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286893"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
L’applet de commande Uninstall-CcAppliance désinstalle l’exécution de l’appliance de la version Cloud Connector de Skype Entreprise à partir du serveur hôte.  
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

Dans l’exemple suivant, l’appareil Cloud Connector est vidé et désinstallé du serveur hôte:
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a>Exemple 2

L’exemple qui suit draine et force la désinstallation de l’application Cloud Connector sur le serveur hôte même si le processus de drainage a échoué:
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Exemple 3

Dans l’exemple suivant, la version de sauvegarde du connecteur Cloud est désinstallée sans confirmation de l’utilisateur:
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Si vous désinstallez la version actuelle du Cloud Connector, les services de drainage s’exécutent pour la première fois sur le serveur de médiation et sur le serveur Edge pour permettre aux appels concurrents de se terminer avant de désinstaller les machines virtuelles. Si vous êtes en train de désinstaller une version de sauvegarde, le nettoyage n'est pas exécuté :
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| Version <br/> | Facultatif <br/> |System.String  <br/> | Version de Cloud Connector qui sera désinstallée à partir du serveur hôte. Si cela n'est pas précisé, désinstallez la version actuelle. <br/> |
|Force  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Si vous désinstallez la version actuelle, essayez de nettoyer les serveurs sur le serveur de médiation et le serveur Edge avant de désinstaller les machines virtuelles. Si vous spécifiez le commutateur "Force", même si les services de nettoyage échouent, les machines virtuelles seront désinstallées. Ce paramètre est uniquement utilisé pour désinstaller la version actuelle.  <br/> |
|Confirm  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Demandez confirmation à l’utilisateur de désinstaller les machines virtuelles. La valeur par défaut est TRUE.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Uninstall-CcAppliance n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

