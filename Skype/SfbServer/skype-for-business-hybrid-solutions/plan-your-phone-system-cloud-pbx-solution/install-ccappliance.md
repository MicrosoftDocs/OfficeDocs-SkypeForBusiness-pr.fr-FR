---
title: Install-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: "	L'applet de commande Install-CcAppliance installe l’appliance de la version Cloud Connector de Skype Entreprise, notamment les machines virtuelles de l’AD, du magasin central de gestion, du serveur de médiation et du serveur Edge, sur le serveur hôte. "
ms.openlocfilehash: 01c689c4a4639c12292d59def6b698281f402299
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287271"
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

### <a name="example-1"></a>Exemple 1

Dans l’exemple suivant, une nouvelle application de connecteur Cloud est installée sur le serveur hôte:
  
```
Install-CcAppliance
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant met à niveau le Cloud Connector vers la version la plus récente:
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Exemple 3

Dans l’exemple suivant, toutes les informations d’identification Cloud Connector sont supprimées sur le serveur hôte, inviter l’utilisateur à spécifier de nouveau toutes les informations d’identification, puis installe Cloud Connector:
  
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

L’exemple suivant crée des fichiers de configuration pour chaque étape de déploiement sur le serveur hôte. Les fichiers de configuration sont enregistrés \<dans\>le\\dossier\>ApplianceRoot \Instances <Version-default\ExportedConfig sur le serveur hôte:
  
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
  
Install-CcAppliance -ShowStepsOnly
  
## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de contrôle install-CcAppliance est utilisée pour déployer le Cloud Connector sur une nouvelle application ou pour mettre à niveau un appareil existant vers la version la plus récente.
  
Si vous disposez d’une nouvelle appliance, commencez par lire Préparation de votre environnement pour Cloud Connector, exécutez l’applet de commande Register-CcAppliance afin d’enregistrer l’appliance, puis exécutez l’applet de commande Install-CcAppliance. Pour plus d’informations, reportez-vous à la rubrique [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) et [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
Si vous avez un déploiement de Cloud Connector et que vous souhaitez effectuer une mise à niveau, suivez les instructions de la procédure de [mise à niveau vers une nouvelle version de Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> | Création de fichiers de configuration pour chaque étape de déploiement. Ce paramètre est uniquement fourni à des fins de résolution de problèmes.  <br/> |
|ShowStepsOnly  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Affichage des noms des étapes de déploiement uniquement. Ce paramètre est uniquement fourni à des fins de résolution de problèmes.  <br/> |
|SkipExistingObjects  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Ce paramètre doit être utilisé conjointement avec le paramètre Étapes. Ce paramètre est uniquement fourni à des fins de résolution de problèmes.  <br/> |
|Étapes  <br/> |Facultatif  <br/> |System.Array  <br/> |Exécution des étapes de déploiement. Ce paramètre est uniquement fourni à des fins de résolution de problèmes.  <br/> |
|Mise à niveau  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Mise à niveau du Cloud Connector existant vers la dernière version.  <br/> |
|Mise à jour de toutes les informations  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Supprimez toutes les informations d’identification Cloud Connector dans le cache. Demandez à l’utilisateur de spécifier de nouvelles informations pour l’installation.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Install-CcAppliance n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

