---
title: Ajouter un magasin d’archivage frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: L’archivage nécessite une version 64 bits du logiciel de base de données Microsoft SQL Server compatible pour le stockage des données d’archivage. Vous pouvez sélectionner une base de données SQL Server définie précédemment à utiliser pour l’archivage, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel réside la base de données SQL Server, en plus de l’instance de SQL se. RVER que vous voulez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: 5c55567b134af368296cc628e1e1297df1a8389a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283947"
---
# <a name="add-front-end-archiving-store"></a>Ajouter un magasin d’archivage frontal

L’archivage nécessite une version 64 bits du logiciel de base de données Microsoft SQL Server compatible pour le stockage des données d’archivage. Vous pouvez sélectionner une base de données SQL Server définie précédemment à utiliser pour l’archivage, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel réside la base de données SQL Server, en plus de l’instance de SQL se. RVER que vous voulez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).

> [!NOTE]
> Si le compte utilisé pour publier la topologie possède les autorisations et les droits d’utilisateur appropriés, vous pouvez créer la base de données de surveillance lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation.

> [!NOTE]
> Pour installer et déployer les bases de données sur le serveur SQL Server pour la surveillance, vous devez être membre du groupe SQL Server sysadmins pour le serveur SQL Server sur lequel vous installez les fichiers de base de données. Si vous n’êtes pas membre du groupe SQL Server sysadmin, vous devez demander que vous soyez ajouté au groupe jusqu’à ce que les fichiers de la base de données soient déployés. Si vous ne pouvez pas être membre du groupe sysadmins, vous devez fournir à l’administrateur de la base de données SQL Server le script de configuration et de déploiement de celles-ci. Pour plus d’informations sur les droits d’utilisateur et les autorisations dont vous avez besoin pour accomplir ces procédures, voir [autorisations de déploiement pour SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) dans la documentation de déploiement.


