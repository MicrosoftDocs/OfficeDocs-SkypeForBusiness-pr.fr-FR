---
title: Ajouter le magasin d’archivage frontal
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
description: L’archivage nécessite une édition 64 bits prise en charge du logiciel de base de données Microsoft SQL Server pour stocker les données d’archivage. Vous pouvez sélectionner une base de données SQL Server précédemment défini à utiliser pour l’archivage, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel la base de données SQL Server réside, en plus de l’instance de SQL Se rveur que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).
ms.openlocfilehash: be924cb8ff418e75f50dbaceaa875397f498ba8d
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23243445"
---
# <a name="add-front-end-archiving-store"></a>Ajouter le magasin d’archivage frontal

L’archivage nécessite une édition 64 bits prise en charge du logiciel de base de données Microsoft SQL Server pour stocker les données d’archivage. Vous pouvez sélectionner une base de données SQL Server précédemment défini à utiliser pour l’archivage, ou définir une nouvelle base de données SQL Server en spécifiant un nom de domaine complet (FQDN) du serveur sur lequel la base de données SQL Server réside, en plus de l’instance de SQL Se rveur que vous souhaitez utiliser pour la nouvelle base de données SQL Server (qui peut être l’instance par défaut ou une instance nommée que vous spécifiez).

> [!NOTE]
> Si le compte utilisé pour publier la topologie possède les droits d’utilisateur appropriés et les autorisations, vous pouvez créer la base de données de surveillance lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation.

> [!NOTE]
> Pour installer et déployer les bases de données sur le serveur SQL Server pour la surveillance, vous devez être membre du groupe administrateurs système SQL Server pour le serveur SQL Server où vous installez les fichiers de base de données. Si vous n’êtes pas un membre du groupe sysadmin de SQL Server, vous devez demander d’être ajouté au groupe jusqu'à ce que les fichiers de base de données sont déployés. Si vous ne peut pas être établie à un membre du groupe administrateurs système, vous devez fournir votre administrateur de base de données SQL Server avec le script pour configurer et déployer les bases de données. Pour plus d’informations sur les droits d’utilisateur et les autorisations dont vous avez besoin pour effectuer les procédures, voir [Autorisations de déploiement pour SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) dans la documentation de déploiement.


