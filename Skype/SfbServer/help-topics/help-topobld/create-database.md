---
title: Créer des bases de données
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: Le générateur de topologie fournit un moyen d’installer des bases de données sur un magasin SQL Server. Lorsque vous installez des bases de données à l’aide du générateur de topologie, l’application lit les informations de la topologie, puis installe les bases de données requises sur l’ordinateur SQL Server spécifié ou le cluster SQL Server. C’est le seul type d’installation de base de données disponible par le biais du générateur de topologie. Si vous avez besoin d’installer une base de données spécifique sur un ordinateur spécifique, ou si vous devez installer une base de données colocalisée, vous devez utiliser l’interface de ligne de commande Windows PowerShell et l’applet de commande Install-CsDatabase.
ms.openlocfilehash: cd3bd6e24f0dc3ec21c5cfa8626d9696454855e7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820236"
---
# <a name="create-database"></a>Créer des bases de données
 
Le générateur de topologie fournit un moyen d’installer des bases de données sur un magasin SQL Server. Lorsque vous installez des bases de données à l’aide du générateur de topologie, l’application lit les informations de la topologie, puis installe les bases de données requises sur l’ordinateur SQL Server spécifié ou le cluster SQL Server. C’est le seul type d’installation de base de données disponible par le biais du générateur de topologie. Si vous avez besoin d’installer une base de données spécifique sur un ordinateur spécifique, ou si vous devez installer une base de données colocalisée, vous devez utiliser l’interface de ligne de commande Windows PowerShell et l’applet de commande [install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) .
  
### <a name="creating-a-database"></a>Création d’une base de données

1. Cliquez sur le nœud Skype entreprise Server 2015, puis cliquez sur **installer la base de données**.
    
2. Dans la boîte de dialogue **installer des bases de données** , dans la page créer une **base de données** , sélectionnez le nom de domaine complet (FQDN) du magasin SQL Server dans lequel les nouvelles bases de données doivent être créées.
    
3. Cliquez sur **Avancé**. Dans la boîte de dialogue **Sélectionner un emplacement de fichier de base de données**, sélectionnez l’une des options suivantes :
    
   - **Déterminer automatiquement l’emplacement du fichier de base de données** : si vous sélectionnez cette option, le générateur de topologie utilise un algorithme intégré pour sélectionner l’emplacement de stockage des journaux de bases de données et des fichiers de données.
    
   - **Utilisez les valeurs par défaut des instances SQL Server**. Si vous sélectionnez cette option, l’algorithme intégré n’est pas utilisé pour choisir les emplacements de stockage pour les journaux de base de données et les fichiers de données. Au lieu de cela, les fichiers de données et de journalisation sont stockés dans les emplacements spécifiés par le chemin d’accès par défaut de SQL Server (ces chemins doivent être configurés dans avancé par un administrateur SQL Server). Les fichiers de données seront stockés dans l’emplacement du fichier de données SQL Server par défaut alors que les fichiers journaux seront stockés dans l’emplacement du fichier journal SQL Server par défaut.
    
4. Cliquez sur **OK**.
    
5. Dans la page **Créer des bases de données**, cliquez sur **Suivant**.
    
6. Dans la page **Création de bases de données terminée**, cliquez sur **Terminer**.
    

