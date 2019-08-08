---
title: Suppression de la base de données SQL Server pour un pool frontal
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après avoir supprimé un pool frontal ou reconfiguré le pool pour utiliser une autre base de données, vous pouvez supprimer les bases de données SQL Server qui ont hébergé les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
ms.openlocfilehash: d22a90401bdfa4a2897a18805e8b9c588892c5fb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241562"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Suppression de la base de données SQL Server pour un pool frontal

Après avoir supprimé un pool frontal ou reconfiguré le pool pour utiliser une autre base de données, vous pouvez supprimer les bases de données SQL Server qui ont hébergé les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Pour supprimer la base de données SQL Server à l’aide du générateur de topologie

1. À partir du serveur frontal Skype entreprise Server 2019, ouvrez le générateur de topologie et téléchargez la topologie existante. 
    
2. Dans le générateur de topologie, accédez à **composants partagés** , puis aux **magasins SQL Server**, cliquez avec le bouton droit sur l’instance SQL Server associée au pool frontal supprimé ou reconfiguré, puis cliquez sur **supprimer**.
    
3. Publiez la topologie, puis vérifiez l’état de la réplication. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Pour supprimer des bases de données d’application et d’application du serveur SQL Server

1. Pour supprimer les bases de données du serveur SQL Server, vous devez être membre du groupe sysadmin SQL Server pour le serveur SQL sur lequel vous supprimez les fichiers de la base de données. 
    
2. Ouvrez Skype entreprise Server Management Shell.
    
3. Pour supprimer la base de données du magasin utilisateur de la liste, tapez:
    
   ```
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Où _ \<FQDN\> _ est le nom de domaine complet (FQDN) du serveur de base de données _ \<et\> l’instance_ est l’instance de base de données nommée (autrement dit, le cas échéant). 
    
4. Pour supprimer la base de données du magasin d’applications de réserve, tapez:
    
   ```
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Où _ \<FQDN\> _ est le nom de domaine complet du serveur de base de données et _ \<l’instance\> _ est l’instance de base de données nommée (autrement dit, le cas échéant). 
    
5. Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou entrée) pour continuer, ou appuyez sur N, puis sur entrée si vous voulez arrêter l’applet de commande (en cas d’erreur). 
    

