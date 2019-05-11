---
title: Modifier les options de base de données d’archivage dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Résumé : Découvrez comment modifier les options de base de données d’archivage pour Skype pour Business Server.'
ms.openlocfilehash: b2ffa1cfd9686be941cca2a1ffdc2684006dde50
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884971"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Modifier les options de base de données d’archivage dans Skype pour Business Server

**Résumé :** Découvrez comment modifier les options de base de données d’archivage pour Skype pour Business Server.
  
Si vous déployez l’archivage à l’aide du stockage SQL Server pour l’archivage du stockage pour tous vos utilisateurs, vous pouvez apporter les modifications de stockage la base de données suivante :
  
- Utiliser une autre base de données SQL Server pour l’archivage du stockage. Cela inclut la base de données principale d’archivage et d’une base de données que vous utilisez pour la mise en miroir SQL Server.
    
- Passez à l’intégration de Microsoft Exchange pour stocker les données d’archivage et de fichiers sur des serveurs Exchange. Si tous vos utilisateurs sont hébergés sur vos serveurs Exchange et que vous souhaitez utiliser le stockage de Microsoft Exchange pour tous les utilisateurs dans votre déploiement, vous devez supprimer les bases de données du magasin SQL Server à partir de votre topologie. 
    
Pour effectuer une de ces modifications, vous devez exécuter le Générateur de topologie, apportez les modifications et puis publiez la topologie à nouveau. Ne spécifiez pas d’informations **magasin SQL Server de l’archivage** ou **la mise en miroir activer magasin SQL Server** , à moins d’avoir Skype pour les utilisateurs professionnels qui ne sont pas hébergés sur des serveurs Exchange.
  
## <a name="change-archiving-database-options"></a>Modifier les options de la base de données d’archivage

1. Sur un ordinateur qui exécute Skype pour Business Server ou sur lequel le Skype pour les outils d’administration Business Server sont installés, ouvrez une session en utilisant un compte qui est membre du groupe utilisateurs local (ou un compte disposant de droits utilisateur équivalents).
    
    > [!NOTE]
    > Vous pouvez définir une topologie en utilisant un compte qui est un membre du groupe utilisateurs local, mais pour publier une topologie qui est nécessaire pour ajouter un composant à la topologie, vous devez utiliser un compte qui est membre du groupe **Admins** du domaine et le **RTCUniversalSer verAdmins** groupe et qui dispose d’autorisations Contrôle total (autrement dit, lire, écrire et modifier) sur le partage de fichiers que vous utilisez pour le Skype Business Server magasin de fichiers (c'est-à-dire, afin que le Générateur de topologie puisse configurer le contrôle d’accès discrétionnaire requis listes (DACL), ou un compte disposant de droits équivalents.
  
2. Démarrez le Générateur de topologie.
    
3. Dans l’arborescence de la console, accédez au pool de serveurs frontaux dans lequel vous avez déployé l’archivage, puis cliquez sur le nom du pool de serveurs frontaux dans lequel vous voulez modifier les options de base de données.
    
4. Dans le menu **Action**, cliquez sur **Modifier les propriétés**. 
    
5. Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.
    
6. Faites défiler la liste jusqu’à **Archivage**.
    
7. Dans **Archivage**, procédez comme suit :
    
   - Pour choisir un autre magasin SQL Server existant, sous **Magasin SQL Server d’archivage**, dans la zone de liste déroulante, procédez comme suit :
    
   - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.
    
   - Pour spécifier un nouveau magasin SQL Server, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir un nouveau magasin SQL Server**, procédez comme suit :
    
     - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.
    
     - Pour spécifier un nouveau magasin SQL Server, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir nouveau magasin SQL Server** , procédez comme suit :
    
       - Dans **Nom de domaine complet de SQL Server**, spécifiez le nom de domaine complet du serveur sur lequel vous souhaitez créer le nouveau magasin SQL Server.
    
       - Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
    
       - Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL se trouve dans la relation de mise en miroir** , puis, dans le **numéro de port de mise en miroir**, spécifiez le numéro de port.
    
   - Pour ajouter le magasin SQL Server ou choisir un autre magasin SQL Server existant pour la mise en miroir, sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis procédez comme suit :
    
     - Pour utiliser un magasin SQL Server pour la mise en miroir, dans la zone de liste déroulante **miroir du magasin SQL Server d’archivage** , cliquez sur le nom du magasin SQL Server que vous souhaitez utiliser pour la mise en miroir.
    
     - Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir nouveau magasin SQL Server** , effectuez l’une des options suivantes :
    
       a. Dans **Nom de domaine complet de SQL Server**, spécifiez le nom de domaine complet du serveur SQL sur lequel vous souhaitez créer le nouveau magasin SQL Server.
    
       b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
    
       c. Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL se trouve dans la relation de mise en miroir** , puis, dans le **numéro de port de mise en miroir**, spécifiez le numéro de port.
    
   - Si vous activez la mise en miroir SQL Server et que vous souhaitez ajouter ou modifier un témoin (une troisième et distincte instance SQL Server qui peut détecter l’intégrité des instances de serveur et de mise en miroir de SQL Server principales) de la mise en miroir de SQL Server, sélectionnez le témoin de mise en miroir utiliser SQL Server **à Activer le basculement automatique** case à cocher, puis effectuez l’une des opérations suivantes :
    
      a. Dans **Nom de domaine complet de SQL Server**, spécifiez le nom de domaine complet du serveur sur lequel vous souhaitez créer le nouveau serveur SQL témoin de mise en miroir.
    
      b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.
    
      c. Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL se trouve dans la relation de mise en miroir** , puis, dans le **numéro de port de mise en miroir**, spécifiez le numéro de port.
    
   - Pour activer l’intégration de Microsoft Exchange pour stocker les données d’archivage et de fichiers sur des serveurs Exchange (si tous les utilisateurs dans votre déploiement sont hébergés sur vos serveurs Exchange), supprimez toutes les informations pour l’archivage des bases de données.
    
     > [!IMPORTANT]
     > Si vous avez tout Skype pour les utilisateurs professionnels qui ne sont pas hébergés sur des serveurs Exchange, ne supprimez pas les informations de stockage SQL Server. 
  
8. Pour enregistrer la configuration, cliquez sur **OK**.
    
    > [!IMPORTANT]
    > Les modifications apportées dans le Générateur de topologie ne prennent effet jusqu'à ce que vous publiez la nouvelle topologie. Pour plus d’informations, voir [Ajouter des bases de données d’archivage à un déploiement existant dans Skype pour Business Server](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Changer l’emplacement de la base d’archivage à l’aide de Windows PowerShell

Dans la plupart des cas, vous n’aurez pas à changer l’emplacement de cette base de données d’archivage qui est indiqué lorsque vous installez le serveur d’archivage. Cependant, en cas de panne matérielle ou d’un autre problème, vous pouvez faire pointer le serveur d’archivage sur une nouvelle base de données à l’aide de l’applet de commande **Set-CsArchivingServer**.
  
L’exemple suivant modifie l’emplacement de la base de données d’archivage pour l’archivingserver : ATL-cs-001.contoso.com serveur d’archivage. Dans cet exemple, la nouvelle base de données se trouve sur ArchivingDatabase:atl-sql-001.contoso.com :
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


