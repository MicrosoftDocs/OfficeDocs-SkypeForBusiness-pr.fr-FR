---
title: Effectuer une mise à niveau vers une nouvelle version de Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Découvrez comment mettre à niveau votre déploiement édition de connecteur de nuage.
ms.openlocfilehash: 0538b5d43c6e11aa11f7d265e43eb5f283e2b74e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Effectuer une mise à niveau vers une nouvelle version de Cloud Connector
 
Découvrez comment mettre à niveau votre déploiement édition de connecteur de nuage.
  
Si vous avez configuré un compte client de gestion en ligne et activé les mises à jour automatiques, votre déploiement existant de Skype Entreprise, version Cloud Connector sera mis à niveau vers la dernière version automatiquement, en fonction de votre configuration de fenêtre de délai de mise à jour automatique. Vous pouvez également effectuer manuellement la mise à niveau. 
  
Versions de connecteur Édition 1.4.1 en nuage et ultérieurement effectuer des mises à jour automatiques par défaut. Si vous souhaitez mettre à niveau vers la version la plus récente (2.1) manuellement, reportez-vous à la section [mise à niveau d’un site vers une nouvelle version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) plus loin dans cette rubrique.
  
Mise à jour automatique nécessite que le service du connecteur du nuage est en cours d’exécution. Les étapes suivantes décrivent le processus de mise à jour automatiques :
  
- Le processus de mise à jour automatique fonctionnera en fonction de la planification que vous avez configurée pour les mises à jour automatiques.
    
- Tâches de mise à jour du système d'exploitation
    
  - Vérifier et télécharger les mises à jour du système d’exploitation sur tous les ordinateurs virtuels de connecteur Cloud. 
    
  - Installer et mettre à jour des ordinateurs virtuels de connecteur de nuage toutes les une par une et redémarrez.
    
  - Après le redémarrage de la VM de connecteur de nuage, vérifiez si un autre redémarrage est nécessaire.
    
  - Après les ordinateurs virtuels connecteur de nuage ont été corrigées, répétez le processus pour l’ordinateur hôte de connecteur de nuage.
    
  - Une fois que l’ordinateur hôte de connecteur de nuage avec succès démarre, les tâches de mise à jour des systèmes d’exploitation en cours sont terminées.
    
- Tâches de mise à jour de connecteur du nuage
    
  - Téléchargez et vérifiez le fichier de version à partir du site de téléchargement.
    
  - Téléchargez le fichier .msi de la nouvelle version.  
    
  - Désinstallation de l’ancien fichier msi ; installer le nouveau fichier msi.
    
  - Télécharger la nouvelle version de Skype pour les bits d’entreprise.
    
  - Enregistrez l’appliance en appelant Register-CcAppliance.
    
  - Installer la nouvelle version de connecteur de nuage.
    
  - Nettoyez l’ancienne appliance puis basculez la connexion réseau vers la nouvelle appliance.
    
> [!NOTE]
>  Lorsque le nuage lien mises à jour vers une nouvelle version, les cmdlets de connecteur de nuage ne peut pas mettre à jour. Cela peut se produire, par exemple, si une fenêtre PowerShell est laissée ouverte pendant la mise à jour automatique. Pour charger les applets de commande mises à jour, vous pouvez effectuer les opérations suivantes : > Fermer PowerShell sur la solution matérielle-logicielle de connecteur de nuage et puis rouvrez PowerShell. > ou bien, vous pouvez exécuter le Module d’importation CloudConnector-Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Mise à niveau d’un site unique vers une nouvelle version
<a name="BKMK_Upgrade"> </a>

Si le site comporte un seul équipement que vous souhaitez mettre à niveau, procédez comme suit :
  
1. Désinstaller la version existante de connecteur de nuage dans **le panneau de configuration \> programmes \> programmes et fonctionnalités**.
    
2. Installer la nouvelle version de CloudConnector.msi de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).
    
3. Vérifiez que vous disposez du fichier CloudConnector.ini pour la version que vous installez et que les valeurs requises pour votre environnement sont mises à jour. Vous ne pouvez pas utiliser le fichier .ini d’une version précédente. Si vous mettez à niveau connecteur de nuage, reportez-vous à la rubrique [préparer votre solution de Cloud connecteur](prepare-your-cloud-connector-appliance.md) et vérifiez SiteName et EnableReferSupport sont définies sur la valeur correcte dans le fichier CloudConnector.ini.
    
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
  
Si vous souhaitez mettre à jour d’administrateur de domaine, administrateur de la machine virtuelle, administrateur du Mode sans échec et informations d’identification administrateur de clients, vous pouvez exécuter l’applet de commande avec le paramètre _UpdateAllCredentials_ pour réinitialiser les informations d’identification tous les :
  
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

Appliquez la procédure de mise à niveau d’un site unique, un site à la fois dans votre déploiement. Assurez-vous qu’et [Valider le déploiement de Cloud connecteur](validate-your-cloud-connector-deployment.md) après la mise à niveau de chaque site.
  

