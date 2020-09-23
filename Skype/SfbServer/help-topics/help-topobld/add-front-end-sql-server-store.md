---
title: Ajouter un magasin SQL Server frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Un déploiement de serveur Standard Edition installe automatiquement le logiciel de base de données Microsoft SQL Server Express et la base de données SQL Server requis. Par conséquent, toutes les options sont préremplies et vous ne pouvez pas modifier la configuration par défaut.
ms.openlocfilehash: 614c3a852bb52a73c8a3f71ee467a2d71f82e9b6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216495"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="7e1d7-104">Ajouter un magasin SQL Server frontal</span><span class="sxs-lookup"><span data-stu-id="7e1d7-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="7e1d7-105">Un déploiement de serveur Standard Edition installe automatiquement le logiciel de base de données Microsoft SQL Server Express et la base de données SQL Server requis.</span><span class="sxs-lookup"><span data-stu-id="7e1d7-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="7e1d7-106">Par conséquent, toutes les options sont préremplies et vous ne pouvez pas modifier la configuration par défaut.</span><span class="sxs-lookup"><span data-stu-id="7e1d7-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="7e1d7-107">Le pool frontal d’un déploiement de serveur Enterprise Edition requiert une édition 64 bits prise en charge du logiciel de base de données SQL Server pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="7e1d7-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="7e1d7-108">Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour la base de données principale, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel la base de données SQL Server doit résider et l’instance de SQL Server que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).</span><span class="sxs-lookup"><span data-stu-id="7e1d7-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="7e1d7-109">Vous pouvez également choisir d’activer la mise en miroir sur le magasin SQL Server, puis spécifier un témoin de mise en miroir pour le basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="7e1d7-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="7e1d7-110">Pour plus d’informations sur la prise en charge de SQL Server, voir [Software Database and clustering support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="7e1d7-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="7e1d7-111">Pour plus d'informations sur la configuration SQL Server pour la base de données principale, voir [Configurer SQL Server pour Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="7e1d7-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server for Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="7e1d7-p105">Si le compte qui est utilisé pour publier la topologie dispose des droits d’utilisateur et autorisations appropriés, vous pouvez créer la base de données principale de communication en temps réel (RTC, Real-Time Communications) lorsque vous publiez la topologie. Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation.</span><span class="sxs-lookup"><span data-stu-id="7e1d7-p105">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology. You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="7e1d7-114">Pour installer et déployer les bases de données sur le serveur SQL Server pour un déploiement Enterprise Edition, vous devez être membre du groupe SQL Server sysadmins pour le serveur SQL Server sur lequel vous installez les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="7e1d7-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="7e1d7-115">Si vous n’êtes pas membre du groupe administrateurs SQL Server, vous devez demander à être ajouté au groupe jusqu’à ce que les fichiers de base de données soient déployés.</span><span class="sxs-lookup"><span data-stu-id="7e1d7-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="7e1d7-116">Si vous ne pouvez pas être membre du groupe administrateurs système, vous devez fournir à votre administrateur de base de données SQL Server le script permettant de configurer et de déployer les bases de données.</span><span class="sxs-lookup"><span data-stu-id="7e1d7-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="7e1d7-117">Pour obtenir des informations sur les droits d’utilisateur et autorisations requis pour réaliser les procédures, voir [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span><span class="sxs-lookup"><span data-stu-id="7e1d7-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


