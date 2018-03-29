---
title: Préparer le serveur d’édition Standard unique (appel)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: Sur la page de commandes en cours d’exécution, les tâches de l’installation de l’édition SQL Server Express et configuration pour agir en tant que le magasin Central de gestion peuvent être affichés dans le volet Office. Par défaut, une instance d’une base de données basée sur SQL Server, nommée RTC est créée. Règles de pare-feu sont également créés pour permettre l’accès entrant et sortant pour les serveurs et les clients de communiquer avec la base de données et l’instance. Une fois la tâche terminée, vous pouvez sélectionner le fichier journal dans la liste déroulante. Le fichier journal est nommé démarrage machine locale. Après avoir sélectionné le fichier journal, cliquez sur Afficher le journal. Passez en revue le fichier journal pour les erreurs et les avertissements. Lorsque vous êtes prêt à continuer, cliquez sur Terminer. Vous devez maintenant définir votre topologie avec le Générateur de topologies si vous ne le n'avez pas déjà fait.
ms.openlocfilehash: d900c383d0f434176ff18b3f310c41042df75b2e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Préparer le serveur d’édition Standard unique (appel)
 
Dans la page **commandes d’en cours d’exécution** , les tâches de l’installation de l’édition SQL Server Express et configuration pour agir en tant que le magasin Central de gestion sont consultables dans le volet Office. Par défaut, une instance d’une base de données basée sur SQL Server, nommée RTC est créée. Règles de pare-feu sont également créés pour permettre l’accès entrant et sortant pour les serveurs et les clients de communiquer avec la base de données et l’instance. Une fois la tâche terminée, vous pouvez sélectionner le fichier journal dans la liste déroulante. Le fichier journal est nommé **démarrage machine locale**. Après avoir sélectionné le fichier journal, cliquez sur **Afficher le journal**. Passez en revue le fichier journal pour les erreurs et les avertissements. Lorsque vous êtes prêt à continuer, cliquez sur **fin.** Vous devez maintenant définir votre topologie avec le Générateur de topologies si vous ne le n'avez pas déjà fait.
  
> [!IMPORTANT]
> L’installation de SQL Server Express peut prendre un certain temps pour terminer. Lors de l’installation, aucune progression n’est visible à l’écran ou le volet Office. Pour contrôler l’installation, utilisez le Gestionnaire des tâches Windows et recherchez les processus MSIExec et les fichiers d’installation de SQL Server. De cette façon, vous pouvez afficher l’état de l’installation et assurez-vous que l’installation est en cours. En fonction de facteurs dépasse le cadre de cette rubrique d’aide, il peut prendre jusqu'à 15 minutes ou plus pour l’installation du SQL Server instance pour terminer. 
  

