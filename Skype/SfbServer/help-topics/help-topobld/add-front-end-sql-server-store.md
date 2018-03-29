---
title: Ajouter banque de Front End SQL Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Un déploiement du serveur Standard Edition installe automatiquement les logiciels de base de données Microsoft SQL Server Express et une base de données de SQL Server. Par conséquent, toutes les options sont préremplies, et vous ne pouvez pas apporter des modifications à la configuration par défaut.
ms.openlocfilehash: facb2e91511323e6fc87015016b060ba5076c8f6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-sql-server-store"></a>Ajouter banque de Front End SQL Server
 
Un déploiement du serveur Standard Edition installe automatiquement les logiciels de base de données Microsoft SQL Server Express et une base de données de SQL Server. Par conséquent, toutes les options sont préremplies, et vous ne pouvez pas apporter des modifications à la configuration par défaut.
  
Le pool frontal d’un déploiement de serveur Enterprise Edition nécessite une édition 64 bits prise en charge du logiciel de base de données SQL Server pour la base de données back-end. Vous pouvez sélectionner une base de données SQL Server défini précédemment à utiliser pour la base de données back-end, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine pleinement qualifié (FQDN) du serveur sur lequel la base de données SQL Server est résident et l’instance de SQL S serveur que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez). Vous pouvez également choisir d’activer la mise en miroir sur la banque d’informations de SQL Server et spécifier un témoin pour le basculement automatique de la mise en miroir.
  
Pour plus d’informations sur SQL Server prend en charge, consultez les [logiciels de base de données et la prise en charge des clusters](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) dans la documentation de prise en charge. Pour plus d’informations sur la configuration de SQL Server pour la base de données back-end, consultez [Configuration de SQL Server de Lync Server 2010](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) dans la documentation de déploiement.
  
> [!NOTE]
> Si le compte qui est utilisé pour publier la topologie a les autorisations et droits d’utilisateur appropriés, vous pouvez créer la base de données back-end (communications en temps réel (RTC)) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données ultérieurement, y compris dans le cadre de la procédure d’installation. 
  
> [!NOTE]
> Pour installer et déployer des bases de données sur le serveur SQL Server pour un déploiement Enterprise Edition, vous devez être membre du groupe sysadmin de SQL Server pour le serveur SQL Server où vous installez les fichiers de base de données. Si vous n’êtes pas un membre du groupe sysadmin de SQL Server, vous devez demander à être ajouté au groupe jusqu'à ce que les fichiers de base de données sont déployés. Si un membre du groupe administrateurs système n’est pas possible, vous devez fournir votre administrateur de base de données SQL Server avec le script à configurer et à déployer les bases de données. Pour plus d’informations sur les droits de l’utilisateur et les autorisations dont vous avez besoin pour effectuer les procédures, voir [Autorisations de déploiement de SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx). 
  

