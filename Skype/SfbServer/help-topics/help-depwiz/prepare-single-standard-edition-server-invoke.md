---
title: Préparer le serveur Standard Edition (appel)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: Dans la page de commandes en cours d’exécution, les tâches d’installation de SQL Server Express et de configuration pour agir en tant que magasin Central de gestion peuvent être affichés dans le volet Office. Par défaut, une instance d’une base de données basée sur SQL Server nommée RTC est créée. Règles de pare-feu sont également créés pour autoriser l’accès entrant et sortant pour les serveurs et clients de communiquer avec la base de données et l’instance. Une fois la tâche terminée, vous pouvez sélectionner le fichier journal dans la liste déroulante. Le fichier journal est nommé d’amorçage ordinateur local. Après avoir sélectionné le fichier journal, cliquez sur Afficher le journal. Passez en revue le fichier journal pour les erreurs et avertissements. Lorsque vous êtes prêt à continuer, cliquez sur Terminer. Vous devez maintenant définir votre topologie avec le Générateur de topologie si vous n’avez pas déjà fait.
ms.openlocfilehash: 665075799794d94328e0a5a3d9e1f9c603813ed7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880062"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Préparer le serveur Standard Edition (appel)
 
Sur la page **en cours d’exécution de commandes** , les tâches d’installation de SQL Server Express et de configuration pour agir en tant que magasin Central de gestion peuvent être affichés dans le volet Office. Par défaut, une instance d’une base de données basée sur SQL Server nommée RTC est créée. Règles de pare-feu sont également créés pour autoriser l’accès entrant et sortant pour les serveurs et clients de communiquer avec la base de données et l’instance. Une fois la tâche terminée, vous pouvez sélectionner le fichier journal dans la liste déroulante. Le fichier journal est nommé **d’amorçage ordinateur local**. Après avoir sélectionné le fichier journal, cliquez sur **Afficher le journal**. Passez en revue le fichier journal pour les erreurs et avertissements. Lorsque vous êtes prêt à continuer, cliquez sur **fin.** Vous devez maintenant définir votre topologie avec le Générateur de topologie si vous n’avez pas déjà fait.
  
> [!IMPORTANT]
> L’installation de SQL Server Express peut prendre du temps. Pendant l’installation, aucun avancement n’est visible dans l’écran ou dans le volet de tâches. Pour surveiller l’installation, vous utilisez le Gestionnaire des tâches Windows et recherchez les processus MSIExec et les fichiers d’installation pour SQL Server. De cette manière, vous pouvez afficher l’état de l’installation et assurez-vous que l’installation est en cours. En fonction des facteurs au-delà de la portée de cette rubrique d’aide, elle peut prendre jusqu'à 15 minutes ou plus pour l’installation de SQL Server instance pour terminer. 
  

