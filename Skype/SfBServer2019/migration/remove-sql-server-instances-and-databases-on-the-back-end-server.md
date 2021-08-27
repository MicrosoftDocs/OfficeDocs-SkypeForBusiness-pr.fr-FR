---
title: Suppression des instances et des bases de données SQL Server sur le serveur principal
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Vous supprimez les Microsoft SQL Server et les instances après avoir supprimé les serveurs en cours d’exécution qui en dépendent ou après avoir reconfiguré les serveurs pour utiliser une autre base de données. Vous devez effectuer la procédure de cette rubrique lorsque vous retirez le SQL Server actuel ou reconfigurez le serveur actuel de telle sorte qu’il rende les bases de données obsolètes ou indisponibles.
ms.openlocfilehash: dafd1589bc4d1624a71998813fe785841cbfb713
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582028"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Suppression des instances et des bases de données SQL Server sur le serveur principal

Vous supprimez les Microsoft SQL Server et les instances après avoir supprimé les serveurs en cours d’exécution qui en dépendent ou après avoir reconfiguré les serveurs pour utiliser une autre base de données. Vous devez effectuer la procédure de cette rubrique lorsque vous retirez le SQL Server actuel ou reconfigurez le serveur actuel de telle sorte qu’il rende les bases de données obsolètes ou indisponibles.
  
Pour supprimer les bases de données ou les instances du serveur d’archivage ou du serveur de surveillance, vous devez d’abord supprimer le rôle serveur. De même, pour supprimer les instances ou les bases de données pour le pool frontal, vous devez d’abord supprimer ou reconfigurer le rôle serveur dépendant. Ces procédures ne font pas de distinction entre les bases de données colocalisées et les instances séparées des serveurs. Elles ne sont pas affectées par la colocalisation des bases de données.
  
## <a name="in-this-section"></a>Dans cette section

- [Suppression de la base de données SQL Server pour un pool frontal](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Suppression de la base de données SQL Server pour un serveur de surveillance](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Suppression de la base de données SQL Server pour un serveur d’archivage](remove-the-sql-server-database-for-an-archiving-server.md)
    

