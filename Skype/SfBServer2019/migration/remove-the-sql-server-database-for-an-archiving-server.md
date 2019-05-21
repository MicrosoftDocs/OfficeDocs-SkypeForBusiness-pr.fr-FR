---
title: Suppression de la base de données SQL Server pour un serveur d’archivage
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après avoir supprimé un serveur d’archivage, vous pouvez supprimer les bases de données SQL Server qui ont hébergé les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
ms.openlocfilehash: 975252ee991df507f02bc490d1d2ef2614f3b475
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307104"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Suppression de la base de données SQL Server pour un serveur d’archivage

Après avoir supprimé un serveur d’archivage, vous pouvez supprimer les bases de données SQL Server qui ont hébergé les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Pour supprimer la base de données SQL Server à l’aide du générateur de topologie

1. Sur le serveur frontal Skype entreprise Server 2019, ouvrez le générateur de topologie.
    
2. Dans le générateur de topologie, accédez à **composants partagés** puis aux **magasins SQL Server**, cliquez avec le bouton droit sur l’instance SQL Server associée au serveur d’archivage supprimé ou reconfiguré, puis cliquez sur **supprimer**.
    
3. Publiez la topologie, puis vérifiez l’état de la réplication. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Pour supprimer les fichiers de base de données du serveur SQL Server

1. Pour supprimer les bases de données du serveur SQL Server, vous devez être membre du groupe sysadmin SQL Server pour le serveur SQL sur lequel vous supprimez les fichiers de la base de données. 
    
2. Ouvrez Skype entreprise Server Management Shell.
    
3. Dans la ligne de commande, tapez ce qui suit :
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Où _ \<FQDN\> _ est le nom de domaine complet (FQDN) du serveur de base de données _ \<et\> l’instance_ est l’instance de base de données nommée (autrement dit, le cas échéant). 
    
4. Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou entrée) pour continuer, ou appuyez sur N, puis sur entrée si vous voulez arrêter l’applet de commande (en cas d’erreur). 
    

