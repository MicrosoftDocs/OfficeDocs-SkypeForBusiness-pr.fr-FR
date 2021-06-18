---
title: Préparer le serveur Standard Edition (appeler)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: Dans la page Exécution de commandes, les tâches d’installation de SQL Server Express et de configuration pour agir en tant que magasin central de gestion peuvent être vues dans le volet Des tâches. Par défaut, une instance d’une base SQL Server basée sur SQL Server appelée RTC est créée. Des règles de pare-feu sont également créées pour autoriser l’accès entrant et sortant des clients et des serveurs en vue de communiquer avec la base de données et l’instance. Une fois la tâche achevée, vous pouvez sélectionner le fichier journal dans la liste déroulante. Le fichier journal s’appelle Démarrage de la machine locale. Une fois le fichier journal sélectionné, cliquez sur Afficher le journal. Recherchez de possibles erreurs et avertissements dans le fichier journal. Lorsque vous êtes prêt à continuer, cliquez sur Terminer. Vous devez maintenant définir votre topologie avec le Générateur de topologie si vous ne l’avez pas déjà fait.
ms.openlocfilehash: c3e6e01f7aed0471d8f1eed0ad79f8ef6320f86a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820614"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Préparer le serveur Standard Edition (appeler)
 
Dans **la** page Exécution de commandes, les tâches d’installation de SQL Server Express et de configuration pour agir en tant que magasin central de gestion peuvent être vues dans le volet Des tâches. Par défaut, une instance d’une base SQL Server basée sur SQL Server appelée RTC est créée. Des règles de pare-feu sont également créées pour autoriser l’accès entrant et sortant des clients et des serveurs en vue de communiquer avec la base de données et l’instance. Une fois la tâche achevée, vous pouvez sélectionner le fichier journal dans la liste déroulante. Le fichier journal s’appelle **Démarrage de la machine locale**. Une fois le fichier journal sélectionné, cliquez sur **Afficher le journal**. Recherchez de possibles erreurs et avertissements dans le fichier journal. Lorsque vous êtes prêt à continuer, cliquez sur **Terminer.** Vous devez maintenant définir votre topologie avec le Générateur de topologie si vous ne l’avez pas déjà fait.
  
> [!IMPORTANT]
> L’installation de SQL Server Express peut prendre un certain temps. Aucune barre de progression n’est visible à l’écran ou dans le volet des tâches pendant l’installation. Pour surveiller l’installation, vous devez utiliser le Gestionnaire des tâches Windows et rechercher les processus MSIExec et les fichiers d’installation pour SQL Server. Ainsi, vous pouvez voir le statut de l’installation et vous assurer de sa progression. Selon des facteurs au-delà de la portée de cette rubrique d’aide, l’installation de l’instance de SQL Server peut prendre jusqu’à 15 minutes. 
  

