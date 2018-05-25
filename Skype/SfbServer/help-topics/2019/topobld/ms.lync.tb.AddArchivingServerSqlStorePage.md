---
title: Ajouter le serveur SQL Server magasin d’archivage
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
description: Serveur d’archivage requiert une édition 64 bits prise en charge du logiciel de base de données SQL Server pour stocker les données d’archive. Vous pouvez sélectionner une base de données SQL Server précédemment défini pour être utilisé pour l’archivage ou de définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel réside la base de données SQL Server et l’instance de SQL Server qui vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: 2c63b6bf71c156bc62e07add023f3049af399095
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="6e6a0-104">Ajouter le serveur SQL Server magasin d’archivage</span><span class="sxs-lookup"><span data-stu-id="6e6a0-104">Add Archiving Server SQL Server Store</span></span>
 
<span data-ttu-id="6e6a0-105">Serveur d’archivage requiert une édition 64 bits prise en charge du logiciel de base de données SQL Server pour stocker les données d’archive.</span><span class="sxs-lookup"><span data-stu-id="6e6a0-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="6e6a0-106">Vous pouvez sélectionner une base de données SQL Server précédemment défini pour être utilisé pour l’archivage ou de définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel réside la base de données SQL Server et l’instance de SQL Server qui vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).</span><span class="sxs-lookup"><span data-stu-id="6e6a0-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6e6a0-107">Si le compte qui est utilisé pour publier la topologie possède les droits d’utilisateur appropriés et les autorisations, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie.</span><span class="sxs-lookup"><span data-stu-id="6e6a0-107">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="6e6a0-108">Vous pouvez également créer la base de données ultérieurement, dans le cadre de la procédure d’installation, ou dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="6e6a0-108">You can also create the database later, as part of the installation procedure, or otherwise.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6e6a0-109">Pour installer et déployer les bases de données sur le serveur SQL Server pour l’archivage, vous devez être membre du groupe administrateurs système SQL Server pour le serveur SQL Server où vous installez les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="6e6a0-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="6e6a0-110">Si vous n’êtes pas un membre du groupe administrateurs système SQL Server, vous devez demander à ajouter au groupe jusqu'à ce que les fichiers de base de données sont déployés.</span><span class="sxs-lookup"><span data-stu-id="6e6a0-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="6e6a0-111">Si vous ne peut pas être établie à un membre du groupe administrateurs système, vous devez fournir votre administrateur de base de données SQL Server avec le script pour configurer et déployer les bases de données.</span><span class="sxs-lookup"><span data-stu-id="6e6a0-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="6e6a0-112">Pour plus d’informations sur les droits d’utilisateur et les autorisations dont vous avez besoin pour effectuer les procédures, voir [Autorisations de déploiement pour SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="6e6a0-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>
  

