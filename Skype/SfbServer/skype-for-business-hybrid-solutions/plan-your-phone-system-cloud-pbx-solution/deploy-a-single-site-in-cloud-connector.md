---
title: Déployer un seul site dans Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: En savoir plus sur le déploiement d’un seul site RTC dans la version Cloud Connector.
ms.openlocfilehash: a2cc8933276bc85b19ee79559ca4bcf9e88a079f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001024"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Deploy a single site in Cloud Connector
 
En savoir plus sur le déploiement d’un seul site RTC dans la version Cloud Connector.
  
Vous pouvez déployer Skype entreprise version Cloud Connector avec ou sans prise en charge de haute disponibilité. Si vous souhaitez activer la haute disponibilité, vous devrez déployer au moins 2 appliances sur un site. Vous pouvez également convertir une appliance existante pour prendre en charge la haute disponibilité une fois celle-ci déployée.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Déployer la première instance Skype Entreprise, version Cloud Connector

Pour déployer la première appliance sur un site, ouvrez une console PowerShell en tant qu'administrateur et exécutez l'applet de commande suivante afin d'inscrire l'appliance :
  
```powershell
Register-CcAppliance
```

Suivez les instructions pour spécifier le mot de passe et le nom de compte d'administration du client. Utilisez le compte que vous avez créé pour la gestion en ligne dans Cloud Connector. Suivez également les instructions pour spécifier les mots de passe de certificat externe, d'administration de mode sans échec, d'administration de domaine et d'administration d'ordinateur virtuel. 
  
Dans la version 1.4.2 et les versions antérieures, suivez également les instructions pour fournir le mot de passe du certificat externe, le mot de passe d’administrateur du mode sans échec, le mot de passe d’administrateur de domaine et le mot de passe d’administrateur 
  
Dans la version 2,0 et les versions ultérieures, suivez également les instructions pour fournir le mot de passe du certificat externe, le mot de passe CceService et le mot de passe CABackupFile.
  
Pour commencer l'installation, ouvrez une console PowerShell en tant qu'administrateur et exécutez l'applet de commande suivante :
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Ajouter une appliance à un site existant

Vous pouvez développer un site de connecteur Cloud existant pour prendre en charge le HA en ajoutant des appareils supplémentaires au site. 
  
1. Suivez les étapes pour préparer votre appareil Cloud Connector comme décrit dans [la rubrique préparer votre appareil Cloud Connector](prepare-your-cloud-connector-appliance.md). Notez que certaines étapes sont requises uniquement pour la première appliance dans votre déploiement. Confirmez que l’annuaire de sites existe et qu’il est correctement configuré pour une prise en charge haute disponibilité.
    
2. N'exécutez l'applet de commande suivante que sur le serveur hôte nouvellement ajouté pour mettre les informations de topologie à jour dans votre configuration de client Office 365. Si vous souhaitez ajouter plusieurs appliances en même temps, exécutez l'applet de commande sur chaque serveur hôte nouvellement ajouté un par un :
    
   ```powershell
   Register-CcAppliance
   ```

3. Mettez la topologie à jour sur les appliances existantes en exécutant l'applet de commande suivante sur chaque serveur hôte. N'exécutez l'applet de commande que sur les appliances existantes.
    
   ```powershell
   Publish-CcAppliance
   ```

4. N'exécutez l'applet de commande suivante que sur les serveurs hôtes nouvellement ajoutés. N'exécutez pas cet applet de commande sur l'appliance existante. Si vous souhaitez ajouter plusieurs appliances en même temps, exécutez l'applet de commande sur chaque serveur hôte nouvellement ajouté un par un :
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Si le chemin d’accès du dossier local de l’annuaire de sites est défini, vous devez définir un partage de fichiers pour ce dossier et utiliser un chemin d’accès UNC pour l’annuaire de sites sur la nouvelle appliance. Vous pouvez faire en sorte que le premier annuaire du site du matériel soit associé au chemin d’accès local ou qu’il utilise le chemin UNC du partage dans le même dossier. Si l’emplacement de l’annuaire de sites partagés change, tous les appareils précédemment installés doivent être désinstallés puis réinstallés. > important : le mot de passe du compte CceService et du compte CABackupFile doit être le même sur toutes les applications déployées dans le site, de sorte que les appareils puissent accéder au partage de l’annuaire de sites et au fichier de sauvegarde de l’autorité de certification crypté dans l’annuaire de sites. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Supprimer une appliance d'un site existant

Pour supprimer une appliance d'un site existant :
  
1. N'exécutez l'applet de commande suivante que sur les serveurs hôtes à supprimer du site pour mettre les informations de topologie à jour dans votre configuration de client Office 365.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. N'exécutez l'applet de commande suivante que sur les serveurs hôtes à partir desquels vous souhaitez supprimer tous les ordinateurs virtuels de l'appliance.
    
   ```powershell
   Uninstall-CcAppliance
   ```


