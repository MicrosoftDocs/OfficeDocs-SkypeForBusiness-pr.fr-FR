---
title: Ajouter le Front-End, l’archivage de banque
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: L’archivage nécessite une édition 64 bits prise en charge du logiciel de base de données Microsoft SQL Server pour stocker les données d’archivage. Vous pouvez sélectionner une base de données SQL Server défini précédemment à utiliser pour l’archivage, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine pleinement qualifié (FQDN) du serveur sur lequel la base de données SQL Server doit se trouver, en plus de l’instance de SQL Se rveur que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: 528c8062b07593a4c7e4cc00f3d1d2566c05f77e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="d223d-104">Ajouter le Front-End, l’archivage de banque</span><span class="sxs-lookup"><span data-stu-id="d223d-104">Add Front End Archiving Store</span></span>
 
<span data-ttu-id="d223d-105">L’archivage nécessite une édition 64 bits prise en charge du logiciel de base de données Microsoft SQL Server pour stocker les données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="d223d-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="d223d-106">Vous pouvez sélectionner une base de données SQL Server défini précédemment à utiliser pour l’archivage, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine pleinement qualifié (FQDN) du serveur sur lequel la base de données SQL Server doit se trouver, en plus de l’instance de SQL Se rveur que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).</span><span class="sxs-lookup"><span data-stu-id="d223d-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d223d-107">Si le compte utilisé pour publier la topologie a les autorisations et droits d’utilisateur appropriés, vous pouvez créer la base de données de contrôle lorsque vous publiez votre topologie.</span><span class="sxs-lookup"><span data-stu-id="d223d-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="d223d-108">Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation.</span><span class="sxs-lookup"><span data-stu-id="d223d-108">You can also create the database later, included as part of the installation procedure.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d223d-109">Pour installer et déployer des bases de données sur le serveur SQL Server pour l’analyse, vous devez être un membre du groupe sysadmin de SQL Server pour le serveur SQL Server où vous installez les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="d223d-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="d223d-110">Si vous n’êtes pas un membre du groupe sysadmin de SQL Server, vous devez demander à être ajouté au groupe jusqu'à ce que les fichiers de base de données sont déployées.</span><span class="sxs-lookup"><span data-stu-id="d223d-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="d223d-111">Si un membre du groupe administrateurs système n’est pas possible, vous devez fournir votre administrateur de base de données SQL Server avec le script à configurer et à déployer les bases de données.</span><span class="sxs-lookup"><span data-stu-id="d223d-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="d223d-112">Pour plus d’informations sur les droits de l’utilisateur et les autorisations dont vous avez besoin pour accomplir les procédures, consultez [Autorisations de déploiement pour SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d223d-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>
  

