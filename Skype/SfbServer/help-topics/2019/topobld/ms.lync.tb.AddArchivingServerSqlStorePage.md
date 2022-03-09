---
title: Ajouter un magasin SQL Server du serveur d’archivage
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: Le serveur d’archivage nécessite une édition 64 bits prise en charge du logiciel de base de données SQL Server pour stocker les données d’archivage. Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour l’archivage ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel résidera la base de données SQL Server et l’instance de SQL Server que vous souhaitez utiliser pour la nouvelle SQL Server  (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: 2901e50ea93de36c0cb3e61a0f954c7589f3b4af
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392036"
---
# <a name="add-archiving-server-sql-server-store"></a>Ajouter un magasin SQL Server du serveur d’archivage

Le serveur d’archivage nécessite une édition 64 bits prise en charge du logiciel de base de données SQL Server pour stocker les données d’archivage. Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour l’archivage ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel résidera la base de données SQL Server et l’instance de SQL Server que vous souhaitez utiliser pour la nouvelle SQL Server  (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).

> [!NOTE]
> Si le compte qui est utilisé pour publier la topologie dispose des autorisations et des droits d’utilisateur appropriés, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, dans le cadre de la procédure d’installation ou d’une autre manière.

> [!NOTE]
> Pour installer et déployer les bases de données sur le serveur SQL Server pour l’archivage, vous devez être membre du groupe SQL Server sysadmins pour le serveur SQL Server sur lequel vous installez les fichiers de base de données. Si vous n’êtes pas membre du groupe SQL Server sysadmins, vous devez demander à être ajouté au groupe jusqu’à ce que les fichiers de base de données soient déployés. Si vous ne pouvez pas être membre du groupe sysadmins, vous devez fournir à votre administrateur de base de données SQL Server le script pour configurer et déployer les bases de données. Pour obtenir des informations sur les droits d’utilisateur et autorisations requis pour réaliser les procédures, voir [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) dans la documentation de déploiement.