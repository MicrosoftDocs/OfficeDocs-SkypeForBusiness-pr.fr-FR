---
title: Ajouter un magasin SQL Server du serveur de surveillance
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
ROBOTS: NOINDEX, NOFOLLOW
description: Le serveur de surveillance nécessite une édition 64 bits prise en charge SQL Server base de données pour stocker les données de surveillance. Vous pouvez soit sélectionner une base de données SQL Server précédemment définie à utiliser pour la surveillance, soit définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel résidera la base de données SQL Server, en plus de l’instance de SQL Server que vous souhaitez utiliser pour la nouvelle base de données SQL Server base de données (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: ca7f2e407bf367a7ff544d08105e6af533454ba2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395956"
---
# <a name="add-monitoring-server-sql-server-store"></a>Ajouter un magasin SQL Server du serveur de surveillance

Le serveur de surveillance nécessite une édition 64 bits prise en charge SQL Server base de données pour stocker les données de surveillance. Vous pouvez soit sélectionner une base de données SQL Server précédemment définie à utiliser pour la surveillance, soit définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel résidera la base de données SQL Server, en plus de l’instance de SQL Server que vous souhaitez utiliser pour la nouvelle base de données SQL Server base de données (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).

Pour plus d’informations sur SQL Server prise en charge, voir La prise en charge des logiciels de base de données et du [clustering](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) dans la documentation de prise en charge. Pour plus d’informations sur la base de données de surveillance, y compris la cocation de la base de données de surveillance, voir [Supported Server Location](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation,Planning [for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in the Planning documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.

> [!NOTE]
> Si le compte utilisé pour publier la topologie dispose des droits d’utilisateur et autorisations adéquats, vous pouvez créer une base de données de surveillance lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation. > Pour installer et déployer les bases de données sur le serveur SQL Server pour la surveillance, vous devez être membre du groupe SQL Server sysadmins pour le serveur SQL Server sur lequel vous installez les fichiers de base de données. Si vous n’êtes pas membre du groupe SQL Server sysadmin, vous devez demander à être ajouté au groupe jusqu’à ce que les fichiers de base de données soient déployés. Si vous ne pouvez pas être membre du groupe sysadmins, vous devez fournir à votre administrateur de base de données SQL Server le script pour configurer et déployer les bases de données. Pour obtenir des informations sur les droits d’utilisateur et autorisations requis pour réaliser ces procédures, voir [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) dans la documentation de déploiement.