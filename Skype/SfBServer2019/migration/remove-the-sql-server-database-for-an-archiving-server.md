---
title: Suppression de la base de données SQL Server pour un serveur d’archivage
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
description: Après avoir supprimé un serveur d’archivage, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du Générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753306"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Suppression de la base de données SQL Server pour un serveur d’archivage

Après avoir supprimé un serveur d’archivage, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du Générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Pour supprimer la base de données SQL Server à l’aide du Générateur de topologie

1. Sur le serveur frontal Skype Entreprise Server 2019, ouvrez le Générateur de topologie.
    
2. Dans le Générateur de topologie, accédez à **Composants partagés,** puis **SQL Server Stores,** cliquez avec le bouton droit sur l’instance SQL Server associée au serveur d’archivage supprimé ou reconfiguré, puis cliquez sur **Supprimer.**
    
3. Publiez la topologie, puis vérifiez l’état de la réplication. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Pour supprimer les fichiers de base de données de SQL Server

1. Pour supprimer les bases de données sur le serveur SQL Server, vous devez être membre du groupe des administrateurs système SQL Server chargés du serveur sur lequel vous voulez supprimer les fichiers de base de données. 
    
2. Ouvrez Skype Entreprise Server Management Shell.
    
3. Dans la ligne de commande, tapez le code suivant :
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Où se trouve le nom de domaine complet (FQDN) du serveur de base de données et l’instance de base de données nommée (si elle  _\<FQDN\>_  _\<instance\>_ a été définie). 
    
4. Lorsque l’cmdlet **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou Entrée) pour continuer, ou appuyez sur N, puis sur Entrée si vous souhaitez arrêter l’cmdlet (s’il existe des erreurs). 
    

