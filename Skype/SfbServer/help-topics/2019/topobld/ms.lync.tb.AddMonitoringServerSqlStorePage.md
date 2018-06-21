---
title: Ajouter un magasin SQL Server du serveur de surveillance
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: Le serveur de surveillance requiert une édition 64 bits prise en charge du logiciel de base de données SQL Server pour stocker les données d’analyse. Vous pouvez sélectionner une base de données SQL Server précédemment défini pour être utilisé pour la surveillance, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel la base de données SQL Server réside, en plus de l’instance de SQL Serveur que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: 362f4be3d778d0c5607f6c0ee1233d85d6b9149e
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19969770"
---
# <a name="add-monitoring-server-sql-server-store"></a>Ajouter un magasin SQL Server du serveur de surveillance
 
Le serveur de surveillance requiert une édition 64 bits prise en charge du logiciel de base de données SQL Server pour stocker les données d’analyse. Vous pouvez sélectionner une base de données SQL Server précédemment défini pour être utilisé pour la surveillance, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel la base de données SQL Server réside, en plus de l’instance de SQL Serveur que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
  
Pour plus d’informations sur SQL Server prennent en charge, voir le [logiciel de base de données et le clustering avec prise en charge](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) dans la documentation de prise en charge. Pour plus d’informations sur la base de données surveillance, y compris la colocalisation de la base de données de surveillance, voir [l’Emplacement du serveur pris en charge](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) dans la documentation de prise en charge, la[planification d’analyse](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) dans la documentation de planification et [de données SQL Server et l’emplacement des fichiers journaux](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) dans la documentation de déploiement.
  
> [!NOTE]
> Si le compte utilisé pour publier la topologie possède les droits d’utilisateur appropriés et les autorisations, vous pouvez créer la base de données de surveillance lorsque vous publiez votre topologie. Vous pouvez également créer la base de données ultérieurement, y compris dans le cadre de la procédure d’installation. > Pour installer et déployer les bases de données sur le serveur SQL Server pour la surveillance, vous devez être membre du groupe administrateurs système SQL Server pour le serveur SQL Server où vous installez les fichiers de base de données. Si vous n’êtes pas un membre du groupe sysadmin de SQL Server, vous devez demander à ajouter au groupe jusqu'à ce que les fichiers de base de données sont déployés. Si vous ne peut pas être établie à un membre du groupe administrateurs système, vous devez fournir votre administrateur de base de données SQL Server avec le script pour configurer et déployer les bases de données. Pour plus d’informations sur les droits d’utilisateur et les autorisations dont vous avez besoin pour effectuer ces procédures, voir [Autorisations de déploiement pour SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) dans la documentation de déploiement.
  

