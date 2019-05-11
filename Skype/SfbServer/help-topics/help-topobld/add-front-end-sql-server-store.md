---
title: Ajouter un magasin SQL Server frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Un déploiement du serveur Standard Edition installe automatiquement le logiciel de base de données Microsoft SQL Server Express requis et la base de données SQL Server. Par conséquent, toutes les options sont préremplies, et vous ne pouvez pas modifier la configuration par défaut.
ms.openlocfilehash: 4c55f70cae6957acac28854c226b3699e860eea3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903788"
---
# <a name="add-front-end-sql-server-store"></a>Ajouter un magasin SQL Server frontal

Un déploiement du serveur Standard Edition installe automatiquement le logiciel de base de données Microsoft SQL Server Express requis et la base de données SQL Server. Par conséquent, toutes les options sont préremplies, et vous ne pouvez pas modifier la configuration par défaut.

Le pool frontal d’un déploiement de serveur Enterprise Edition nécessite une édition 64 bits prise en charge du logiciel de base de données SQL Server pour la base de données principale. Vous pouvez sélectionner une base de données SQL Server précédemment défini à utiliser pour la base de données principale, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel la base de données SQL Server doit résider et l’instance de SQL S serveur que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez). Vous pouvez également choisir d’activer la mise en miroir sur le magasin SQL Server et spécifier un témoin de mise en miroir pour le basculement automatique.

Pour plus d’informations sur SQL Server prennent en charge, voir le [logiciel de base de données et le clustering avec prise en charge](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) dans la documentation de prise en charge. Pour plus d’informations sur la configuration de SQL Server pour la base de données principale, consultez [Configurer SQL Server pour Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) dans la documentation de déploiement.

> [!NOTE]
> Si le compte qui est utilisé pour publier la topologie possède les droits d’utilisateur appropriés et les autorisations, vous pouvez créer la base de données principale (communications en temps réel (RTC)) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données ultérieurement, y compris dans le cadre de la procédure d’installation.

> [!NOTE]
> Pour installer et déployer les bases de données sur le serveur SQL Server pour un déploiement Enterprise Edition, vous devez être membre du groupe administrateurs système SQL Server pour le serveur SQL Server où vous installez les fichiers de base de données. Si vous n’êtes pas un membre du groupe administrateurs système SQL Server, vous devez demander à ajouter au groupe jusqu'à ce que les fichiers de base de données sont déployés. Si vous ne peut pas être établie à un membre du groupe administrateurs système, vous devez fournir votre administrateur de base de données SQL Server avec le script pour configurer et déployer les bases de données. Pour plus d’informations sur les droits d’utilisateur et les autorisations dont vous avez besoin pour effectuer les procédures, voir [Autorisations de déploiement pour SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).


