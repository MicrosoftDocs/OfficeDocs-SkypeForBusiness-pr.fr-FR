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
description: Après avoir supprimé un serveur de surveillance, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données du serveur. Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753326"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Suppression de la base de données SQL Server pour un serveur de surveillance

Après avoir supprimé un serveur de surveillance, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données du serveur. Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Pour supprimer la base de données SQL Server à l’aide du générateur de topologies

1. Sur le serveur frontal Skype entreprise Server 2019, ouvrez le générateur de topologie.
    
2. Dans le générateur de topologies, accédez à **composants partagés** , puis **magasins SQL Server**, cliquez avec le bouton droit sur l’instance SQL Server associée au serveur de surveillance supprimé ou reconfiguré, puis cliquez sur **supprimer**.
    
3. Publiez la topologie, puis vérifiez l’état de la réplication.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Pour supprimer les fichiers de base de données du serveur SQL Server

1. Pour supprimer les bases de données sur le serveur SQL Server, vous devez être membre du groupe sysadmins SQL Server pour le serveur SQL Server sur lequel vous supprimez les fichiers de base de données.
    
2. Ouvrez Skype entreprise Server Management Shell.
    
3. Dans la ligne de commande, tapez le code suivant :
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Où _\<FQDN\>_ est le nom de domaine complet (FQDN) du serveur de base de données et _\<instance\>_ est l’instance de base de données nommée facultative. 
    
4. Lorsque l’applet de commande **Uninstall-applet csdatabase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou sur entrée) pour continuer, ou appuyez sur N, puis entrez si vous voulez arrêter l’applet de commande (en cas d’erreur). 
    

