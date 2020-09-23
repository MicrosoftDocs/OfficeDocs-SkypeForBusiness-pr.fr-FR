---
title: Ajouter un magasin SQL Server du serveur de surveillance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: Le serveur de surveillance nécessite une édition 64 bits prise en charge du logiciel de base de données SQL Server pour stocker les données de surveillance. Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour la surveillance ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel la base de données SQL Server doit résider, ainsi que l’instance de SQL Server que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: adeb5385b385345163d7dc99b0a652837ab8bca4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217895"
---
# <a name="add-monitoring-server-sql-server-store"></a>Ajouter un magasin SQL Server du serveur de surveillance

Le serveur de surveillance nécessite une édition 64 bits prise en charge du logiciel de base de données SQL Server pour stocker les données de surveillance. Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour la surveillance ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel la base de données SQL Server doit résider, ainsi que l’instance de SQL Server que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).

Pour plus d’informations sur la prise en charge de SQL Server, voir [Software Database and clustering support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) dans la documentation de prise en charge. Pour plus d’informations sur la base de données de surveillance, notamment la colocalisation de la base de données de surveillance, voir l' [emplacement du serveur pris en charge](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) dans la documentation de prise en charge,[planification de la surveillance](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) dans la documentation de planification et l’emplacement des fichiers journaux et des [données SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) dans la documentation de déploiement

> [!NOTE]
> Si le compte utilisé pour publier la topologie dispose des droits d’utilisateur et autorisations adéquats, vous pouvez créer une base de données de surveillance lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation. > pour installer et déployer les bases de données sur le serveur SQL Server à des fins de surveillance, vous devez être membre du groupe SQL Server sysadmins pour le serveur SQL Server sur lequel vous installez les fichiers de base de données. Si vous n’êtes pas membre du groupe sysadmin SQL Server, vous devez demander à être ajouté au groupe jusqu’à ce que les fichiers de base de données soient déployés. Si vous ne pouvez pas être membre du groupe administrateurs système, vous devez fournir à votre administrateur de base de données SQL Server le script permettant de configurer et de déployer les bases de données. Pour obtenir des informations sur les droits d’utilisateur et autorisations requis pour réaliser ces procédures, voir [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) dans la documentation de déploiement.


