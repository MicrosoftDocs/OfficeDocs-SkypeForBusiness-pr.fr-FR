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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Découvrez le déploiement d’un seul site PSTN dans Cloud Connector Edition.
ms.openlocfilehash: 07262f88f85602b6213dc287babbd05ddec25ed9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610541"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Déployer un seul site dans Cloud Connector
 
> [!Important]
> Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online. Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)

Découvrez le déploiement d’un seul site PSTN dans Cloud Connector Edition.
  
Vous pouvez déployer des Skype Entreprise Cloud Connector Edition avec ou sans la prise en charge de la haute disponibilité (HA). Si vous souhaitez activer la ha, vous devez déployer au moins deux appliances au sein d’un site. Vous pouvez également convertir une appliance existante pour prendre en charge la ha après son déploiement.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Déployer le premier Skype Entreprise Cloud Connector Edition appliance

Pour déployer la première appliance dans un site, ouvrez une console PowerShell en tant qu’administrateur et exécutez l’cmdlet suivante pour inscrire l’appliance :
  
```powershell
Register-CcAppliance
```

Suivez les instructions pour fournir le nom et le mot de passe du compte d’administrateur client. Utilisez le compte que vous avez créé pour la gestion en ligne de Cloud Connector. Suivez également les instructions pour fournir le mot de passe du certificat externe, le mot de passe d’administrateur en mode sans échec, le mot de passe d’administrateur de domaine et le mot de passe d’administrateur de la VM. 
  
Dans la version 1.4.2 et antérieure, suivez également les instructions pour fournir le mot de passe du certificat externe, le mot de passe d’administrateur en mode sans échec, le mot de passe d’administrateur de domaine et le mot de passe d’administrateur de la VM. 
  
Dans la version 2.0 et ultérieure, suivez également les instructions pour fournir le mot de passe du certificat externe, le mot de passe CceService et le mot de passe CABackupFile.
  
Pour démarrer l’installation, ouvrez une console PowerShell en tant qu’administrateur et exécutez l’cmdlet suivante :
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Ajouter une appliance à un site existant

Vous pouvez étendre un site Cloud Connector existant pour prendre en charge la haute qualité de l’expérience en ajoutant des appliances supplémentaires au site. 
  
1. Suivez les étapes pour préparer votre appliance Cloud Connector comme décrit dans [Préparer votre appliance Cloud Connector.](prepare-your-cloud-connector-appliance.md) Notez que certaines étapes sont requises uniquement pour la première appliance de votre déploiement. Confirmez que l’annuaire de sites existe et qu’il est correctement configuré pour la prise en charge de la ha.
    
2. Exécutez l’cmdlet suivante uniquement sur le serveur hôte nouvellement ajouté pour mettre à jour les informations de topologie dans votre configuration Microsoft 365 ou Office 365'organisation. Si vous souhaitez ajouter plusieurs appliances en même temps, exécutez l’cmdlet sur chaque serveur hôte nouvellement ajouté un par un :
    
   ```powershell
   Register-CcAppliance
   ```

3. Mettez à jour la topologie sur les appliances existantes en exécutant l’cmdlet suivante sur chaque serveur hôte. Exécutez uniquement l’cmdlet sur les appliances existantes.
    
   ```powershell
   Publish-CcAppliance
   ```

4. Exécutez la cmdlet suivante uniquement sur les serveurs hôtes nouvellement ajoutés. N’exécutez pas cette cmdlet sur l’appliance existante. Si vous souhaitez ajouter plusieurs appliances en même temps, exécutez l’cmdlet sur chaque serveur hôte nouvellement ajouté un par un.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Si l’annuaire de sites a été défini sur un chemin d’accès de dossier local, vous devez définir un partage de fichiers pour ce dossier et utiliser un chemin UNC pour l’annuaire de sites sur la nouvelle appliance. Vous pouvez laisser le premier répertoire de site appliance avec le chemin d’accès local ou le modifier pour utiliser le chemin d’accès UNC pour le partage vers le même dossier. Si l’emplacement de l’annuaire de sites partagés change, toutes les appliances précédemment installées doivent être désinstallées, puis réinstallées. > Important : le mot de passe du compte CceService et du compte CABackupFile doit être identique sur toutes les appliances déployées sur le site, afin que les appliances peuvent accéder au partage d’annuaire de sites et au fichier de sauvegarde de l’autorité de contrôle d’accès chiffré dans l’annuaire de sites. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Supprimer une appliance d’un site existant

Si vous souhaitez supprimer une appliance d’un site existant :
  
1. Exécutez la cmdlet suivante uniquement sur les serveurs hôtes que vous souhaitez supprimer du site pour mettre à jour les informations de topologie dans la configuration de votre Microsoft 365 ou Office 365'organisation.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. Exécutez la cmdlet suivante uniquement sur les serveurs hôtes dont vous souhaitez supprimer tous les ordinateurs virtuels de l’appliance.
    
   ```powershell
   Uninstall-CcAppliance
   ```