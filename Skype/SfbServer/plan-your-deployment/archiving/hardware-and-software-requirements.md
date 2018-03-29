---
title: Configuration logicielle et matérielle requise pour l’archivage dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle pour l’archivage dans Skype pour Business Server 2015.'
ms.openlocfilehash: d8d8039e95a3b578551d0db6ff219fe8f3c1e5c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Configuration logicielle et matérielle requise pour l’archivage dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle pour l’archivage dans Skype pour Business Server 2015.
  
Skype pour Business Server 2015 l’archivage fait désormais partie du rôle de Front-End, vous n’avez pas besoin d’installer un serveur distinct. Vous devez, cependant, avoir à prendre en compte les exigences suivantes :
  
- Conditions d’infrastructure requises
    
- Configuration logicielle requise
    
- Exigences pour le stockage des données
    
## <a name="infrastructure-requirements"></a>Conditions d’infrastructure requises

Skype pour les exigences de l’infrastructure d’archivage de Server Business sont les mêmes que pour déploiement de Skype pour Business Server. Pour plus d’informations, voir [Configuration requise pour votre Skype pour environnement d’entreprise](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
## <a name="prerequisite-software-requirements"></a>Configuration logicielle requise

L’archivage des conditions préalables pour Skype pour Business Server sont plus simples que les versions précédentes de Lync Server raisons suivantes : 
  
- Étant donné que l’archivage n’est plus un rôle de serveur, il est inutile d’installer un serveur distinct pour l’archivage. Au lieu de cela, les agents de collecte de données unifiée sont installés et activés automatiquement sur chaque pool frontal Enterprise Edition et chaque serveur Standard Edition. Vous devrez activer et publier votre topologie d’archivage en utilisant le générateur de topologie.
    
- L’archivage d’utilise le Skype pour le stockage de fichiers de serveur d’entreprise pour le stockage temporaire des fichiers de contenu, à la réunion afin que vous ne définissez pas un magasin de fichier distinct pour l’archivage.
    
- Dans Skype pour Business Server, Microsoft Message Queuing n’est pas nécessaire.
    
## <a name="data-storage-requirements"></a>Exigences pour le stockage des données

Vous devez configurer l’infrastructure d’archivage des données. Cela inclut le choix de l’une des options suivantes :
  
- **Stockage de Microsoft Exchange**. Les fichiers de contenu de réunion, par exemple, les présentations PowerPoint, sont archivés sous forme de pièces jointes. Si vous souhaitez stocker Skype pour archiver les données métiers avec des données de conformité d’Exchange, vous devez utiliser Exchange pour votre déploiement d’Exchange et assurez-vous que la taille maximale de stockage prend en charge le stockage des fichiers de contenu de réunion. Vous devez déployer Exchange avant de déployer et d’activation de l’archivage à l’aide de l’option d’intégration de Microsoft Exchange. 
    
    Si vous choisissez d’utiliser le stockage Exchange, vous n’avez pas besoin déployer des bases de données SQL Server distinctes pour l’archivage, à moins d’avoir Skype pour les utilisateurs professionnels qui ne sont pas hébergées sur vos serveurs Exchange. Si vous déployez l’archivage à l’aide de l’option d’intégration de Microsoft Exchange, Skype pour archiver les données métier est stockée avec les données de conformité d’Exchange uniquement pour les utilisateurs qui sont hébergés sur vos serveurs Exchange. 
    
- **Skype pour le stockage d’archivage du serveur de l’entreprise**. Pour prendre en charge les utilisateurs qui ne sont pas hébergées sur les serveurs Exchange, ou si vous ne souhaitez pas utiliser l’option d’intégration de Microsoft Exchange, vous devez déployer le stockage d’archivage à l’aide d’une base de données SQL Server. Skype pour Business Server prend en charge les versions 64 bits suivantes de SQL Server :
    
  - Microsoft SQL Server 2008 R2 Enterprise
    
  - Microsoft SQL Server 2008 R2 Standard
    
  - Microsoft SQL Server 2012 Enterprise
    
  - Microsoft SQL Server 2012 Standard
    
  - Entreprise 2014 de Microsoft SQL Server
    
  - Microsoft SQL Server 2014 Standard
    
    > [!NOTE]
    > Versions de Microsoft SQL Server Express ne sont pas pris en charge pour l’archivage. versions 32 bits de SQL Server ne sont pas pris en charge. Pour des exigences de SQL Server et des restrictions supplémentaires, voir [Configuration requise pour votre Skype pour environnement d’entreprise](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
    Vous devez paramétrer les plates-formes SQL Server avant de déployer et d’activation de l’archivage. Si le compte à utiliser pour la publication de la topologie est doté des droits et autorisations d’administrateur appropriés, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation. Pour plus d’informations sur SQL Server, voir [SQL Server TechCenter](https://go.microsoft.com/fwlink/p/?linkID=129045).
    
    L’augmentation de la charge pour cause d’archivage peut être importante. Par conséquent, vous devez vous assurer que l’espace disque est suffisant pour les serveurs frontaux sur lesquels l’archivage est activé.
    

