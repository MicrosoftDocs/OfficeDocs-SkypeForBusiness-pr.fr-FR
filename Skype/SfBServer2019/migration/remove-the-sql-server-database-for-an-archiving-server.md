---
title: Supprimer la base de données SQL Server pour un serveur d’archivage
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après la suppression d’un serveur d’archivage, vous pouvez supprimer les bases de données SQL Server hébergeant les données du pool. Utilisez les procédures suivantes pour supprimer les définitions de générateur de topologie, puis supprimer les fichiers journaux et de base de données à partir du serveur de base de données.
ms.openlocfilehash: b7c1fe6591564a690ea1da55fb65eb1071661d63
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370800"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Supprimer la base de données SQL Server pour un serveur d’archivage

Après la suppression d’un serveur d’archivage, vous pouvez supprimer les bases de données SQL Server hébergeant les données du pool. Utilisez les procédures suivantes pour supprimer les définitions de générateur de topologie, puis supprimer les fichiers journaux et de base de données à partir du serveur de base de données.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Pour supprimer la base de données SQL Server à l’aide du Générateur de topologie

1. Sur Skype pour Business Server 2019 serveur frontal, ouvrez le Générateur de topologie.
    
2. Dans le Générateur de topologie, accédez à **Composants partagés** puis **Magasins SQL Server**, cliquez sur le serveur SQL Server instance associé supprimé ou reconfiguré serveur d’archivage, puis cliquez sur **Supprimer**.
    
3. Publiez la topologie, puis vérifier l’état de réplication. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Pour supprimer les fichiers de base de données de SQL Server.

1. Pour supprimer les bases de données sur le serveur SQL Server, vous devez être membre du groupe administrateurs système SQL Server pour lequel vous voulez supprimer les fichiers de base de données SQL Server. 
    
2. Ouvrez le Skype pour Business Server Management Shell.
    
3. Dans la ligne de commande, tapez ce qui suit :
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Où _ \<nom de domaine complet\> _ est le nom de domaine complet (FQDN) du serveur de base de données, et _ \<instance\> _ est l’instance de base de données nommée (autrement dit, si elle a été définie). 
    
4. Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou entrez) pour continuer ou appuyez sur N et appuyez sur entrée, si vous souhaitez arrêter l’applet de commande (s’il y a des erreurs). 
    

