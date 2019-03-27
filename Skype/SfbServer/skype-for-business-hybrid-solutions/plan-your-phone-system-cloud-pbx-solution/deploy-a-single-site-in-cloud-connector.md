---
title: Déployer un seul site dans Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: En savoir plus sur le déploiement d’un seul site PSTN dans le nuage connecteur Edition.
ms.openlocfilehash: 667637fdf7dd42df64c4fdf9aca6b20931da188d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881140"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Deploy a single site in Cloud Connector
 
En savoir plus sur le déploiement d’un seul site PSTN dans le nuage connecteur Edition.
  
Vous pouvez déployer Skype pour l’édition de connecteur Business Cloud avec ou sans prise en charge de la haute disponibilité (HA). Si vous souhaitez activer la haute disponibilité, vous devrez déployer au moins 2 appliances sur un site. Vous pouvez également convertir une appliance existante pour prendre en charge la haute disponibilité une fois celle-ci déployée.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Déployer la première instance Skype Entreprise, version Cloud Connector

Pour déployer la première appliance sur un site, ouvrez une console PowerShell en tant qu'administrateur et exécutez l'applet de commande suivante afin d'inscrire l'appliance :
  
```
Register-CcAppliance
```

Suivez les instructions pour spécifier le mot de passe et le nom de compte d'administration du client. Utiliser le compte que vous avez créé pour la gestion en nuage connecteur en ligne. Suivez également les instructions pour spécifier les mots de passe de certificat externe, d'administration de mode sans échec, d'administration de domaine et d'administration d'ordinateur virtuel. 
  
Dans la version 1.4.2 et précédemment, également suivre les instructions pour fournir le mot de passe de certificat externe, le mot de passe d’administration en mode sans échec, mot de passe d’administration de domaine et le mot de passe d’administration ordinateur virtuel. 
  
Dans la version 2.0 et versions ultérieures, également suivre les instructions pour fournir le mot de passe de certificat externe, CceService mot de passe et le mot de passe CABackupFile.
  
Pour commencer l'installation, ouvrez une console PowerShell en tant qu'administrateur et exécutez l'applet de commande suivante :
  
```
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Ajouter une appliance à un site existant

Vous pouvez étendre un site existant de nuage connecteur pour prendre en charge la haute disponibilité en ajoutant des équipements supplémentaires pour le site. 
  
1. Suivez les étapes pour préparer votre solution de nuage connecteur comme décrit dans [préparer votre solution de nuage connecteur](prepare-your-cloud-connector-appliance.md). Notez que certaines étapes sont requises uniquement pour la première appliance dans votre déploiement. Confirmez que l’annuaire de sites existe et qu’il est correctement configuré pour une prise en charge haute disponibilité.
    
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
> Si l’annuaire de sites a été défini sur un chemin d’accès du dossier local, vous devez définir un partage de fichiers pour ce dossier et d’utiliser un chemin d’accès UNC de l’annuaire de sites sur le nouveau matériel. Vous pouvez laisser l’annuaire de sites appliance premier avec le chemin d’accès local ou modifier pour qu’il utilise le chemin d’accès UNC du partage dans le même dossier. Si l’emplacement de l’annuaire de sites partagés change, n’importe quel appliances précédemment installé doivent être désinstallés et puis réinstallé. > Important : le mot de passe pour le compte CceService et le compte CABackupFile doit être identiques sur tous les appareils déployés dans le site, afin que les appareils puissent accéder le partage de répertoire du site et le fichier de sauvegarde chiffré autorité de certification dans l’annuaire de sites. 
  
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


