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
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Le déploiement d’un serveur Standard Edition Server installe automatiquement le logiciel de base de données Microsoft SQL Server Express et la base de données SQL Server requis. Par conséquent, toutes les options sont préremplies et vous ne pouvez pas apporter de modifications à la configuration par défaut.
ms.openlocfilehash: b2f3aef2b48981368a74d536254da55ae5e0495d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685137"
---
# <a name="add-front-end-sql-server-store"></a>Ajouter un magasin SQL Server frontal

Le déploiement d’un serveur Standard Edition Server installe automatiquement le logiciel de base de données Microsoft SQL Server Express et la base de données SQL Server requis. Par conséquent, toutes les options sont préremplies et vous ne pouvez pas apporter de modifications à la configuration par défaut.

Le pool frontal d’un déploiement de serveur Enterprise Edition nécessite une version 64 bits du logiciel de base de données SQL Server pour la base de données principale. Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour la base de données principale, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel réside la base de données SQL Server et l’instance de SQL S. serveur de noms que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez). Vous pouvez également choisir d’activer la mise en miroir sur SQL Server Store et spécifier un témoin de mise en miroir pour le basculement automatique.

Pour plus d’informations sur la prise en charge de SQL Server, voir [logiciels de base de données et prise en charge](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) de la mise en cluster dans la documentation de support. Pour plus d’informations sur la configuration de SQL Server pour la base de données principale, voir [configurer SQL Server pour Lync server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) dans la documentation de déploiement.

> [!NOTE]
> Si le compte qui est utilisé pour publier la topologie possède les autorisations et les droits d’utilisateur appropriés, vous pouvez créer la base de données principale (RTC) lors de la publication de votre topologie. Vous pouvez également créer la base de données ultérieurement, y compris dans le cadre de la procédure d’installation.

> [!NOTE]
> Pour installer et déployer les bases de données sur le serveur SQL Server pour le déploiement d’Enterprise Edition, vous devez être membre du groupe SQL Server sysadmins pour le serveur SQL Server sur lequel vous installez les fichiers de base de données. Si vous n’êtes pas membre du groupe SQL Server sysadmins, vous devez demander à être ajouté au groupe tant que les fichiers de la base de données ne sont pas déployés. Si vous ne pouvez pas être membre du groupe sysadmins, vous devez fournir à l’administrateur de la base de données SQL Server le script de configuration et de déploiement de celles-ci. Pour plus d’informations sur les droits d’utilisateur et les autorisations dont vous avez besoin pour accomplir ces procédures, voir [autorisations de déploiement pour SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).


