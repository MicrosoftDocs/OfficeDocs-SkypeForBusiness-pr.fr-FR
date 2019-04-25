---
title: Gérer les bases de données avec un groupe de disponibilité AlwaysOn dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Résumé : Découvrez comment ajouter plus Skype pour les bases de données Business Server à un groupe de disponibilité AlwaysOn existant et en savoir plus sur les étapes supplémentaires nécessaires après correctifs ou mise à niveau d’un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn dans Skype pour Serveur d’entreprise.'
ms.openlocfilehash: 8d25e7d3aa1e840be7eb246e6aaa3065b65b7ff7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214693"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Gérer les bases de données avec un groupe de disponibilité AlwaysOn dans Skype pour Business Server

Utilisez les étapes de cet article pour ajouter plusieurs Skype pour les bases de données Business Server à un groupe de disponibilité AlwaysOn existant dans Skype pour Business Server et découvrez les étapes supplémentaires après avoir des correctifs ou mise à niveau d’un serveur principal qui fait partie d’un AlwaysOn Groupe de disponibilité dans Skype pour Business Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Ajouter des bases de données à un groupe de disponibilité AlwaysOn 

1. Ouvrez SQL Server Management Studio et accédez au groupe de disponibilité AlwaysOn. Basculer sur le réplica principal.
    
2. Dans le Générateur de topologie, définissez le nom de domaine complet SQL Server du groupe de disponibilité AlwaysOn sur le nom de domaine complet du nœud principal de ce groupe.
    
   - Ouvrez le Générateur de topologie, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, cliquez sur **OK**.
    
   - Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**. Cliquez sur le magasin SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **Modifier les propriétés**.
    
   - En bas de la page, dans la zone **Nom de domaine complet de SQL Server** , tapez dans le nom de domaine complet du nœud principal du groupe de disponibilité AlwaysOn.
    
3. Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.
    
4. Pour ajouter la nouvelle base de données pour le groupe de disponibilité AlwaysOn, utilisez SQL Server Management Studio.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Correctifs ou mise à jour de SQL Server dans un groupe de disponibilité AlwaysOn

Après la mise à jour d’un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn, vous devez republier la topologie.

1. Installez la mise à jour sur votre Skype pour l’entreprise ou les serveurs.
    
2. Exécutez la commande PowerShell suivante dans votre Skype pour Business Management Shell (connecté avec un compte qui est correctement autorisé à appliquer les modifications apportées aux bases de données SQL AlwaysOn) comme suit :
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Où [sqlpool.contoso.com] est remplacé par le nom de domaine complet (FQDN) de votre groupe de disponibilité AlwaysOn.
