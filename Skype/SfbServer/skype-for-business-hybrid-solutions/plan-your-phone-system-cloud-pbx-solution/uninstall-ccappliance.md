---
title: CcAppliance-désinstaller
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'L’applet de commande Uninstall-CcAppliance désinstalle l’exécution de l’appliance de la version Cloud Connector de Skype Entreprise à partir du serveur hôte. '
ms.openlocfilehash: 325e21d28ef87f9d27e87721452bc3d67d197169
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="uninstall-ccappliance"></a>CcAppliance-désinstaller
 
L’applet de commande Uninstall-CcAppliance désinstalle l’exécution de l’appliance de la version Cloud Connector de Skype Entreprise à partir du serveur hôte.  
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant drains et désinstalle l’application Connecteur de nuage à partir du serveur hôte :
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant drains et force désinstalle la solution matérielle-logicielle nuage connecteur en cours d’exécution sur le serveur hôte même si le processus de drain a échoué :
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Exemple 3

L’exemple suivant désinstalle une version de sauvegarde de nuage connecteur sans demande de confirmation de l’utilisateur :
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Si vous désinstallez la version actuelle en cours d’exécution du connecteur du nuage, services de drain sont tout d’abord exécutées sur le serveur de médiation et le serveur de transport Edge pour permettre les appels simultanés terminer avant de désinstaller les ordinateurs virtuels. Si vous êtes en train de désinstaller une version de sauvegarde, le nettoyage n'est pas exécuté :
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type de**|**Description**|
|:-----|:-----|:-----|:-----|
| Version <br/> | Facultatif <br/> |System.String  <br/> | La version du connecteur de nuage qui va être désinstallé à partir du serveur hôte. Si cela n'est pas précisé, désinstallez la version actuelle. <br/> |
|Force  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Si vous désinstallez la version actuelle, essayez de nettoyer les serveurs sur le serveur de médiation et le serveur Edge avant de désinstaller les machines virtuelles. Si vous spécifiez le commutateur "Force", même si les services de nettoyage échouent, les machines virtuelles seront désinstallées. Ce paramètre est uniquement utilisé pour désinstaller la version actuelle.  <br/> |
|Confirm  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Demander confirmation de l’utilisateur pour désinstaller les ordinateurs virtuels. La valeur par défaut est TRUE.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Uninstall-CcAppliance n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Installation-CcAppliance](install-ccappliance.md)
  
[Publication-CcAppliance](publish-ccappliance.md)
  
[Registre-CcAppliance](register-ccappliance.md)
  
[Annuler l’inscription-CcAppliance](unregister-ccappliance.md)
  

