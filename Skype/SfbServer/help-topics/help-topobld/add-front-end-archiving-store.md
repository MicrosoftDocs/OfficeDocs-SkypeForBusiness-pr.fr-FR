---
title: Ajouter le Front-End, l’archivage de banque
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: L’archivage nécessite une édition 64 bits prise en charge du logiciel de base de données Microsoft SQL Server pour stocker les données d’archivage. Vous pouvez sélectionner une base de données SQL Server défini précédemment à utiliser pour l’archivage, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine pleinement qualifié (FQDN) du serveur sur lequel la base de données SQL Server doit se trouver, en plus de l’instance de SQL Se rveur que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: 528c8062b07593a4c7e4cc00f3d1d2566c05f77e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-archiving-store"></a>Ajouter le Front-End, l’archivage de banque
 
L’archivage nécessite une édition 64 bits prise en charge du logiciel de base de données Microsoft SQL Server pour stocker les données d’archivage. Vous pouvez sélectionner une base de données SQL Server défini précédemment à utiliser pour l’archivage, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine pleinement qualifié (FQDN) du serveur sur lequel la base de données SQL Server doit se trouver, en plus de l’instance de SQL Se rveur que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
  
> [!NOTE]
> Si le compte utilisé pour publier la topologie a les autorisations et droits d’utilisateur appropriés, vous pouvez créer la base de données de contrôle lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation. 
  
> [!NOTE]
> Pour installer et déployer des bases de données sur le serveur SQL Server pour l’analyse, vous devez être un membre du groupe sysadmin de SQL Server pour le serveur SQL Server où vous installez les fichiers de base de données. Si vous n’êtes pas un membre du groupe sysadmin de SQL Server, vous devez demander à être ajouté au groupe jusqu'à ce que les fichiers de base de données sont déployées. Si un membre du groupe administrateurs système n’est pas possible, vous devez fournir votre administrateur de base de données SQL Server avec le script à configurer et à déployer les bases de données. Pour plus d’informations sur les droits de l’utilisateur et les autorisations dont vous avez besoin pour accomplir les procédures, consultez [Autorisations de déploiement pour SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) dans la documentation de déploiement.
  

