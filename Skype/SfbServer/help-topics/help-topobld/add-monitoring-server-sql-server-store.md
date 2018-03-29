---
title: Ajouter la surveillance de base de serveur SQL Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: Monitoring Server nécessite une édition 64 bits prise en charge du logiciel de base de données SQL Server pour stocker les données d’analyse. Vous pouvez sélectionner une base de données SQL Server défini précédemment à utiliser pour l’analyse, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine pleinement qualifié (FQDN) du serveur sur lequel la base de données SQL Server doit résider, en plus de l’instance de SQL Serveur que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: f52f44acd9ca57112da75fcc368d8ebaae99b081
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-monitoring-server-sql-server-store"></a>Ajouter la surveillance de base de serveur SQL Server
 
Monitoring Server nécessite une édition 64 bits prise en charge du logiciel de base de données SQL Server pour stocker les données d’analyse. Vous pouvez sélectionner une base de données SQL Server défini précédemment à utiliser pour l’analyse, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine pleinement qualifié (FQDN) du serveur sur lequel la base de données SQL Server doit résider, en plus de l’instance de SQL Serveur que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
  
Pour plus d’informations sur SQL Server prend en charge, consultez les [logiciels de base de données et la prise en charge des clusters](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) dans la documentation de prise en charge. Pour plus d’informations sur la surveillance de base de données, y compris colocalisation de la surveillance de la base de données, reportez-vous à la section [Emplacement de serveur pris en charge](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) dans la documentation de prise en charge, la[planification de l’analyse](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) dans la documentation de planification et de la [de données de SQL Server et l’emplacement du fichier journal](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) dans la documentation de déploiement.
  
> [!NOTE]
> Si le compte utilisé pour publier la topologie a les autorisations et droits d’utilisateur appropriés, vous pouvez créer la base de données de contrôle lorsque vous publiez votre topologie. Vous pouvez également créer la base de données ultérieurement, y compris dans le cadre de la procédure d’installation. > Pour installer et déployer des bases de données sur le serveur SQL Server pour l’analyse, vous devez être un membre du groupe sysadmin de SQL Server pour le serveur SQL Server où vous installez les fichiers de base de données. Si vous n’êtes pas un membre du groupe sysadmin de SQL Server, vous devez demander à être ajouté au groupe jusqu'à ce que les fichiers de base de données sont déployés. Si un membre du groupe administrateurs système n’est pas possible, vous devez fournir votre administrateur de base de données SQL Server avec le script à configurer et à déployer les bases de données. Pour plus d’informations sur les droits de l’utilisateur et les autorisations dont vous avez besoin pour effectuer ces procédures, consultez [Autorisations de déploiement pour SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) dans la documentation de déploiement.
  

