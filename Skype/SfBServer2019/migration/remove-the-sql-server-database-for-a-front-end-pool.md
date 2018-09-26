---
title: Supprimer la base de données SQL Server pour un pool frontal
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Une fois que vous supprimez un pool frontal ou reconfigurez le pool pour utiliser une autre base de données, vous pouvez supprimer les bases de données SQL Server hébergeant les données du pool. Utilisez les procédures suivantes pour supprimer les définitions de générateur de topologie, puis supprimer les fichiers journaux et de base de données à partir du serveur de base de données.
ms.openlocfilehash: 65fd0367051e32aa081fa13859632504e1331669
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028606"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Supprimer la base de données SQL Server pour un pool frontal

Une fois que vous supprimez un pool frontal ou reconfigurez le pool pour utiliser une autre base de données, vous pouvez supprimer les bases de données SQL Server hébergeant les données du pool. Utilisez les procédures suivantes pour supprimer les définitions de générateur de topologie, puis supprimer les fichiers journaux et de base de données à partir du serveur de base de données.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Pour supprimer la base de données SQL Server à l’aide du Générateur de topologie

1. Depuis Skype pour Business Server 2019 serveur frontal, ouvrez le Générateur de topologie et téléchargez la topologie existante. 
    
2. Dans le Générateur de topologie, accédez à **Composants partagés** puis **Magasins SQL Server**, cliquez sur l’instance SQL Server associée au pool frontal supprimé ou reconfiguré, puis cliquez sur **Supprimer**.
    
3. Publiez la topologie, puis vérifiez l’état de réplication. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Pour supprimer les bases de données utilisateur et d’application de SQL server.

1. Pour supprimer les bases de données sur le serveur SQL server, vous devez être membre du groupe administrateurs système SQL Server pour lequel vous voulez supprimer les fichiers de base de données SQL server. 
    
2. Ouvrez Skype pour Business Server Management Shell.
    
3. Pour supprimer la base de données pour le magasin d’utilisateurs pool, tapez :
    
  ```
  Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    Où _ \<nom de domaine complet\> _ est le nom de domaine complet (FQDN) du serveur de base de données, et _ \<instance\> _ est l’instance de base de données nommée (autrement dit, si elle a été définie). 
    
4. Pour supprimer la base de données pour le magasin d’application pool, tapez :
    
  ```
  Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    Où _ \<nom de domaine complet\> _ est le nom de domaine complet du serveur de base de données, et _ \<instance\> _ est l’instance de base de données nommée (autrement dit, si elle a été définie). 
    
5. Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou entrez) pour continuer ou appuyez sur N et appuyez sur entrée, si vous souhaitez arrêter l’applet de commande (s’il y a des erreurs). 
    

