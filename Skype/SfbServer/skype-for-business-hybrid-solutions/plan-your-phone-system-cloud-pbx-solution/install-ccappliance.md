---
title: Install-CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: "	L'applet de commande Install-CcAppliance installe l’appliance de la version Cloud Connector de Skype Entreprise, notamment les machines virtuelles de l’AD, du magasin central de gestion, du serveur de médiation et du serveur Edge, sur le serveur hôte. "
ms.openlocfilehash: d35a102f7d3ade7b64bcf43388eaf03dc455c27b
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569986"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
	L'applet de commande Install-CcAppliance installe l’appliance de la version Cloud Connector de Skype Entreprise, notamment les machines virtuelles de l’AD, du magasin central de gestion, du serveur de médiation et du serveur Edge, sur le serveur hôte.  
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant installe un nouveau matériel nuage connecteur sur le serveur hôte :
  
```
Install-CcAppliance
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant met à niveau dans le nuage connecteur vers la dernière version :
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Exemple 3

L’exemple suivant supprime toutes les informations d’identification de nuage connecteur mis en cache sur le serveur hôte, invite l’utilisateur à spécifier toutes les informations d’identification et puis installe le connecteur de nuage :
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>Exemple 4

L'exempe suivant affiche toutes les étapes de déploiement dans la console PowerShell :
  
```
Install-CcAppliance -ShowStepsOnly
```

Le paramètre ShowStepsOnly est uniquement dédié à la résolution de problèmes.
  
### <a name="example-5"></a>Exemple 5

L’exemple suivant crée des fichiers de configuration pour chaque étape de déploiement sur le serveur hôte. Fichiers de configuration sont enregistrés dans le \<ApplianceRoot\>\Instances\\< Version\>-dossier default\ExportedConfig sur le serveur hôte :
  
```
Install-CcAppliance -PrepareOnly
```

Pour déterminer la racine de l’appliance, exécutez l’applet de commande Get-CcApplianceDirectory.  
  
### <a name="example-6"></a>Exemple 6

Dans l’exemple suivant, Cloud Connector exécute les étapes 1,2 et 3 de déploiement pour créer des commutateurs virtuels, une machine virtuelle AD et installer le service de domaine sur le serveur AD. Il passe l’étape si elle a déjà été exécutée :
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

Le paramètre SkipExistingObjects doit être utilisé conjointement avec le paramètre Étapes.
  
> [!NOTE]
> Le paramètre Étapes est uniquement fourni à des fins de résolution de problèmes. N’utilisez pas ce paramètre pour déployer une appliance ou mettre à niveau une appliance en service. 
  
Pour déterminer les étapes du déploiement, exécutez la commande suivante :
  
Install-CcAppliance - ShowStepsOnly
  
## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de commande Install-CcAppliance est utilisé pour déployer dans le nuage connecteur sur un nouveau matériel ou mise à niveau une appliance existante vers la version la plus récente.
  
Si vous disposez d’une nouvelle appliance, commencez par lire Préparation de votre environnement pour Cloud Connector, exécutez l’applet de commande Register-CcAppliance afin d’enregistrer l’appliance, puis exécutez l’applet de commande Install-CcAppliance. Pour plus d’informations, voir [déployer un seul site dans le nuage connecteur](deploy-a-single-site-in-cloud-connector.md) et le [déploiement de plusieurs sites dans le nuage connecteur](deploy-multiple-sites-in-cloud-connector.md). 
  
Si vous disposez d’un déploiement existant du nuage connecteur et que vous souhaitez mettre à niveau, suivez les instructions de [mise à niveau vers une nouvelle version du nuage connecteur](upgrade-to-a-new-version-of-cloud-connector.md).
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> | Création de fichiers de configuration pour chaque étape de déploiement. Ce paramètre est uniquement fourni à des fins de résolution de problèmes.  <br/> |
|ShowStepsOnly  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Affichage des noms des étapes de déploiement uniquement. Ce paramètre est uniquement fourni à des fins de résolution de problèmes.  <br/> |
|SkipExistingObjects  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Ce paramètre doit être utilisé conjointement avec le paramètre Étapes. Ce paramètre est uniquement fourni à des fins de résolution de problèmes.  <br/> |
|Étapes  <br/> |Facultatif  <br/> |System.Array  <br/> |Exécution des étapes de déploiement. Ce paramètre est uniquement fourni à des fins de résolution de problèmes.  <br/> |
|Mise à niveau  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Mise à niveau du Cloud Connector existant vers la dernière version.  <br/> |
|UpdateAllCredentials  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Supprimer toutes les informations d’identification sur le nuage connecteur dans le cache. Demandez à l’utilisateur de spécifier de nouvelles informations pour l’installation.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Install-CcAppliance n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[CcAppliance publier](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[CcAppliance annuler l’inscription](unregister-ccappliance.md)
  
[CcAppliance désinstaller](uninstall-ccappliance.md)
  

