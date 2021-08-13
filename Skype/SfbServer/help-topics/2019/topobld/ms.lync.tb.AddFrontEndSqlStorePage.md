---
title: Ajouter un magasin SQL Server frontal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Un déploiement Édition Standard serveur de gestion installe automatiquement les logiciels Microsoft SQL Server Express base de données SQL Server base de données. Par conséquent, toutes les options sont prérupuplées et vous ne pouvez pas apporter de modifications à la configuration par défaut.
ms.openlocfilehash: 79391900b3379836460935dfc8c0402a2914ec0d80fc398b1483dad93bdb72d2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323466"
---
# <a name="add-front-end-sql-server-store"></a>Ajouter un magasin SQL Server frontal

Un déploiement Édition Standard serveur de gestion installe automatiquement les logiciels Microsoft SQL Server Express base de données SQL Server base de données. Par conséquent, toutes les options sont prérupuplées et vous ne pouvez pas apporter de modifications à la configuration par défaut.

Le pool frontal d’un déploiement de serveur Êdition Entreprise nécessite une édition 64 bits prise en charge du logiciel de base de données SQL Server pour la base de données principale. Vous pouvez sélectionner une base de données SQL Server précédemment définie à utiliser pour la base de données principale ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel la base de données SQL Server doit résider et l’instance de SQL Server que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez). Vous pouvez également choisir d’activer la mise en miroir sur le magasin SQL Server, puis spécifier un témoin de mise en miroir pour le basculement automatique.

Pour plus d’informations sur SQL Server prise en charge, voir La prise en charge des logiciels de base de données et du [clustering](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) dans la documentation de prise en charge. Pour plus d’informations sur la configuration SQL Server la base de données principale, voir [Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server) in the Deployment documentation.

> [!NOTE]
> Si le compte qui est utilisé pour publier la topologie dispose des droits d’utilisateur et autorisations appropriés, vous pouvez créer la base de données principale de communication en temps réel (RTC, Real-Time Communications) lorsque vous publiez la topologie. Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation.

> [!NOTE]
> Pour installer et déployer les bases de données sur le serveur SQL Server pour un déploiement Êdition Entreprise, vous devez être membre du groupe SQL Server sysadmins pour le serveur SQL Server sur lequel vous installez les fichiers de base de données. Si vous n’êtes pas membre du groupe SQL Server sysadmins, vous devez demander à être ajouté au groupe jusqu’à ce que les fichiers de base de données soient déployés. Si vous ne pouvez pas être membre du groupe sysadmins, vous devez fournir à votre administrateur de base de données SQL Server le script pour configurer et déployer les bases de données. Pour obtenir des informations sur les droits d’utilisateur et autorisations requis pour réaliser les procédures, voir [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server).