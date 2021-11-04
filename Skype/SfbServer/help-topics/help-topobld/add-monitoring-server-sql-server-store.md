---
title: Ajouter un magasin SQL Server du serveur de surveillance
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: Le serveur de surveillance nécessite une édition 64 bits prise en charge SQL Server base de données pour stocker les données de surveillance. Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour la surveillance ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel résidera la base de données SQL Server, en plus de l’instance de SQL Server que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: a9417132e1b0bc2d6fc39bffaa4dd1abf86c6817
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743830"
---
# <a name="add-monitoring-server-sql-server-store"></a>Ajouter un magasin SQL Server du serveur de surveillance

Le serveur de surveillance nécessite une édition 64 bits prise en charge SQL Server base de données pour stocker les données de surveillance. Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour la surveillance ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel résidera la base de données SQL Server, en plus de l’instance de SQL Server que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).

Pour plus d’informations sur SQL Server prise en charge, voir La prise en charge des logiciels de base de données et du [clustering](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) dans la documentation de prise en charge. Pour plus d’informations sur la base de données de surveillance, y compris la cocation de la base de données de surveillance, voir [Emplacement](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) du serveur pris en charge dans la documentation de prise en charge,[Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in the Planning documentation and SQL Server Data and Log File [Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.

> [!NOTE]
> Si le compte utilisé pour publier la topologie dispose des droits d’utilisateur et autorisations adéquats, vous pouvez créer une base de données de surveillance lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation. > Pour installer et déployer les bases de données sur le serveur SQL Server pour la surveillance, vous devez être membre du groupe SQL Server sysadmins pour le serveur SQL Server sur lequel vous installez les fichiers de base de données. Si vous n’êtes pas membre du groupe SQL Server sysadmin, vous devez demander à être ajouté au groupe jusqu’à ce que les fichiers de base de données soient déployés. Si vous ne pouvez pas être membre du groupe sysadmins, vous devez fournir à votre administrateur de base de données SQL Server le script pour configurer et déployer les bases de données. Pour obtenir des informations sur les droits d’utilisateur et autorisations requis pour réaliser ces procédures, voir [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) dans la documentation de déploiement.