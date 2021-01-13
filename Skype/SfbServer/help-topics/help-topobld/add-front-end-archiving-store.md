---
title: Ajouter un magasin d’archivage frontal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: L’archivage nécessite une édition 64 bits prise en charge du logiciel de base de données Microsoft SQL Server pour stocker les données d’archivage. Vous pouvez soit sélectionner une base de données SQL Server précédemment définie à utiliser pour l’archivage, soit définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel la base de données SQL Server doit résider, en plus de l’instance de SQL Server que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut). ou une instance nommée que vous spécifiez).
ms.openlocfilehash: 9e094bacca87e6b70a7caa1db9c43a5c98c0edbd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824214"
---
# <a name="add-front-end-archiving-store"></a>Ajouter un magasin d’archivage frontal

L’archivage nécessite une édition 64 bits prise en charge du logiciel de base de données Microsoft SQL Server pour stocker les données d’archivage. Vous pouvez soit sélectionner une base de données SQL Server précédemment définie à utiliser pour l’archivage, soit définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel la base de données SQL Server doit résider, en plus de l’instance de SQL Server que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut). ou une instance nommée que vous spécifiez).

> [!NOTE]
> Si le compte utilisé pour publier la topologie dispose des droits d’utilisateur et autorisations adéquats, vous pouvez créer une base de données de surveillance lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, lors de la procédure d’installation.

> [!NOTE]
> Pour installer et déployer les bases de données sur le serveur SQL Server pour la surveillance, vous devez être membre du groupe SQL Server sysadmins pour le serveur SQL Server sur lequel vous installez les fichiers de base de données. Si vous n’êtes pas membre du groupe SQL Server sysadmin, vous devez demander à être ajouté au groupe jusqu’à ce que les fichiers de base de données soient déployés. Si vous ne pouvez pas être membre du groupe sysadmins, vous devez fournir à votre administrateur de base de données SQL Server le script pour configurer et déployer les bases de données. Pour obtenir des informations sur les droits d’utilisateur et autorisations requis pour réaliser les procédures, voir [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) dans la documentation de déploiement.


