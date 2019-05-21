---
title: Ajouter un magasin SQL Server du serveur de surveillance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
ROBOTS: NOINDEX, NOFOLLOW
description: La surveillance du serveur nécessite une version 64 bits du logiciel de base de données SQL Server compatible pour le stockage des données de surveillance. Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour la surveillance ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel réside la base de données SQL Server, en plus de l’instance de SQL Serveur que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: 406c1da490506ec3cc762deb388162534084451a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306180"
---
# <a name="add-monitoring-server-sql-server-store"></a>Ajouter un magasin SQL Server du serveur de surveillance

La surveillance du serveur nécessite une version 64 bits du logiciel de base de données SQL Server compatible pour le stockage des données de surveillance. Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour la surveillance ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel réside la base de données SQL Server, en plus de l’instance de SQL Serveur que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).

Pour plus d’informations sur la prise en charge de SQL Server, voir [logiciels de base de données et prise en charge](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) de la mise en cluster dans la documentation de support. Pour plus d’informations sur la base de données de surveillance, y compris la colocalisation de la base de données de surveillance, voir [emplacement du serveur pris en charge](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) dans la documentation de prise en charge,[planification de l’analyse](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) dans la documentation de planification et les [données SQL Server Emplacement du fichier journal](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) dans la documentation de déploiement.

> [!NOTE]
> Si le compte utilisé pour publier la topologie possède les autorisations et les droits d’utilisateur appropriés, vous pouvez créer la base de données de surveillance lorsque vous publiez votre topologie. Vous pouvez également créer la base de données ultérieurement, y compris dans le cadre de la procédure d’installation. >, XXX XX XXX XX XXX XX XXX XX XXX XX XXX XX XXX XX XXX XX XXX XX XXX XX XXX XX XXX XX XXX XX XXX XX XXX XX XXX XX XXX XX XXX XXX Si vous n’êtes pas membre du groupe SQL Server sysadmin, vous devez demander à être ajouté au groupe tant que les fichiers de base de données ne sont pas déployés. Si vous ne pouvez pas être membre du groupe sysadmins, vous devez fournir à l’administrateur de la base de données SQL Server le script de configuration et de déploiement de celles-ci. Pour plus d’informations sur les droits d’utilisateur et les autorisations dont vous avez besoin pour accomplir ces procédures, voir [autorisations de déploiement pour SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) dans la documentation de déploiement.


