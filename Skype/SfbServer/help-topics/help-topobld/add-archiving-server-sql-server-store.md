---
title: Ajouter l’archivage de base de serveur SQL Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: Serveur d’archivage nécessite une édition 64 bits prise en charge du logiciel de base de données SQL Server pour stocker les données d’archive. Vous pouvez sélectionner une base de données de SQL Server défini précédemment à utiliser pour l’archivage ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine pleinement qualifié (FQDN) du serveur sur lequel réside la base de données SQL Server et l’instance de SQL Server qui vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: 2c63b6bf71c156bc62e07add023f3049af399095
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-archiving-server-sql-server-store"></a>Ajouter l’archivage de base de serveur SQL Server
 
Serveur d’archivage nécessite une édition 64 bits prise en charge du logiciel de base de données SQL Server pour stocker les données d’archive. Vous pouvez sélectionner une base de données de SQL Server défini précédemment à utiliser pour l’archivage ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine pleinement qualifié (FQDN) du serveur sur lequel réside la base de données SQL Server et l’instance de SQL Server qui vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
  
> [!NOTE]
> Si le compte qui est utilisé pour publier la topologie a les autorisations et droits d’utilisateur appropriés, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données ultérieurement, dans le cadre de la procédure d’installation, ou dans le cas contraire. 
  
> [!NOTE]
> Pour installer et déployer des bases de données sur le serveur SQL Server pour l’archivage, vous devez être membre du groupe sysadmin de SQL Server pour le serveur SQL Server où vous installez les fichiers de base de données. Si vous n’êtes pas un membre du groupe sysadmin de SQL Server, vous devez demander à être ajouté au groupe jusqu'à ce que les fichiers de base de données sont déployés. Si un membre du groupe administrateurs système n’est pas possible, vous devez fournir votre administrateur de base de données SQL Server avec le script à configurer et à déployer les bases de données. Pour plus d’informations sur les droits de l’utilisateur et les autorisations dont vous avez besoin pour accomplir les procédures, consultez [Autorisations de déploiement pour SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) dans la documentation de déploiement.
  

