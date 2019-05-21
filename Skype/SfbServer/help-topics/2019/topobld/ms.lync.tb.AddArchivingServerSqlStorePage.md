---
title: Ajouter un magasin SQL Server du serveur d’archivage
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: Le serveur d’archivage nécessite une version 64 bits du logiciel de base de données SQL Server compatible pour le stockage des données d’archivage. Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour l’archivage ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel réside la base de données SQL Server et l’instance de SQL Server qui vous voulez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: 9d9d5af7e769a22c7742029d786826e3d2b3c998
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304099"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="12d35-104">Ajouter un magasin SQL Server du serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="12d35-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="12d35-105">Le serveur d’archivage nécessite une version 64 bits du logiciel de base de données SQL Server compatible pour le stockage des données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="12d35-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="12d35-106">Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour l’archivage ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel réside la base de données SQL Server et l’instance de SQL Server qui vous voulez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).</span><span class="sxs-lookup"><span data-stu-id="12d35-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="12d35-107">Si le compte qui est utilisé pour publier la topologie possède les autorisations et les droits d’utilisateur appropriés, vous pouvez créer la base de données d’archivage (LcsLog) lors de la publication de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="12d35-107">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="12d35-108">Vous pouvez également créer la base de données plus tard dans le cadre de la procédure d’installation, sinon.</span><span class="sxs-lookup"><span data-stu-id="12d35-108">You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="12d35-109">Pour installer et déployer les bases de données sur le serveur SQL Server pour l’archivage, vous devez être membre du groupe SQL Server sysadmins pour le serveur SQL Server sur lequel vous installez les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="12d35-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="12d35-110">Si vous n’êtes pas membre du groupe SQL Server sysadmins, vous devez demander à être ajouté au groupe tant que les fichiers de la base de données ne sont pas déployés.</span><span class="sxs-lookup"><span data-stu-id="12d35-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="12d35-111">Si vous ne pouvez pas être membre du groupe sysadmins, vous devez fournir à l’administrateur de la base de données SQL Server le script de configuration et de déploiement de celles-ci.</span><span class="sxs-lookup"><span data-stu-id="12d35-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="12d35-112">Pour plus d’informations sur les droits d’utilisateur et les autorisations dont vous avez besoin pour accomplir ces procédures, voir [autorisations de déploiement pour SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="12d35-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


