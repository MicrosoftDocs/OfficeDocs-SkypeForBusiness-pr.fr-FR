---
title: Ajouter un magasin SQL Server du serveur d’archivage
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: Serveur d’archivage requiert une édition 64 bits prise en charge du logiciel de base de données SQL Server pour stocker les données d’archive. Vous pouvez sélectionner une base de données SQL Server précédemment défini pour être utilisé pour l’archivage ou de définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel réside la base de données SQL Server et l’instance de SQL Server qui vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: f16a405551822041ad7d792ac9307e29df19ee45
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889328"
---
# <a name="add-archiving-server-sql-server-store"></a>Ajouter un magasin SQL Server du serveur d’archivage

Serveur d’archivage requiert une édition 64 bits prise en charge du logiciel de base de données SQL Server pour stocker les données d’archive. Vous pouvez sélectionner une base de données SQL Server précédemment défini pour être utilisé pour l’archivage ou de définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel réside la base de données SQL Server et l’instance de SQL Server qui vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).

> [!NOTE]
> Si le compte qui est utilisé pour publier la topologie possède les droits d’utilisateur appropriés et les autorisations, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données ultérieurement, dans le cadre de la procédure d’installation, ou dans le cas contraire.

> [!NOTE]
> Pour installer et déployer les bases de données sur le serveur SQL Server pour l’archivage, vous devez être membre du groupe administrateurs système SQL Server pour le serveur SQL Server où vous installez les fichiers de base de données. Si vous n’êtes pas un membre du groupe administrateurs système SQL Server, vous devez demander à ajouter au groupe jusqu'à ce que les fichiers de base de données sont déployés. Si vous ne peut pas être établie à un membre du groupe administrateurs système, vous devez fournir votre administrateur de base de données SQL Server avec le script pour configurer et déployer les bases de données. Pour plus d’informations sur les droits d’utilisateur et les autorisations dont vous avez besoin pour effectuer les procédures, voir [Autorisations de déploiement pour SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) dans la documentation de déploiement.


