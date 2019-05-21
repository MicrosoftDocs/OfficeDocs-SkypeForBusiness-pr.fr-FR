---
title: Modification des options de base de données d’archivage dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Résumé: Découvrez comment modifier les options de base de données d’archivage de Skype entreprise Server.'
ms.openlocfilehash: 56aa29ef185176ce3b080572723c566455731dc4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299985"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Modification des options de base de données d’archivage dans Skype entreprise Server

**Résumé:** Découvrez comment modifier les options de base de données d’archivage de Skype entreprise Server.
  
Si vous déployez l’archivage à l’aide du stockage SQL Server pour l’archivage pour l’un de vos utilisateurs, vous pouvez effectuer les modifications suivantes du stockage de la base de données:
  
- Utilisez une autre base de données SQL Server pour l’archivage du stockage. Il s’agit de la base de données d’archivage principale et de la base de données que vous utilisez pour la mise en miroir SQL Server.
    
- Basculez vers l’intégration de Microsoft Exchange pour stocker les données et fichiers d’archivage sur les serveurs Exchange. Si tous vos utilisateurs sont sur votre serveur Exchange et que vous souhaitez utiliser le stockage Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez supprimer les bases de données SQL Server Store de votre topologie. 
    
Pour effectuer l’une de ces modifications, vous devez exécuter le générateur de topologie, apporter les modifications, puis publier de nouveau la topologie. Ne spécifiez pas **l’archivage de SQL Server Store** ou activez les informations de **mise en miroir SQL Server Store** , sauf si les utilisateurs de Skype entreprise ne sont pas hébergés sur des serveurs Exchange.
  
## <a name="change-archiving-database-options"></a>Modifier les options de la base de données d’archivage

1. Sur un ordinateur exécutant Skype entreprise Server ou sur lequel sont installés les outils d’administration de Skype entreprise Server, connectez-vous à l’aide d’un compte membre du groupe utilisateurs locaux (ou d’un compte possédant des droits d’utilisateur similaires).
    
    > [!NOTE]
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais pour publier une topologie, qui est nécessaire pour ajouter un composant à la topologie, vous devez utiliser un compte membre du groupe **administrateurs de domaine** et de la **RTCUniversalSer. verAdmins** et qui dispose des autorisations de contrôle total (lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le stockage de fichiers Skype entreprise Server (c’est-à-dire que le générateur de topologie peut configurer le contrôle d’accès discrétionnaire requis des listes (DACL) ou un compte avec des droits équivalents.
  
2. Démarrer le générateur de topologie.
    
3. Dans l’arborescence de la console, accédez au pool de serveurs frontaux dans lequel vous avez déployé l’archivage, puis cliquez sur le nom du pool de serveurs frontaux dans lequel vous voulez modifier les options de base de données.
    
4. Dans le menu **Action**, cliquez sur **Modifier les propriétés**. 
    
5. Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.
    
6. Faites défiler la liste jusqu’à **Archivage**.
    
7. Dans **Archivage**, procédez comme suit :
    
   - Pour choisir un autre magasin SQL Server existant, sous **Magasin SQL Server d’archivage**, dans la zone de liste déroulante, procédez comme suit :
    
   - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.
    
   - Pour spécifier un nouveau magasin SQL Server, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir un nouveau magasin SQL Server**, procédez comme suit :
    
     - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.
    
     - Pour spécifier un nouveau SQL Server Store, cliquez sur **nouveau**puis, dans la boîte de dialogue **définir un nouveau SQL Server Store** , procédez comme suit:
    
       - Dans **FQDN SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau SQL Server Store.
    
       - Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
    
       - Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.
    
   - Pour ajouter le magasin SQL Server ou choisir un autre magasin SQL Server existant pour la mise en miroir, sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis procédez comme suit :
    
     - Pour utiliser un magasin SQL Server existant pour la mise en miroir, dans la zone de liste déroulante archivage de **SQL Server Store** , cliquez sur le nom du magasin SQL Server que vous voulez utiliser pour la mise en miroir.
    
     - Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **nouveau**puis, dans la boîte de dialogue **définir un nouveau SQL Server Store** , effectuez l’une des opérations suivantes:
    
       a. Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL sur lequel vous souhaitez créer le nouveau SQL Server Store.
    
       b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
    
       c. Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.
    
   - Si vous activez la mise en miroir SQL Server et voulez ajouter ou modifier un témoin de mise en miroir SQL Server (troisième instance SQL Server distincte capable de détecter l’état du serveur SQL Server principal et des instances miroir), sélectionnez le **témoin de mise en miroir SQL Server. activez l’option reprise automatique** , puis effectuez l’une des opérations suivantes:
    
      a. Dans **FQDN SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau témoin de mise en miroir SQL Server.
    
      b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.
    
      c. Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.
    
   - Pour basculer vers l’intégration de Microsoft Exchange pour stocker les données et fichiers d’archivage sur les serveurs Exchange (si tous les utilisateurs de votre déploiement sont hébergés sur vos serveurs Exchange), supprimez toutes les informations pour l’archivage des bases de données.
    
     > [!IMPORTANT]
     > Si vous avez des utilisateurs Skype entreprise qui ne sont pas hébergés sur des serveurs Exchange, ne supprimez pas les informations du Windows Store SQL Server. 
  
8. Pour enregistrer la configuration, cliquez sur **OK**.
    
    > [!IMPORTANT]
    > Les modifications que vous apportez dans le générateur de topologie ne s’appliquent pas tant que vous n’avez pas publié la nouvelle topologie. Pour plus d’informations, reportez-vous à la section [Ajouter des bases de données d’archivage à un déploiement existant dans Skype entreprise Server](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Changer l’emplacement de la base d’archivage à l’aide de Windows PowerShell

Dans la plupart des cas, vous n’aurez pas à changer l’emplacement de cette base de données d’archivage qui est indiqué lorsque vous installez le serveur d’archivage. Cependant, en cas de panne matérielle ou d’un autre problème, vous pouvez faire pointer le serveur d’archivage sur une nouvelle base de données à l’aide de l’applet de commande **Set-CsArchivingServer**.
  
Dans l’exemple suivant, l’emplacement de la base de données d’archivage du serveur d’archivage ArchivingServer: ATL-CS-001.contoso.com est modifié. Dans cet exemple, la nouvelle base de données se trouve sur ArchivingDatabase:atl-sql-001.contoso.com :
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


