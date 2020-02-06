---
title: Préparer le serveur Standard Edition (appel)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Sur la page exécution des commandes, les tâches d’installation de SQL Server Express et de configuration pour fonctionner en tant que magasin de gestion centrale peuvent être affichées dans le volet Office. Par défaut, une instance de base de données SQL Server nommée RTC est créée. Des règles de pare-feu sont également créées pour autoriser l’accès entrant et sortant aux serveurs et clients pour communiquer avec la base de données et l’instance. Une fois la tâche effectuée, vous pouvez sélectionner le fichier journal dans la liste déroulante. Le fichier journal porte le nom de l’ordinateur local bootstrap. Après avoir sélectionné le fichier journal, cliquez sur Afficher le journal. Examinez le fichier journal pour afficher les erreurs et les avertissements. Lorsque vous êtes prêt à poursuivre, cliquez sur Terminer. Si ce n’est déjà fait, vous devez maintenant définir votre topologie avec le générateur de topologie.
ms.openlocfilehash: 0a1b8245df8e50ba4da73c98e9dcb865446a0ecc
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796965"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Préparer le serveur Standard Edition (appel)
 
Sur la page **exécution des commandes** , les tâches d’installation de SQL Server Express et de configuration pour fonctionner en tant que magasin de gestion centrale peuvent être affichées dans le volet Office. Par défaut, une instance de base de données SQL Server nommée RTC est créée. Des règles de pare-feu sont également créées pour autoriser l’accès entrant et sortant aux serveurs et clients pour communiquer avec la base de données et l’instance. Une fois la tâche effectuée, vous pouvez sélectionner le fichier journal dans la liste déroulante. Le fichier journal porte le nom de l' **ordinateur local bootstrap**. Après avoir sélectionné le fichier journal, cliquez sur **afficher le journal**. Examinez le fichier journal pour afficher les erreurs et les avertissements. Lorsque vous êtes prêt à poursuivre, cliquez sur **Terminer.** Si ce n’est déjà fait, vous devez maintenant définir votre topologie avec le générateur de topologie.
  
> [!IMPORTANT]
> L’installation de SQL Server Express peut prendre un certain temps. Lors de l’installation, aucune progression n’est visible à l’écran ou par le volet Office. Pour surveiller l’installation, utilisez le gestionnaire des tâches Windows et recherchez les processus MSIExec et les fichiers d’installation de SQL Server. De cette façon, vous pouvez afficher l’état de l’installation et vérifier qu’elle est en cours d’installation. Selon les facteurs au-delà de la portée de cette rubrique d’aide, l’installation de l’instance SQL Server peut prendre jusqu’à 15 minutes. 
  

