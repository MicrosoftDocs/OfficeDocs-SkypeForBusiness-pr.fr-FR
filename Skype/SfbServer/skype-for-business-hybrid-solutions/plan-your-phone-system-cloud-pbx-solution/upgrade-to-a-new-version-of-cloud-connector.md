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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Découvrez comment mettre à niveau le déploiement de votre édition Cloud Connector.
ms.openlocfilehash: c2613069f1626f8fc7e28b4fb5a246fc7647cf98
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286626"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Upgrade to a new version of Cloud Connector
 
Découvrez comment mettre à niveau le déploiement de votre édition Cloud Connector.
  
Si vous avez configuré un compte client de gestion en ligne et activé les mises à jour automatiques, votre déploiement existant de Skype Entreprise, version Cloud Connector sera mis à niveau vers la dernière version automatiquement, en fonction de votre configuration de fenêtre de délai de mise à jour automatique. Vous pouvez également effectuer manuellement la mise à niveau. 
  
Dans le Cloud Connector Edition 1.4.1 et versions ultérieures, les mises à jour automatiques sont exécutées par défaut. Si vous voulez effectuer une mise à niveau vers la dernière version (2,1) manuellement, voir [mettre à niveau un seul site vers une nouvelle version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) plus loin dans cette rubrique.
  
La mise à jour automatique nécessite le fonctionnement du service de connecteur Cloud. Les étapes suivantes décrivent le processus de mise à jour automatiques :
  
- Le processus de mise à jour automatique fonctionnera en fonction de la planification que vous avez configurée pour les mises à jour automatiques.
    
- Tâches de mise à jour du système d'exploitation
    
  - Vérifier et télécharger les mises à jour du système d’exploitation sur tous les ordinateurs virtuels du Cloud Connector. 
    
  - Installez et mettez à jour tous les ordinateurs virtuels Cloud Connector un par un, puis redémarrez.
    
  - Après le redémarrage des VM sur le Cloud Connector, vérifiez si un autre redémarrage est nécessaire.
    
  - Une fois les ordinateurs virtuels du connecteur Cloud correctement corrigés, répétez le processus pour l’ordinateur hôte du Cloud Connector.
    
  - Une fois l’ordinateur hôte du connecteur Cloud démarré, toutes les tâches de mise à jour du système d’exploitation en attente sont effectuées.
    
- Tâches de mise à jour de Cloud Connector
    
  - Téléchargez et vérifiez le fichier de version à partir du site de téléchargement.
    
  - Téléchargez le fichier .msi de la nouvelle version.  
    
  - Désinstaller l’ancien fichier MSI; Installez le nouveau fichier msi.
    
  - Téléchargez la nouvelle version de Skype entreprise bits.
    
  - Enregistrez l’appliance en appelant Register-CcAppliance.
    
  - Installez la nouvelle version Cloud Connector.
    
  - Nettoyez l’ancienne appliance puis basculez la connexion réseau vers la nouvelle appliance.
    
> [!NOTE]
>  Lors de la mise à jour d’un connecteur Cloud vers une nouvelle version, il est possible que les applets de construction Cloud Connector ne soient pas mises à jour. Cela peut se produire, par exemple, si une fenêtre PowerShell reste ouverte lors de la mise à jour automatique. Pour charger les applets de commande mises à jour, vous pouvez effectuer l’une des opérations suivantes: > Fermez PowerShell sur le périphérique Cloud Connector, puis rouvrez PowerShell. > ou vous pouvez exécuter import-module CloudConnector-force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Mise à niveau d’un site unique vers une nouvelle version
<a name="BKMK_Upgrade"> </a>

Si le site comporte un seul équipement que vous souhaitez mettre à niveau, procédez comme suit :
  
1. Désinstallez la version actuelle du connecteur Cloud dans programmes **et fonctionnalités du panneau de \> \> configuration**.
    
2. Installez la nouvelle version de CloudConnector. msi à [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)partir de.
    
3. Vérifiez que vous disposez du fichier CloudConnector.ini pour la version que vous installez et que les valeurs requises pour votre environnement sont mises à jour. Vous ne pouvez pas utiliser le fichier .ini d’une version précédente. Si vous effectuez une mise à niveau vers le Cloud Connector, reportez-vous à la rubrique [préparer votre appareil de connexion Cloud](prepare-your-cloud-connector-appliance.md) et assurez-vous que SiteName et EnableReferSupport sont définis sur la valeur correcte dans le fichier CloudConnector. ini.
    
4. Démarrez une console PowerShell en tant qu’administrateur et exécutez l’applet de commande suivante pour enregistrer l’appliance actuelle :
    
   ```
   Register-CcAppliance
   ```

5. Exécutez l’applet de commande suivante pour télécharger la dernière version :
    
   ```
   Start-CcDownload
   ```

6. Exécutez l’applet de commande suivante pour démarrer l’installation :  
    
   ```
   Install-CcAppliance -Upgrade
   ```

7. Exécutez l’applet de commande suivante pour activer le nouveau déploiement et désactiver la version précédente :
    
   ```
   Switch-CcVersion
   ```

Si le site comporte plusieurs équipements, suivez la procédure précédente pour les mettre à niveau l’un après l’autre.
  
Si vous voulez mettre à jour les informations d’identification de l’administrateur de domaine, de l’administrateur de l’ordinateur virtuel, de l’administrateur du mode sans échec et de l’administrateur client, vous pouvez exécuter l’applet de connexion avec le paramètre _UpdateAllCredentials_ pour réinitialiser toutes les informations d’identification:
  
```
Install-CcAppliance -UpdateAllCredentials
```

Puis, lors de la mise à niveau vers la nouvelle version, vous serez invité à saisir les nouvelles informations d’identification.  
  
Si vous souhaitez réinitialiser uniquement les informations d’identification d’administrateur de clients, exécutez l’applet de commande suivante :
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Mise à niveau de sites multiples vers une nouvelle version
<a name="BKMK_Upgrade"> </a>

Appliquez la procédure de mise à niveau d’un site unique, un site à la fois dans votre déploiement. Vérifiez et [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) après chaque mise à niveau de site.
  

