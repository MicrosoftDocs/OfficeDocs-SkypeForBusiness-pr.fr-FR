---
title: Suppression de la base de données SQL Server pour un pool frontal
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Après avoir supprimé un pool frontal ou reconfiguré le pool pour utiliser une autre base de données, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du Générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753406"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Suppression de la base de données SQL Server pour un pool frontal

Après avoir supprimé un pool frontal ou reconfiguré le pool pour utiliser une autre base de données, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du Générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Pour supprimer la base de données SQL Server à l’aide du Générateur de topologie

1. À partir du serveur frontal Skype Entreprise Server 2019, ouvrez le Générateur de topologie et téléchargez la topologie existante. 
    
2. Dans le Générateur de topologie, accédez à **Composants partagés,** puis **SQL Server Stores,** cliquez avec le bouton droit sur l’instance SQL Server associée au pool frontal supprimé ou reconfiguré, puis cliquez sur **Supprimer.**
    
3. Publiez la topologie, puis vérifiez l’état de la réplication. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Pour supprimer des bases de données utilisateur et d’application du SQL serveur

1. Pour supprimer les bases de données sur le serveur SQL, vous devez être membre du groupe SQL Server sysadmins pour le serveur SQL où vous supprimez les fichiers de base de données. 
    
2. Ouvrez Skype Entreprise Server Management Shell.
    
3. Pour supprimer la base de données du magasin d’utilisateurs du pool, tapez :
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Où se trouve le nom de domaine complet (FQDN) du serveur de base de données et l’instance de base de données nommée (si elle  _\<FQDN\>_  _\<instance\>_ a été définie). 
    
4. Pour supprimer la base de données du magasin d’applications du pool, tapez :
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Où  _\<FQDN\>_ se trouve le nom deqdn du serveur de base de données et l’instance de base de données nommée (c’est-à-dire, si une instance a été  _\<instance\>_ définie). 
    
5. Lorsque l’cmdlet **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou Entrée) pour continuer, ou appuyez sur N, puis sur Entrée si vous souhaitez arrêter l’cmdlet (s’il existe des erreurs). 
    

