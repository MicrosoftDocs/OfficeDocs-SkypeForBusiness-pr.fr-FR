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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Découvrez comment déployer un seul site RTC dans la version Cloud Connector.
ms.openlocfilehash: 334454645be3361794fdd0d16076095a518e58b0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220534"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Déployer un seul site dans Cloud Connector
 
Découvrez comment déployer un seul site RTC dans la version Cloud Connector.
  
Vous pouvez déployer Skype entreprise, version Cloud Connector avec ou sans prise en charge de la haute disponibilité (HA). Si vous souhaitez activer la haute disponibilité, vous devez déployer au moins deux Appliances au sein d’un site. Vous pouvez également convertir une appliance existante pour prendre en charge la haute disponibilité après son déploiement.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Déployer la première Appliance Skype entreprise, version Cloud Connector

Pour déployer la première appliance sur un site, ouvrez une console PowerShell en tant qu’administrateur et exécutez l’applet de commande suivante pour enregistrer l’appliance :
  
```powershell
Register-CcAppliance
```

Suivez les instructions pour indiquer le nom du compte et le mot de passe de l’administrateur client. Utilisez le compte que vous avez créé pour la gestion en ligne de Cloud Connector. Suivez également les instructions pour indiquer le mot de passe du certificat externe, le mot de passe administrateur en mode sans échec, le mot de passe administrateur de domaine et le mot de passe d’administrateur de l’ordinateur virtuel. 
  
Dans la version 1.4.2 et les versions antérieures, suivez également les instructions pour indiquer le mot de passe du certificat externe, le mot de passe administrateur en mode sans échec, le mot de passe d’administrateur de domaine et le mot de passe d’administrateur VM. 
  
Dans la version 2,0 et les versions ultérieures, suivez également les instructions pour indiquer le mot de passe du certificat externe, le mot de passe CceService et le mot de passe CABackupFile.
  
Pour démarrer l’installation, ouvrez une console PowerShell en tant qu’administrateur et exécutez l’applet de commande suivante :
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Ajouter une appliance à un site existant

Vous pouvez étendre un site Cloud Connector existant pour prendre en charge la haute disponibilité en ajoutant des appliances supplémentaires au site. 
  
1. Suivez les étapes de préparation de votre appliance Cloud Connector comme décrit dans [prepare the Cloud Connector Appliance](prepare-your-cloud-connector-appliance.md). Certaines étapes sont requises uniquement pour la première appliance de votre déploiement. Vérifiez que l’annuaire de sites existe et qu’il est correctement configuré pour la prise en charge de la haute disponibilité.
    
2. Exécutez l’applet de commande suivante uniquement sur le serveur hôte nouvellement ajouté afin de mettre à jour les informations de topologie dans la configuration de votre organisation Microsoft 365 ou Office 365. Si vous souhaitez ajouter plusieurs Appliances en même temps, exécutez l’applet de commande sur chaque serveur hôte nouvellement ajouté un par un :
    
   ```powershell
   Register-CcAppliance
   ```

3. Mettez à jour la topologie sur les appliances existantes en exécutant l’applet de commande suivante sur chaque serveur hôte. N’exécutez l’applet de commande que sur les appliances existantes.
    
   ```powershell
   Publish-CcAppliance
   ```

4. Exécutez l’applet de commande suivante uniquement sur les serveurs hôtes nouvellement ajoutés. N’exécutez pas cette applet de commande sur l’appliance existante. Si vous souhaitez ajouter plusieurs Appliances en même temps, exécutez l’applet de commande sur chaque serveur hôte nouvellement ajouté un par un.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Si l’annuaire de sites a été défini sur un chemin d’accès au dossier local, vous devez définir un partage de fichiers pour ce dossier et utiliser un chemin d’accès UNC pour l’annuaire de sites sur le nouvel appareil. Vous pouvez laisser le premier annuaire de sites de matériel avec le chemin d’accès local ou le modifier pour utiliser le chemin d’accès UNC du partage vers le même dossier. Si l’emplacement de l’annuaire de sites partagé change, les appliances précédemment installées doivent être désinstallées, puis réinstallées. > important : le mot de passe pour le compte CceService et le compte CABackupFile doit être le même sur toutes les appliances déployées au sein du site, afin que les appliances puissent accéder au partage de l’annuaire de sites et au fichier de sauvegarde de l’autorité de certification chiffré dans l’annuaire de sites. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Supprimer une appliance d’un site existant

Si vous souhaitez supprimer une appliance d’un site existant :
  
1. Exécutez l’applet de commande suivante uniquement sur les serveurs hôtes que vous souhaitez supprimer du site afin de mettre à jour les informations de topologie dans la configuration de votre organisation Microsoft 365 ou Office 365.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. Exécutez l’applet de commande suivante uniquement sur les serveurs hôtes dont vous souhaitez supprimer tous les ordinateurs virtuels de l’appliance.
    
   ```powershell
   Uninstall-CcAppliance
   ```


