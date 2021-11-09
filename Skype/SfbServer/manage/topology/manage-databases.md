---
title: Gérer les bases de données avec un groupe de disponibilité AlwaysOn dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Résumé : Découvrez comment ajouter des bases de données Skype Entreprise Server à un groupe de disponibilité AlwaysOn existant et découvrez les étapes supplémentaires nécessaires après avoir corrigé ou mis à niveau un serveur principal faisant partie d’un groupe de disponibilité AlwaysOn dans Skype Entreprise Server.'
ms.openlocfilehash: fe74cd804aff746a3d6c52163ed96d6b270703ce
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827507"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Gérer les bases de données avec un groupe de disponibilité AlwaysOn dans Skype Entreprise Server

Utilisez les étapes de cet article pour ajouter des bases de données Skype Entreprise Server à un groupe de disponibilité AlwaysOn existant dans Skype Entreprise Server et découvrir les étapes supplémentaires nécessaires après avoir corrigé ou mis à niveau un serveur principal faisant partie d’un groupe de disponibilité AlwaysOn dans Skype Entreprise Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Ajouter des bases de données à un groupe de disponibilité AlwaysOn 

1. Ouvrez SQL Server Management Studio et accédez au groupe de disponibilité AlwaysOn. Retenter vers le réplica principal.
    
2. Dans le Générateur de topologie, définissez SQL Server FQDN du groupe de disponibilité AlwaysOn sur le FQDN du nœud principal de ce groupe.
    
   - Ouvrez le Générateur de topologie, **sélectionnez Télécharger la topologie** à partir d’un déploiement existant, puis cliquez sur **OK.**
    
   - Développez Skype Entreprise Server, développez votre topologie et développez **SQL Server Stores.** Cliquez avec le bouton droit SQL magasin du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **Modifier les propriétés.**
    
   - Au bas de la page, dans la zone **SQL Server FQDN,** tapez le FQDN du nœud principal du groupe de disponibilité AlwaysOn.
    
3. Publiez la topologie. Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.** Ensuite, dans la page de confirmation, cliquez sur **Suivant**.
    
4. Utilisez SQL Server Management Studio pour ajouter la nouvelle base de données au groupe de disponibilité AlwaysOn.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Patch or update a SQL Server in an AlwaysOn Availability Group

Après avoir corrigé un serveur principal faisant partie d’un groupe de disponibilité AlwaysOn, vous devez republier la topologie.

1. Installez la mise à jour sur Skype Entreprise serveurs.
    
2. Exécutez la commande PowerShell suivante dans votre Skype Entreprise Management Shell (connecté avec un compte autorisé à appliquer les modifications aux bases de données SQL AlwaysOn) comme suit :
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Où [sqlpool.contoso.com] est remplacé par le nom de domaine complet (FQDN) de votre groupe de disponibilité AlwaysOn.
