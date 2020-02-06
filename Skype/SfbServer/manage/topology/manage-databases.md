---
title: Gérer des bases de données à l’aide d’un groupe de disponibilité AlwaysOn dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Résumé : Découvrez comment ajouter des bases de données Skype entreprise Server à un groupe de disponibilité AlwaysOn existant et en savoir plus sur les étapes supplémentaires nécessaires après le correctif ou la mise à niveau d’un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn dans Skype pour Business Server.'
ms.openlocfilehash: 579b00047a9966e3ce991863506f5686d8a2d520
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817135"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Gérer des bases de données à l’aide d’un groupe de disponibilité AlwaysOn dans Skype entreprise Server

Suivez les étapes décrites dans cet article pour ajouter d’autres bases de données Skype entreprise Server à un groupe de disponibilité AlwaysOn existant dans Skype entreprise Server et en savoir plus sur les étapes supplémentaires nécessaires après le correctif ou la mise à niveau d’un serveur principal qui fait partie d’un serveur AlwaysOn. Groupe disponibilité dans Skype entreprise Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Ajouter des bases de données à un groupe de disponibilité AlwaysOn 

1. Ouvrez SQL Server Management Studio, puis accédez au groupe disponibilité AlwaysOn. Basculez vers le réplica principal.
    
2. Dans le générateur de topologie, définissez le nom de domaine complet SQL Server du groupe disponibilité AlwaysOn sur le nom de domaine complet du nœud principal de ce groupe.
    
   - Ouvrez le générateur de topologie, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.
    
   - Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**. Cliquez avec le bouton droit sur le magasin SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **modifier les propriétés**.
    
   - En bas de la page, dans la zone **nom de domaine complet (FQDN) SQL Server** , entrez le nom de domaine complet (FQDN) du nœud principal du groupe disponibilité AlwaysOn.
    
3. Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.
    
4. Utilisez SQL Server Management Studio pour ajouter la nouvelle base de données dans le groupe disponibilité AlwaysOn.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Correctif ou mise à jour d’un serveur SQL Server dans un groupe disponibilité AlwaysOn

Après avoir corrigé un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn, vous devez republier la topologie.

1. Installez la mise à jour sur votre serveur ou vos serveurs Skype entreprise.
    
2. Exécutez la commande PowerShell suivante dans votre shell de gestion de Skype entreprise (connectez-vous à l’aide d’un compte qui a été approprié pour appliquer les modifications aux bases de données SQL AlwaysOn) comme suit :
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Où [sqlpool.contoso.com] est remplacé par le nom de domaine complet (FQDN) de votre groupe disponibilité AlwaysOn.
