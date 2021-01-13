---
title: Créer des bases de données
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: Le Générateur de topologie permet d’installer des bases de données sur SQL Server magasin. Lorsque vous installez des bases de données à l’aide du Générateur de topologie, l’application lit les informations de la topologie, puis installe les bases de données requises sur l’ordinateur SQL Server ou le cluster SQL Server spécifié. C’est le seul type d’installation de base de données disponible par le biais du Générateur de topologie. Si vous devez installer une base de données spécifique sur un ordinateur spécifique, ou si vous devez installer une base de données c collocée, vous devez utiliser l’interface de ligne de commande Windows PowerShell et l’cmdlet Install-CsDatabase à la place.
ms.openlocfilehash: 0ba463ed2995aae2a31890633b7a959cf889837c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833084"
---
# <a name="create-database"></a>Création de base de données
 
Le Générateur de topologie permet d’installer des bases de données sur SQL Server magasin. Lorsque vous installez des bases de données à l’aide du Générateur de topologie, l’application lit les informations de la topologie, puis installe les bases de données requises sur l’ordinateur SQL Server ou le cluster SQL Server spécifié. C’est le seul type d’installation de base de données disponible par le biais du Générateur de topologie. Si vous avez besoin d’installer une base de données spécifique sur un ordinateur spécifique, ou si vous devez installer une base de données CsDatabase, vous devez utiliser l’interface de ligne de commande Windows PowerShell et l’cmdlet [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) à la place.
  
### <a name="creating-a-database"></a>Création d’une base de données

1. Cliquez sur le nœud Skype Entreprise Server 2015, puis cliquez sur Installer la base **de données.**
    
2. Dans  la boîte de dialogue Installer des bases de données, dans la **page** Créer une base de données, sélectionnez le nom de domaine complet (FQDN) du magasin SQL Server où les nouvelles bases de données doivent être créées.
    
3. Cliquez sur **Avancé**. Dans la boîte de dialogue **Sélectionner un emplacement de fichier de base de données**, sélectionnez l’une des options suivantes :
    
   - **Déterminer automatiquement l’emplacement du fichier de base de données**. Si vous sélectionnez cette option, le Générateur de topologie utilise un algorithme intégré pour choisir l’emplacement de stockage pour les journaux de bases de données et les fichiers de données.
    
   - **Utiliser les valeurs par défaut de l’instance SQL Server**. Si vous sélectionnez cette option, l’algorithme intégré n’est pas utilisé pour choisir les emplacements de stockage pour les journaux de bases de données et les fichiers de données. À la place, les fichiers journaux et les fichiers de données sont stockés aux emplacements spécifiés dans les chemins d’accès SQL Server par défaut (ces chemins doivent être configurés à l’avance par un administrateur SQL). Les fichiers de données seront stockés à l’emplacement attribué par défaut pour les fichiers de données SQL Server et les fichiers journaux SQL Server à leur emplacement défini par défaut.
    
4. Cliquez sur **OK**.
    
5. Dans la page **Créer des bases de données**, cliquez sur **Suivant**.
    
6. Dans la page **Création de bases de données terminée**, cliquez sur **Terminer**.
    

