---
title: Déployer un seul site dans Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom:
- Strat_SB_Hybrid
- Strat_SB_Hybrid
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Obtenir des informations sur le déploiement d’un seul site RTPC dans le nuage lien édition.
ms.openlocfilehash: 6268a9207d36e89faf391ac77a7dd832ba65704f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Déployer un seul site dans Cloud Connector
 
Obtenir des informations sur le déploiement d’un seul site RTPC dans le nuage lien édition.
  
Vous pouvez déployer Skype pour connecteur de Cloud Business Edition avec ou sans prise en charge de la haute disponibilité (HA). Si vous souhaitez activer la haute disponibilité, vous devrez déployer au moins 2 appliances sur un site. Vous pouvez également convertir une appliance existante pour prendre en charge la haute disponibilité une fois celle-ci déployée.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Déployer la première instance Skype Entreprise, version Cloud Connector

Pour déployer la première appliance sur un site, ouvrez une console PowerShell en tant qu'administrateur et exécutez l'applet de commande suivante afin d'inscrire l'appliance :
  
```
Register-CcAppliance
```

Suivez les instructions pour spécifier le mot de passe et le nom de compte d'administration du client. Utilisez le compte que vous avez créé pour la gestion en ligne de Cloud Connector. Suivez également les instructions pour spécifier les mots de passe de certificat externe, d'administration de mode sans échec, d'administration de domaine et d'administration d'ordinateur virtuel.  
  
Dans la version 1.4.2 et antérieure, également de suivre les instructions pour fournir le mot de passe de certificat externe mot de passe administrateur en mode sans échec, mot de passe administrateur de domaine et mot de passe administrateur de machine virtuelle. 
  
Dans les versions 2.0 et suivantes, suivez également les instructions pour spécifier les mots de passe de certificat externe, CceService et CABackupFile.
  
Pour commencer l'installation, ouvrez une console PowerShell en tant qu'administrateur et exécutez l'applet de commande suivante :
  
```
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Ajouter une appliance à un site existant

Vous pouvez étendre un site connecteur du Cloud existant pour prendre en charge la haute disponibilité par l’ajout d’appliances supplémentaires sur le site. 
  
1. Suivez les étapes pour préparer votre solution de Cloud connecteur comme décrit dans [préparer votre appliance de connecteur de nuage](prepare-your-cloud-connector-appliance.md). Notez que certaines étapes sont requises uniquement pour la première appliance dans votre déploiement. Confirmez que l’annuaire de sites existe et qu’il est correctement configuré pour une prise en charge haute disponibilité.
    
2. N'exécutez l'applet de commande suivante que sur le serveur hôte nouvellement ajouté pour mettre les informations de topologie à jour dans votre configuration de client Office 365. Si vous souhaitez ajouter plusieurs appliances en même temps, exécutez l'applet de commande sur chaque serveur hôte nouvellement ajouté un par un :
    
  ```
  Register-CcAppliance
  ```

3. Mettez la topologie à jour sur les appliances existantes en exécutant l'applet de commande suivante sur chaque serveur hôte. N'exécutez l'applet de commande que sur les appliances existantes.
    
  ```
  Publish-CcAppliance
  ```

4. N'exécutez l'applet de commande suivante que sur les serveurs hôtes nouvellement ajoutés. N'exécutez pas cet applet de commande sur l'appliance existante. Si vous souhaitez ajouter plusieurs appliances en même temps, exécutez l'applet de commande sur chaque serveur hôte nouvellement ajouté un par un :
    
  ```
  Install-CcAppliance
  ```

> [!NOTE]
> Si l’annuaire de sites a été défini à un chemin d’accès du dossier local, vous devez définir un partage de fichiers de ce dossier et d’utiliser un chemin d’accès UNC pour le répertoire de site sur le nouveau matériel. Vous pouvez laisser le premier répertoire de site solution matérielle-logicielle avec le chemin d’accès local ou le modifier pour utiliser le chemin d’accès UNC pour le partage dans le même dossier. Si l’emplacement du répertoire du site partagé change, les appliances précédemment installé doivent être désinstallé et réinstallé. > Important : Le mot de passe pour le compte CceService et le CABackupFile de compte doit être le même sur tous les appareils déployés dans le site, afin que les applications puissent accéder le partage de répertoire du site et le fichier de sauvegarde chiffré autorité de certification dans l’annuaire de sites. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Supprimer une appliance d'un site existant

Pour supprimer une appliance d'un site existant :
  
1. N'exécutez l'applet de commande suivante que sur les serveurs hôtes à supprimer du site pour mettre les informations de topologie à jour dans votre configuration de client Office 365.
    
  ```
  Unregister-CcAppliance
  ```

2. N'exécutez l'applet de commande suivante que sur les serveurs hôtes à partir desquels vous souhaitez supprimer tous les ordinateurs virtuels de l'appliance.
    
  ```
  Uninstall-CcAppliance
  ```


