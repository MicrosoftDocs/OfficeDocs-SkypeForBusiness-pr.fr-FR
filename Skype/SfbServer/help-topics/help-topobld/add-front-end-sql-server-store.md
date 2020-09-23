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
# <a name="add-front-end-sql-server-store"></a>Ajouter un magasin SQL Server frontal

Un déploiement de serveur Standard Edition installe automatiquement le logiciel de base de données Microsoft SQL Server Express et la base de données SQL Server requis. Par conséquent, toutes les options sont préremplies et vous ne pouvez pas modifier la configuration par défaut.

Le pool frontal d’un déploiement de serveur Enterprise Edition requiert une édition 64 bits prise en charge du logiciel de base de données SQL Server pour la base de données principale. Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour la base de données principale, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel la base de données SQL Server doit résider et l’instance de SQL Server que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez). Vous pouvez également choisir d’activer la mise en miroir sur le magasin SQL Server, puis spécifier un témoin de mise en miroir pour le basculement automatique.

Pour plus d’informations sur la prise en charge de SQL Server, voir [Software Database and clustering support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) dans la documentation de prise en charge. Pour plus d'informations sur la configuration SQL Server pour la base de données principale, voir [Configurer SQL Server pour Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) dans la documentation de déploiement.

> [!NOTE]
> Si le compte qui est utilisé pour publier la topologie dispose des droits d’utilisateur et autorisations appropriés, vous pouvez créer la base de données principale de communication en temps réel (RTC, Real-Time Communications) lorsque vous publiez la topologie. Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation.

> [!NOTE]
> Pour installer et déployer les bases de données sur le serveur SQL Server pour un déploiement Enterprise Edition, vous devez être membre du groupe SQL Server sysadmins pour le serveur SQL Server sur lequel vous installez les fichiers de base de données. Si vous n’êtes pas membre du groupe administrateurs SQL Server, vous devez demander à être ajouté au groupe jusqu’à ce que les fichiers de base de données soient déployés. Si vous ne pouvez pas être membre du groupe administrateurs système, vous devez fournir à votre administrateur de base de données SQL Server le script permettant de configurer et de déployer les bases de données. Pour obtenir des informations sur les droits d’utilisateur et autorisations requis pour réaliser les procédures, voir [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).


