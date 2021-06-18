---
title: Effectuer une mise à niveau vers une nouvelle version de Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Découvrez comment mettre à niveau votre déploiement de la version Cloud Connector.
ms.openlocfilehash: fea78c6b1b6ba3b2e644fef71d78b94aa3a244b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109130"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Effectuer une mise à niveau vers une nouvelle version de Cloud Connector

> [!Important]
> Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online. Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams à l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)
 
Découvrez comment mettre à niveau votre déploiement de la version Cloud Connector.
  
Si vous avez installé un compte client de gestion en ligne et activé les mises à jour automatiques, votre déploiement existant de Skype Entreprise, version Cloud Connector sera automatiquement mise à niveau vers la version la plus récente, en fonction de la configuration de votre fenêtre de temps de mise à jour automatique. Vous pouvez également effectuer une mise à niveau manuelle. 
  
Les versions 1.4.1 et ultérieures de Cloud Connector effectuent des mises à jour automatiques par défaut. Si vous souhaitez mettre à niveau vers la dernière version (2.1) manuellement, voir Mettre à niveau un site unique vers une [nouvelle version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) plus loin dans cette rubrique.
  
La mise à jour automatique nécessite que le service Cloud Connector soit en cours d’exécution. Les étapes suivantes décrivent le processus de mise à jour automatique :
  
- Le processus de mise à jour automatique s’exécute en fonction de la planification que vous avez configurée pour les mises à jour automatiques.
    
- Tâches de mise à jour du système d’exploitation
    
  - Vérifiez et téléchargez les mises à jour du système d’exploitation sur toutes les VM Cloud Connector. 
    
  - Installez et mettez à jour toutes les VM Cloud Connector une par une, puis redémarrez.
    
  - Après le redémarrage des VM Cloud Connector, vérifiez si un autre redémarrage est nécessaire.
    
  - Une fois que les machines VM Cloud Connector ont été correctement corrigés, répétez le processus pour l’ordinateur hôte Cloud Connector.
    
  - Une fois l’ordinateur hôte Cloud Connector correctement lancé, toutes les tâches de mise à jour du système d’exploitation en suspens sont terminées.
    
- Tâches de mise à jour cloud Connector
    
  - Téléchargez et vérifiez le fichier de version à partir du site de téléchargement.
    
  - Téléchargez le fichier .msi de la nouvelle version. 
    
  - Désinstallez l’ancien fichier msi ; installez le nouveau fichier msi.
    
  - Téléchargez la nouvelle version de Skype Entreprise Bits.
    
  - Enregistrez l’appliance en appelant Register-CcAppliance.
    
  - Installez la nouvelle version de Cloud Connector.
    
  - Drainez l’ancienne appliance et basculez la connexion réseau vers la nouvelle appliance.
    
> [!NOTE]
>  Lorsque Cloud Connector est mis à jour vers une nouvelle build, il se peut que les cmdlets Cloud Connector ne soient pas mises à jour. Cela peut se produire, par exemple, si une fenêtre PowerShell reste ouverte pendant la mise à jour automatique. Pour charger les cmdlets mises à jour, vous pouvez exécuter l’une des étapes suivantes : > Fermez PowerShell sur l’appliance Cloud Connector, puis rouvrez PowerShell.> Ou, vous pouvez exécuter Import-Module CloudConnector -Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Mettre à niveau un site unique vers une nouvelle version
<a name="BKMK_Upgrade"> </a>

S’il n’existe qu’une seule appliance dans le site que vous souhaitez mettre à niveau, faites les choses suivantes :
  
1. Désinstallez la version Cloud Connector existante dans programmes et fonctionnalités du Panneau **\> de \> contrôle.**
    
2. Installez la nouvelle version de CloudConnector.msi à partir [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) de .
    
3. Confirmez que vous avez le fichier CloudConnector.ini pour la version que vous installez et que vous avez mis à jour toutes les valeurs requises pour votre environnement. Vous ne pouvez pas utiliser le fichier .ini d’une version précédente. Si vous êtes en cours de mise à niveau de Cloud Connector, reportez-vous à la rubrique Préparer votre appliance [Cloud Connector](prepare-your-cloud-connector-appliance.md) et assurez-vous que SiteName et EnableReferSupport sont définies sur la valeur correcte dans le fichier CloudConnector.ini.
    
4. Démarrez une console PowerShell en tant qu’administrateur et exécutez l’cmdlet suivante pour inscrire l’appliance actuelle :
    
   ```powershell
   Register-CcAppliance
   ```

5. Exécutez l’cmdlet suivante pour télécharger la dernière version :
    
   ```powershell
   Start-CcDownload
   ```

6. Exécutez l’cmdlet suivante pour démarrer l’installation : 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. Exécutez l’cmdlet suivante pour activer le nouveau déploiement et désactiver la version précédente :
    
   ```powershell
   Switch-CcVersion
   ```

S’il existe plusieurs appliances dans le site, suivez les étapes précédentes pour mettre à niveau chaque appliance une par une.
  
Si vous souhaitez mettre à jour les informations d’identification d’administrateur de domaine, d’administrateur d’ordinateur virtuel, d’administrateur en mode sans échec et d’administrateur client, vous pouvez exécuter l’cmdlet avec le paramètre  _UpdateAllCredentials_ pour réinitialiser toutes les informations d’identification :
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

Ensuite, lorsque vous commencez à mettre à niveau vers une nouvelle version, vous êtes promu pour entrer les nouvelles informations d’identification. 
  
Si vous souhaitez uniquement réinitialiser vos informations d’identification d’administrateur client, exécutez l’cmdlet suivante :
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Mettre à niveau plusieurs sites vers une nouvelle version
<a name="BKMK_Upgrade"> </a>

Suivez les étapes de mise à niveau d’un site unique, mise à niveau d’un site à la fois pour chaque site de votre déploiement. Assurez-vous et [validez votre déploiement Cloud Connector après](validate-your-cloud-connector-deployment.md) la mise à niveau de chaque site.
