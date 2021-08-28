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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: La cmdlet Install-CcAppliance installe l’appliance Skype Entreprise Cloud Connector Edition,y compris les machines virtuelles AD, Central Management Store, Mediation Server et Edge Server, sur le serveur hôte.
ms.openlocfilehash: 0ed13282039b84975bea3e26f5ae1d7f79122a11
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635838"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
La cmdlet Install-CcAppliance installe l’appliance Skype Entreprise Cloud Connector Edition,y compris les machines virtuelles AD, Central Management Store, Mediation Server et Edge Server, sur le serveur hôte. 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant installe une nouvelle appliance Cloud Connector sur le serveur hôte :
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant permet de mettre à niveau Cloud Connector vers la dernière version :
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Exemple 3

L’exemple suivant supprime toutes les informations d’identification Cloud Connector mises en cache sur le serveur hôte, invite l’utilisateur à spécifier à nouveau toutes les informations d’identification, puis installe Cloud Connector :
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>Exemple 4

L’exemple suivant affiche toutes les étapes de déploiement dans la console PowerShell :
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

Le paramètre -ShowStepsOnly est uniquement pour la résolution des problèmes.
  
### <a name="example-5"></a>Exemple 5

L’exemple suivant génère des fichiers de configuration pour chaque étape de déploiement sur le serveur hôte. Les fichiers de configuration sont enregistrés dans \<ApplianceRoot\> le dossier \Instances \\<Version \> -default\ExportedConfig sur le serveur hôte :
  
```powershell
Install-CcAppliance -PrepareOnly
```

Pour déterminer la racine de l’appliance, exécutez Get-CcApplianceDirectory cmdlet. 
  
### <a name="example-6"></a>Exemple 6

Dans l’exemple suivant, Cloud Connector exécute les étapes de déploiement 1, 2 et 3 pour créer des commutateurs virtuels, créer une machine virtuelle AD et installer le service de domaine sur le serveur AD. Il ignore l’étape si l’étape a déjà été exécutée :
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

Le paramètre SkipExistingObjects doit être utilisé conjointement avec le paramètre Steps.
  
> [!NOTE]
> Le paramètre Steps est uniquement à des fins de dépannage. N’utilisez pas ce paramètre pour déployer une appliance ou mettre à niveau une appliance en service. 
  
Pour déterminer les étapes du déploiement, exécutez la commande suivante :
  
Install-CcAppliance -ShowStepsOnly
  
## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

LInstall-CcAppliance cmdlet est utilisée pour déployer Cloud Connector sur une nouvelle appliance ou pour mettre à niveau une appliance existante vers la dernière version.
  
Si vous avez une nouvelle appliance, lisez d’abord Préparer votre environnement pour Cloud Connector, exécutez l’cmdlet Register-CcAppliance pour inscrire l’appliance, puis exécutez l'Install-CcAppliance cmdlet. Pour plus d’informations, voir [Déployer un seul site dans Cloud Connector](deploy-a-single-site-in-cloud-connector.md) et Déployer plusieurs sites dans Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md) 
  
Si vous avez un déploiement existant de Cloud Connector et que vous souhaitez mettre à niveau, suivez les instructions de la mise à niveau vers une [nouvelle version de Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> | Générer des fichiers de configuration pour chaque étape de déploiement. Ce paramètre est uniquement pour la résolution des problèmes. <br/> |
|ShowStepsOnly  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Afficher uniquement les noms des étapes de déploiement. Ce paramètre est uniquement pour la résolution des problèmes.  <br/> |
|SkipExistingObjects  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Ce paramètre doit être utilisé conjointement avec le paramètre Steps. Ce paramètre est uniquement pour la résolution des problèmes.  <br/> |
|Étapes  <br/> |Facultatif  <br/> |System.Array  <br/> |Exécutez les étapes de déploiement. Ce paramètre est uniquement pour la résolution des problèmes.  <br/> |
|Mise à niveau  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Mettre à niveau le Cloud Connector existant vers la dernière version.  <br/> |
|UpdateAllCredentials  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Supprimez toutes les informations d’identification Cloud Connector dans le cache. Invitez l’utilisateur à spécifier de nouvelles informations d’identification pour l’installation.  <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Install-CcAppliance n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

