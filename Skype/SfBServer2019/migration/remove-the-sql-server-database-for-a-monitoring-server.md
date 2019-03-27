---
title: Suppression de la base de données SQL Server pour un serveur de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Une fois que vous supprimez un serveur de surveillance, vous pouvez supprimer les bases de données SQL Server hébergeant les données du serveur. Utilisez les procédures suivantes pour supprimer les définitions de générateur de topologie, puis supprimer les fichiers journaux et de base de données à partir du serveur de base de données.
ms.openlocfilehash: 7e299eb2de3fc0820cd4497c2956c71ceec79910
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876341"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Suppression de la base de données SQL Server pour un serveur de surveillance

Une fois que vous supprimez un serveur de surveillance, vous pouvez supprimer les bases de données SQL Server hébergeant les données du serveur. Utilisez les procédures suivantes pour supprimer les définitions de générateur de topologie, puis supprimer les fichiers journaux et de base de données à partir du serveur de base de données.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Pour supprimer la base de données SQL Server à l’aide du Générateur de topologie

1. Sur Skype pour Business Server 2019 serveur frontal, ouvrez le Générateur de topologie.
    
2. Dans le Générateur de topologie, accédez à **Composants partagés** puis **Magasins SQL Server**, cliquez sur le serveur SQL Server instance associé supprimé ou reconfiguré le serveur de surveillance, puis cliquez sur **Supprimer**.
    
3. Publiez la topologie, puis vérifier l’état de réplication.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Pour supprimer les fichiers de base de données de SQL Server.

1. Pour supprimer les bases de données sur le serveur SQL Server, vous devez être membre du groupe administrateurs système SQL Server pour le serveur SQL Server où vous supprimez les fichiers de base de données.
    
2. Ouvrez le Skype pour Business Server Management Shell.
    
3. Dans la ligne de commande, tapez ce qui suit :
    
   ```
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Où _ \<nom de domaine complet\> _ est le nom de domaine complet (FQDN) du serveur de base de données, et _ \<instance\> _ l’instance de base de données nommée facultative. 
    
4. Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou entrez) pour continuer ou appuyez sur N et appuyez sur entrée, si vous souhaitez arrêter l’applet de commande (s’il y a des erreurs). 
    

