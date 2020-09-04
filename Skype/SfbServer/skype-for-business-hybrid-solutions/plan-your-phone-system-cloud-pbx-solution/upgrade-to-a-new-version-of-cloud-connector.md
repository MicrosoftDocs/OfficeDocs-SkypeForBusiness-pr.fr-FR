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
description: Découvrez comment mettre à niveau votre déploiement de Cloud Connector Edition.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359290"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Effectuer une mise à niveau vers une nouvelle version de Cloud Connector

> [!Important]
> La version Cloud Connector sera déconnectée le 31 juillet 2021 avec Skype entreprise online. Une fois que votre organisation a effectué la mise à niveau vers Teams, Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).
 
Découvrez comment mettre à niveau votre déploiement de Cloud Connector Edition.
  
Si vous avez configuré un compte client de gestion en ligne et activé les mises à jour automatiques, votre déploiement existant de Skype entreprise, version Cloud Connector, sera automatiquement mis à niveau vers la version la plus récente, en fonction de la configuration de la fenêtre de mise à jour automatique. Vous pouvez également effectuer une mise à niveau manuelle. 
  
La version de Cloud Connector version 1.4.1 et les versions ultérieures effectuent des mises à jour automatiques par défaut. Si vous souhaitez effectuer une mise à niveau vers la dernière version (2,1) manuellement, consultez la rubrique [mise à niveau d’un site unique vers une nouvelle version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) plus loin dans cette rubrique.
  
La mise à jour automatique nécessite que le service Cloud Connector soit en cours d’exécution. Les étapes suivantes décrivent le processus de mise à jour automatique :
  
- Le processus de mise à jour automatique s’exécute en fonction de la planification que vous avez configurée pour les mises à jour automatiques.
    
- Tâches de mise à jour du système d’exploitation
    
  - Vérifiez et téléchargez les mises à jour du système d’exploitation sur tous les ordinateurs virtuels Cloud Connector. 
    
  - Installez et mettez à jour tous les ordinateurs virtuels Cloud Connector un par un et redémarrez.
    
  - Après le redémarrage des machines virtuelles de Cloud Connector, vérifiez si un autre redémarrage est nécessaire.
    
  - Une fois que les machines virtuelles Cloud Connector ont été mises à jour avec succès, répétez le processus pour l’ordinateur hôte Cloud Connector.
    
  - Une fois que la machine hôte Cloud Connector s’est exécutée correctement, toutes les tâches de mise à jour du système d’exploitation en suspens sont effectuées.
    
- Tâches de mise à jour de Cloud Connector
    
  - Téléchargez et vérifiez le fichier de version à partir du site de téléchargement.
    
  - Téléchargez le fichier. msi de la nouvelle version. 
    
  - Désinstallez l’ancien fichier MSI ; Installez le nouveau fichier msi.
    
  - Téléchargez la nouvelle version de Skype entreprise bits.
    
  - Inscrivez l’appliance en appelant Register-applet ccappliance.
    
  - Installez la nouvelle version de Cloud Connector.
    
  - Déchargez l’ancien matériel et basculez la connexion réseau vers le nouveau matériel.
    
> [!NOTE]
>  Lorsque Cloud Connector est mis à jour vers une nouvelle version, les cmdlets de Cloud Connector ne sont peut-être pas mises à jour. Cela peut se produire, par exemple, si une fenêtre PowerShell est laissée ouverte pendant que la mise à jour automatique se produit. Pour charger les applets de commande mises à jour, vous pouvez effectuer l’une des opérations suivantes : > fermer PowerShell sur l’appliance Cloud Connector, puis rouvrir PowerShell. > ou exécuter import-module CloudConnector-force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Mettre à niveau un site unique vers une nouvelle version
<a name="BKMK_Upgrade"> </a>

S’il n’y a qu’une seule Appliance dans le site que vous souhaitez mettre à niveau, procédez comme suit :
  
1. Désinstallez la version de Cloud Connector existante dans programmes **du panneau de configuration programmes \> \> et fonctionnalités**.
    
2. Installez la nouvelle version de CloudConnector.msi à partir de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .
    
3. Vérifiez que vous disposez du fichier de CloudConnector.ini pour la version que vous installez et que vous avez mis à jour toutes les valeurs requises pour votre environnement. Vous ne pouvez pas utiliser le fichier. ini d’une version précédente. Si vous mettez à niveau Cloud Connector, reportez-vous à la rubrique [Prepare Your Cloud Connector Appliance](prepare-your-cloud-connector-appliance.md) et assurez-vous que SiteName and EnableReferSupport sont définis sur la valeur correcte dans le fichier CloudConnector.ini.
    
4. Démarrez une console PowerShell en tant qu’administrateur et exécutez l’applet de commande suivante pour enregistrer l’appliance actuelle :
    
   ```powershell
   Register-CcAppliance
   ```

5. Exécutez l’applet de commande suivante pour télécharger la dernière version :
    
   ```powershell
   Start-CcDownload
   ```

6. Exécutez l’applet de commande suivante pour démarrer l’installation : 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. Exécutez l’applet de commande suivante pour activer le nouveau déploiement et désactiver la version précédente :
    
   ```powershell
   Switch-CcVersion
   ```

S’il y a plusieurs Appliances dans le site, suivez les étapes précédentes pour mettre à niveau chaque appliance une par une.
  
Si vous souhaitez mettre à jour les informations d’identification de l’administrateur de domaine, de l’administrateur de la machine virtuelle, du mode sans échec et de l’administrateur client, vous pouvez exécuter l’applet de commande avec le paramètre  _UpdateAllCredentials_ pour réinitialiser toutes les informations d’identification :
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

Ensuite, lorsque vous commencez à effectuer une mise à niveau vers une nouvelle version, vous serez invité à entrer les nouvelles informations d’identification. 
  
Si vous souhaitez uniquement réinitialiser les informations d’identification d’administrateur de client, exécutez l’applet de commande suivante :
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Mettre à niveau plusieurs sites vers une nouvelle version
<a name="BKMK_Upgrade"> </a>

Suivez les étapes de mise à niveau d’un site unique, mettant à niveau un site à la fois pour chaque site de votre déploiement. Assurez-vous et [validez votre déploiement de Cloud Connector après la](validate-your-cloud-connector-deployment.md) mise à niveau de chaque site.
  

