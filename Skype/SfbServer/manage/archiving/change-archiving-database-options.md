---
title: Modification des options de base de données d’archivage dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Résumé : Apprenez à modifier les options de base de données d’archivage de Skype pour Business Server 2015.'
ms.openlocfilehash: 5bb7ee9329cc3fa7a0795115f9a0d11768ab7aa4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="change-archiving-database-options-in-skype-for-business-server-2015"></a>Modification des options de base de données d’archivage dans Skype Entreprise Server 2015

**Résumé :** Découvrez comment modifier les options de base de données d’archivage de Skype pour Business Server 2015.
  
Si vous déployez l’archivage à l’aide de stockage de SQL Server pour l’archivage de stockage pour certains de vos utilisateurs, vous pouvez modifier la base de données suivante stockage :
  
- Utilisez une autre base de données SQL Server pour le stockage d’archives. Cela inclut la base de données principale d’archivage et de toute base de données que vous utilisez pour la mise en miroir de SQL Server.
    
- Passer à l’intégration de Microsoft Exchange pour stocker des données et des fichiers sur les serveurs Exchange d’archivage. Si tous vos utilisateurs sont hébergées sur vos serveurs Exchange et que vous souhaitez utiliser le stockage de Microsoft Exchange pour tous les utilisateurs dans votre déploiement, vous devez supprimer les bases de données de banque d’informations de SQL Server de votre topologie. 
    
Pour effectuer une ou l’autre de ces modifications, vous devez exécuter le Générateur de topologies, apportez les modifications et puis publiez de nouveau la topologie. Ne spécifiez pas d’informations **de SQL Server l’archivage de stocker** ou de **mise en miroir de la banque d’informations de SQL Server permettent** , à moins d’avoir Skype pour les utilisateurs professionnels qui ne sont pas hébergées sur les serveurs Exchange.
  
## <a name="change-archiving-database-options"></a>Modifier les options de la base de données d’archivage

1. Sur un ordinateur qui exécute Skype pour Business Server ou sur lequel le Skype pour outils d’administration de Business Server sont installés, ouvrez une session en utilisant un compte qui est membre du groupe d’utilisateurs local (ou un compte avec des droits d’utilisateur équivalent).
    
    > [!NOTE]
    > Vous pouvez définir une topologie en utilisant un compte qui est membre du groupe d’utilisateurs local, mais pour publier une topologie, ce qui est nécessaire pour ajouter un composant à la topologie, vous devez utiliser un compte qui est membre du groupe **Admins** du domaine et de la **RTCUniversalSer verAdmins** groupe et qui dispose d’autorisations de contrôle total (c'est-à-dire, lire, écrire et modifier) sur le partage de fichiers que vous utilisez pour le Skype pour stockage de fichiers de serveur d’entreprise (c'est-à-dire, afin que le Générateur de topologies peut configurer le contrôle d’accès discrétionnaire requis listes (DACL), ou un compte avec des droits équivalents.
  
2. Démarrer le Générateur de topologies.
    
3. Dans l’arborescence de la console, accédez au pool de serveurs frontaux dans lequel vous avez déployé l’archivage, puis cliquez sur le nom du pool de serveurs frontaux dans lequel vous voulez modifier les options de base de données.
    
4. Dans le menu **Action**, cliquez sur **Modifier les propriétés**. 
    
5. Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.
    
6. Faites défiler la liste jusqu’à **Archivage**.
    
7. Dans **Archivage**, procédez comme suit :
    
  - Pour choisir un autre magasin SQL Server existant, sous **Magasin SQL Server d’archivage**, dans la zone de liste déroulante, procédez comme suit :
    
  - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.
    
  - Pour spécifier un nouveau magasin SQL Server, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir un nouveau magasin SQL Server**, procédez comme suit :
    
    - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.
    
    - Pour spécifier un nouveau magasin de SQL Server, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir nouveau SQL Server magasin** , effectuez les opérations suivantes :
    
      - Dans **Nom de domaine complet de SQL Server**, spécifiez le nom de domaine complet du serveur sur lequel vous souhaitez créer le nouveau magasin de SQL Server.
    
      - Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
    
      - Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **SQL de cette instance est mise en relation de miroir** et puis, dans le **numéro de port miroir**, spécifiez le numéro de port.
    
  - Pour ajouter le magasin SQL Server ou choisir un autre magasin SQL Server existant pour la mise en miroir, sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis procédez comme suit :
    
    - Pour utiliser une banque existante de SQL Server pour la mise en miroir, dans la zone de liste déroulante **mise en miroir de la banque d’informations de SQL Server l’archivage** , cliquez sur le nom de la banque d’informations de SQL Server que vous souhaitez utiliser pour la mise en miroir.
    
    - Pour spécifier un nouveau magasin de SQL Server pour la mise en miroir, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir nouveau SQL Server magasin** , effectuez l’une des opérations suivantes :
    
      a. Dans **Nom de domaine complet de SQL Server**, spécifiez le nom de domaine complet de la SQL Server sur lequel vous souhaitez créer le nouveau magasin de SQL Server.
    
      b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
    
      c. Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **SQL de cette instance est mise en relation de miroir** et puis, dans le **numéro de port miroir**, spécifiez le numéro de port.
    
  - Si vous activez la mise en miroir de SQL Server et que vous souhaitez ajouter ou modifier un SQL Server mise en miroir de rappel (une tiers, distincte de SQL Server instance capables de détecter l’état de santé des instances de serveur et de la mise en miroir de SQL Server principales), sélectionnez le témoin de la mise en miroir de SQL Server d’utilisation de **pour Activer le basculement automatique** case à cocher, puis effectuez l’une des opérations suivantes :
    
      a. Dans **Nom de domaine complet de SQL Server**, spécifiez le nom de domaine complet du serveur sur lequel vous souhaitez créer le nouveau SQL Server témoin de la mise en miroir.
    
      b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.
    
      c. Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **SQL de cette instance est mise en relation de miroir** et puis, dans le **numéro de port miroir**, spécifiez le numéro de port.
    
  - Pour passer à l’intégration de Microsoft Exchange pour stocker d’archivage des données et des fichiers sur des serveurs Exchange (si tous les utilisateurs dans votre déploiement sont hébergées sur vos serveurs Exchange), supprimer toutes les informations pour l’archivage des bases de données.
    
    > [!IMPORTANT]
    > Si vous avez tout Skype pour les utilisateurs professionnels qui ne sont pas hébergées sur des serveurs Exchange, ne supprimez pas les banque d’informations de SQL Server. 
  
8. Pour enregistrer la configuration, cliquez sur **OK**.
    
    > [!IMPORTANT]
    > Les modifications que vous apportez dans le Générateur de topologie ne prendront effet que lorsque vous publiez la nouvelle topologie. Pour plus d’informations, consultez [Ajouter des bases de données d’archivage à un déploiement existant dans Skype pour Business Server 2015](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Changer l’emplacement de la base d’archivage à l’aide de Windows PowerShell

Dans la plupart des cas, vous n’aurez pas à changer l’emplacement de cette base de données d’archivage qui est indiqué lorsque vous installez le serveur d’archivage. Cependant, en cas de panne matérielle ou d’un autre problème, vous pouvez faire pointer le serveur d’archivage sur une nouvelle base de données à l’aide de l’applet de commande **Set-CsArchivingServer**.
  
L’exemple suivant modifie l’emplacement de la base de données d’archivage de la ArchivingServer:atl-cs-001.contoso.com serveur d’archivage. Dans cet exemple, la nouvelle base de données se trouve sur ArchivingDatabase:atl-sql-001.contoso.com :
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


