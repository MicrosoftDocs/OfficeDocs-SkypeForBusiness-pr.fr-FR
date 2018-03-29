---
title: Créer des bases de données
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: Générateur de topologies permet d’installer les bases de données sur un magasin de SQL Server. Lorsque vous installez les bases de données à l’aide du Générateur de topologies, l’application lit les informations de la topologie et puis installe les bases de données requises sur l’ou les clusters de SQL Server de SQL Server spécifié. C’est le seul type d’installation de base de données disponible par le biais du générateur de topologie. Si vous devez installer une base de données spécifique sur un ordinateur spécifique, ou si vous devez installer une base de données concurrentes, vous devez plutôt utiliser interface de ligne de commande de Windows PowerShell et l’applet de commande Install-CsDatabase.
ms.openlocfilehash: 9bee333e0b56a6eeb8f4363e6657be2fabfa1ace
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-database"></a>Créer des bases de données
 
Générateur de topologies permet d’installer les bases de données sur un magasin de SQL Server. Lorsque vous installez les bases de données à l’aide du Générateur de topologies, l’application lit les informations de la topologie et puis installe les bases de données requises sur l’ou les clusters de SQL Server de SQL Server spécifié. C’est le seul type d’installation de base de données disponible par le biais du générateur de topologie. Si vous devez installer une base de données spécifique sur un ordinateur spécifique, ou si vous devez installer une base de données concurrentes, vous devez plutôt utiliser interface de ligne de commande de Windows PowerShell et l’applet de commande [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) .
  
### <a name="creating-a-database"></a>Création d’une base de données

1. Cliquez sur le Skype pour Business Server 2015 nœud puis **Installer la base de données**.
    
2. Dans la boîte de dialogue **Installer les bases de données** , dans la page **Créer une base de données** , sélectionnez le nom de domaine pleinement qualifié (FQDN) de la banque d’informations de SQL Server où les nouvelles bases de données doivent être créés.
    
3. Cliquez sur **Avancé**. Dans la boîte de dialogue **Sélectionner un emplacement de fichier de base de données**, sélectionnez l’une des options suivantes :
    
  - **Déterminer automatiquement l’emplacement du fichier de base de données** : si vous sélectionnez cette option, le générateur de topologie utilise un algorithme intégré pour sélectionner l’emplacement de stockage des journaux de bases de données et des fichiers de données.
    
  - **Utilisez SQL Server, instance par défaut**. Si vous sélectionnez cette option, l’algorithme intégré n’est pas utilisé pour choisir les emplacements de stockage pour les fichiers de données et journaux de la base de données. Au lieu de cela, les fichiers journaux et de données sont stockés dans les emplacements spécifiés par le chemin d’accès par défaut de SQL Server (ces chemins d’accès doivent être configurés dans avancée par un administrateur de SQL Server). Les fichiers de données seront stockées dans l’emplacement par défaut du fichier de données de SQL Server alors que les fichiers journaux seront stockés dans l’emplacement du fichier journal par défaut de SQL Server.
    
4. Cliquez sur **OK**.
    
5. Dans la page **Créer des bases de données**, cliquez sur **Suivant**.
    
6. Dans la page **Création de bases de données terminée**, cliquez sur **Terminer**.
    

