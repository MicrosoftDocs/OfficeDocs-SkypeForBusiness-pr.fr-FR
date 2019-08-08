---
title: Suppression des instances et des bases de données SQL Server sur le serveur principal
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous supprimez les bases de données et les instances Microsoft SQL Server après avoir supprimé les serveurs qui en dépendent ou après avoir reconfiguré les serveurs pour utiliser une autre base de données. Vous devez effectuer la procédure décrite dans cette rubrique lorsque vous supprimez le serveur SQL Server actuel ou que vous reconfigurez le serveur actuel de telle sorte qu’il affiche les bases de données obsolètes ou indisponibles.
ms.openlocfilehash: 6c526499e3036c9a10b8dc92ccc519f21ae8bc96
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244200"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Suppression des instances et des bases de données SQL Server sur le serveur principal

Vous supprimez les bases de données et les instances Microsoft SQL Server après avoir supprimé les serveurs qui en dépendent ou après avoir reconfiguré les serveurs pour utiliser une autre base de données. Vous devez effectuer la procédure décrite dans cette rubrique lorsque vous supprimez le serveur SQL Server actuel ou que vous reconfigurez le serveur actuel de telle sorte qu’il affiche les bases de données obsolètes ou indisponibles.
  
Pour supprimer les bases de données ou les instances du serveur d’archivage ou du serveur de surveillance, vous devez d’abord supprimer le rôle de serveur. De même, pour supprimer les instances ou bases de données du pool frontal, vous devez d’abord supprimer ou reconfigurer le rôle de serveur dépendant. Ces procédures n’effectuent aucune distinction entre les bases de données colocalisées ou les instances distinctes pour les serveurs. Les procédures ne sont pas affectées par la colocalisation des bases de données.
  
## <a name="in-this-section"></a>Contenu de cette section

- [Suppression de la base de données SQL Server pour un pool frontal](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Suppression de la base de données SQL Server pour un serveur de surveillance](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Suppression de la base de données SQL Server pour un serveur d’archivage](remove-the-sql-server-database-for-an-archiving-server.md)
    

