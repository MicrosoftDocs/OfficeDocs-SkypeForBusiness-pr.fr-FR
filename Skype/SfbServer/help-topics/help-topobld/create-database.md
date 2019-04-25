---
title: Créer des bases de données
ms.reviewer: ''
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
description: Générateur de topologies permet d’installer les bases de données sur un magasin SQL Server. Lorsque vous installez les bases de données à l’aide du Générateur de topologie, l’application lit les informations de la topologie de, puis installe les bases de données requises sur l’ordinateur SQL Server spécifié ou d’un cluster SQL Server. C’est le seul type d’installation de base de données disponible par le biais du générateur de topologie. Si vous avez besoin installer une base de données spécifique sur un ordinateur spécifique, ou si vous devez installer une base de données colocalisée, vous devez utiliser à la place interface de ligne de commande Windows PowerShell et l’applet de commande Install-CsDatabase.
ms.openlocfilehash: 9b9d3e3678fe0015281a75aa04b2a2a88daf5d2f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226970"
---
# <a name="create-database"></a>Créer des bases de données
 
Générateur de topologies permet d’installer les bases de données sur un magasin SQL Server. Lorsque vous installez les bases de données à l’aide du Générateur de topologie, l’application lit les informations de la topologie de, puis installe les bases de données requises sur l’ordinateur SQL Server spécifié ou d’un cluster SQL Server. C’est le seul type d’installation de base de données disponible par le biais du générateur de topologie. Si vous avez besoin installer une base de données spécifique sur un ordinateur spécifique, ou si vous devez installer une base de données colocalisée, vous devez utiliser à la place interface de ligne de commande Windows PowerShell et l’applet de commande [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) .
  
### <a name="creating-a-database"></a>Création d’une base de données

1. Cliquez sur le Skype Business Server 2015 nœud, puis cliquez sur **Installer une base de données**.
    
2. Dans la boîte de dialogue **Installer les bases de données** , dans la page **Créer une base de données** , sélectionnez le nom de domaine complet (FQDN) du magasin SQL Server où les nouvelles bases de données sont créées.
    
3. Cliquez sur **Avancé**. Dans la boîte de dialogue **Sélectionner un emplacement de fichier de base de données**, sélectionnez l’une des options suivantes :
    
   - **Déterminer automatiquement l’emplacement du fichier de base de données** : si vous sélectionnez cette option, le générateur de topologie utilise un algorithme intégré pour sélectionner l’emplacement de stockage des journaux de bases de données et des fichiers de données.
    
   - **Utiliser SQL Server instance par défaut**. Si vous sélectionnez cette option, l’algorithme intégré n’est pas utilisé pour choisir les emplacements de stockage pour les journaux de base de données et les fichiers de données. Au lieu de cela, les fichiers journaux et de données sont stockés dans les emplacements spécifiés par le chemin d’accès par défaut de SQL Server (les chemins d’accès doivent être configurés dans avancée par un administrateur de SQL Server). Fichiers de données seront stockés dans l’emplacement de fichier de données SQL Server par défaut pendant que les fichiers journaux seront stockés dans l’emplacement du fichier journal SQL Server par défaut.
    
4. Cliquez sur **OK**.
    
5. Dans la page **Créer des bases de données**, cliquez sur **Suivant**.
    
6. Dans la page **Création de bases de données terminée**, cliquez sur **Terminer**.
    

