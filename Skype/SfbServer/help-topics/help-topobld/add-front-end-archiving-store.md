---
title: Ajouter un magasin d’archivage frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: L’archivage nécessite une version 64 bits du logiciel de base de données Microsoft SQL Server compatible pour le stockage des données d’archivage. Vous pouvez sélectionner une base de données SQL Server définie précédemment à utiliser pour l’archivage, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel réside la base de données SQL Server, en plus de l’instance de SQL se. RVER que vous voulez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: e315e27ddb96d018ca0bead13564ad88e944cd34
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820926"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="7f4e1-104">Ajouter un magasin d’archivage frontal</span><span class="sxs-lookup"><span data-stu-id="7f4e1-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="7f4e1-105">L’archivage nécessite une version 64 bits du logiciel de base de données Microsoft SQL Server compatible pour le stockage des données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="7f4e1-106">Vous pouvez sélectionner une base de données SQL Server définie précédemment à utiliser pour l’archivage, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel réside la base de données SQL Server, en plus de l’instance de SQL se. RVER que vous voulez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).</span><span class="sxs-lookup"><span data-stu-id="7f4e1-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="7f4e1-107">Si le compte utilisé pour publier la topologie possède les autorisations et les droits d’utilisateur appropriés, vous pouvez créer la base de données de surveillance lorsque vous publiez votre topologie.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="7f4e1-108">Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="7f4e1-109">Pour installer et déployer les bases de données sur le serveur SQL Server pour la surveillance, vous devez être membre du groupe SQL Server sysadmins pour le serveur SQL Server sur lequel vous installez les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="7f4e1-110">Si vous n’êtes pas membre du groupe SQL Server sysadmin, vous devez demander que vous soyez ajouté au groupe jusqu’à ce que les fichiers de la base de données soient déployés.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="7f4e1-111">Si vous ne pouvez pas être membre du groupe sysadmins, vous devez fournir à l’administrateur de la base de données SQL Server le script de configuration et de déploiement de celles-ci.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="7f4e1-112">Pour plus d’informations sur les droits d’utilisateur et les autorisations dont vous avez besoin pour accomplir ces procédures, voir [autorisations de déploiement pour SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


