---
title: Suppression de la base de données SQL Server pour un serveur de surveillance
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
description: Après avoir supprimé un serveur de surveillance, vous pouvez supprimer les bases SQL Server données qui hébergeaient les données du serveur. Utilisez les procédures suivantes pour supprimer les définitions du Générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753326"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Suppression de la base de données SQL Server pour un serveur de surveillance

Après avoir supprimé un serveur de surveillance, vous pouvez supprimer les bases SQL Server données qui hébergeaient les données du serveur. Utilisez les procédures suivantes pour supprimer les définitions du Générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Pour supprimer la base de données SQL Server à l’aide du Générateur de topologie

1. Sur le serveur frontal Skype Entreprise Server 2019, ouvrez le Générateur de topologie.
    
2. Dans le Générateur de topologie, accédez à **Composants partagés,** puis **SQL Server Stores,** cliquez avec le bouton droit sur l’instance SQL Server associée au serveur de surveillance supprimé ou reconfiguré, puis cliquez sur **Supprimer.**
    
3. Publiez la topologie, puis vérifiez l’état de la réplication.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Pour supprimer les fichiers de base de données du serveur SQL Server

1. Pour supprimer les bases de données sur le serveur SQL Server, vous devez être membre du groupe sysadmins SQL Server pour le serveur SQL Server sur lequel vous supprimez les fichiers de base de données.
    
2. Ouvrez Skype Entreprise Server Management Shell.
    
3. Dans la ligne de commande, tapez le code suivant :
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Où se trouve le nom de domaine complet (FQDN) du serveur de base de données et est l’instance de base de données  _\<FQDN\>_  _\<instance\>_ nommée facultative. 
    
4. Lorsque l’cmdlet **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou Entrée) pour continuer, ou appuyez sur N, puis sur Entrée si vous souhaitez arrêter l’cmdlet (s’il existe des erreurs). 
    

