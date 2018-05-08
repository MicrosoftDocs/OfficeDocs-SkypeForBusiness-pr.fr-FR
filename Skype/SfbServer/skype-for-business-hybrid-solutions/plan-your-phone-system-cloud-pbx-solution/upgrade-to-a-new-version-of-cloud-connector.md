---
title: Effectuer une mise à niveau vers une nouvelle version de Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Découvrez comment mettre à niveau votre déploiement en nuage connecteur Edition.
ms.openlocfilehash: 925b19360115e74a147f8b32c6faa42b84971f60
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Effectuer une mise à niveau vers une nouvelle version de Cloud Connector
 
Découvrez comment mettre à niveau votre déploiement en nuage connecteur Edition.
  
Si vous avez configuré un compte client de gestion en ligne et activé les mises à jour automatiques, votre déploiement existant de Skype Entreprise, version Cloud Connector sera mis à niveau vers la dernière version automatiquement, en fonction de votre configuration de fenêtre de délai de mise à jour automatique. Vous pouvez également effectuer manuellement la mise à niveau. 
  
Versions de connecteur Edition 1.4.1 en nuage et ultérieurement effectuer des mises à jour automatiques par défaut. Si vous souhaitez mettre à niveau vers la dernière version (2.1) manuellement, voir [mettre à niveau un seul site vers une nouvelle version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) plus loin dans cette rubrique.
  
Mise à jour automatique requiert que le service nuage connecteur est en cours d’exécution. Les étapes suivantes décrivent le processus de mise à jour automatiques :
  
- Le processus de mise à jour automatique fonctionnera en fonction de la planification que vous avez configurée pour les mises à jour automatiques.
    
- Tâches de mise à jour du système d'exploitation
    
  - Vérifier et télécharger des mises à jour du système d’exploitation sur tous les ordinateurs virtuels de connecteur dans le nuage. 
    
  - Installer et mettre à jour tous les ordinateurs dans le nuage connecteur virtuels un par un redémarrage.
    
  - Après le redémarrage d’ordinateurs virtuels dans le nuage connecteur, vérifie si un autre redémarrage est nécessaire.
    
  - Après avoir des ordinateurs virtuels dans le nuage connecteur ont été correctement corrigés, répétez le processus pour l’ordinateur hôte de nuage connecteur.
    
  - Une fois que l’ordinateur hôte de nuage connecteur correctement démarre, des tâches de mise à jour de système d’exploitation en attente sont terminées.
    
- Tâches de mise à jour de connecteur en nuage
    
  - Téléchargez et vérifiez le fichier de version à partir du site de téléchargement.
    
  - Téléchargez le fichier .msi de la nouvelle version.  
    
  - Désinstaller l’ancien fichier msi ; Installez le nouveau fichier msi.
    
  - Téléchargez la nouvelle version de Skype pour bits de l’entreprise.
    
  - Enregistrez l’appliance en appelant Register-CcAppliance.
    
  - Installer la nouvelle version de connecteur dans le nuage.
    
  - Nettoyez l’ancienne appliance puis basculez la connexion réseau vers la nouvelle appliance.
    
> [!NOTE]
>  Lorsque nuage connecteur mises à jour vers une nouvelle version, cmdlets de connecteur de nuage ne peut pas mis à jour. Cela peut se produire, par exemple, si une fenêtre PowerShell reste ouverte pendant la mise à jour automatique. Pour charger les applets de commande mis à jour, vous pouvez effectuer une des opérations suivantes : > Fermer PowerShell sur le nuage connecteur appliance et rouvrez PowerShell. > ou bien, vous pouvez exécuter Import-Module CloudConnector-Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Mise à niveau d’un site unique vers une nouvelle version
<a name="BKMK_Upgrade"> </a>

Si le site comporte un seul équipement que vous souhaitez mettre à niveau, procédez comme suit :
  
1. Désinstaller la version existante de nuage connecteur dans **le panneau de configuration \> programmes \> programmes et fonctionnalités**.
    
2. Installer la nouvelle version de CloudConnector.msi de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).
    
3. Vérifiez que vous disposez du fichier CloudConnector.ini pour la version que vous installez et que les valeurs requises pour votre environnement sont mises à jour. Vous ne pouvez pas utiliser le fichier .ini d’une version précédente. Si vous mettez à niveau dans le nuage connecteur, reportez-vous à la rubrique [préparer votre solution de nuage connecteur](prepare-your-cloud-connector-appliance.md) et vérifiez SiteName et EnableReferSupport sont définies dans le fichier CloudConnector.ini à la valeur correcte.
    
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
  
Si vous souhaitez mettre à jour d’administrateur de domaine, administrateur de l’ordinateur virtuel, administrateur en Mode sans échec et les informations d’identification administrateur client, vous pouvez exécuter l’applet de commande avec le paramètre _UpdateAllCredentials_ pour réinitialiser tous les informations d’identification :
  
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

Appliquez la procédure de mise à niveau d’un site unique, un site à la fois dans votre déploiement. Assurez-vous qu’et [valider votre déploiement en nuage connecteur](validate-your-cloud-connector-deployment.md) après la mise à niveau de chaque site.
  

