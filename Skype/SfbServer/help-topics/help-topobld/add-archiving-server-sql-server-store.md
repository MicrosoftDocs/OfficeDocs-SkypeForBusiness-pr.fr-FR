---
title: Ajouter un magasin SQL Server du serveur d’archivage
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: Le serveur d’archivage nécessite une édition 64 bits prise en charge du logiciel SQL Server base de données pour stocker les données d’archivage. Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour l’archivage ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel résidera la base de données SQL Server et l’instance de SQL Server que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: 813b6f75db61153c704d2300341cac28bd16cc3c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119833"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="df9b3-104">Ajouter un magasin SQL Server du serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="df9b3-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="df9b3-105">Le serveur d’archivage nécessite une édition 64 bits prise en charge du logiciel SQL Server base de données pour stocker les données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="df9b3-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="df9b3-106">Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour l’archivage ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel résidera la base de données SQL Server et l’instance de SQL Server que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).</span><span class="sxs-lookup"><span data-stu-id="df9b3-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="df9b3-p103">Si le compte qui est utilisé pour publier la topologie dispose des autorisations et des droits d’utilisateur appropriés, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, dans le cadre de la procédure d’installation ou d’une autre manière.</span><span class="sxs-lookup"><span data-stu-id="df9b3-p103">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology. You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="df9b3-109">Pour installer et déployer les bases de données sur le serveur SQL Server pour l’archivage, vous devez être membre du groupe SQL Server sysadmins pour le serveur SQL Server sur lequel vous installez les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="df9b3-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="df9b3-110">Si vous n’êtes pas membre du groupe SQL Server sysadmins, vous devez demander à être ajouté au groupe jusqu’à ce que les fichiers de base de données soient déployés.</span><span class="sxs-lookup"><span data-stu-id="df9b3-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="df9b3-111">Si vous ne pouvez pas être membre du groupe sysadmins, vous devez fournir à votre administrateur de base de données SQL Server le script pour configurer et déployer les bases de données.</span><span class="sxs-lookup"><span data-stu-id="df9b3-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="df9b3-112">Pour obtenir des informations sur les droits d’utilisateur et autorisations requis pour réaliser les procédures, voir [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="df9b3-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in the Deployment documentation.</span></span>