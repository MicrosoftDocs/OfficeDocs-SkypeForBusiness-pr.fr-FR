---
title: Préparer le serveur Standard Edition (introduction)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: Pour commencer l’installation d’un Skype pour Business Server 2015 Standard Edition server qui contiendra le magasin Central de gestion et autres services colocalisés que vous sélectionnez, vous devez être connecté en tant que membre du groupe Administrateurs local sur le serveur qui sera devenir le serveur Standard Edition server. La page préparer Standard Edition Server en détail la configuration requise pour l’installation initiale. L’ordinateur doit être membre du domaine dans lequel vous allez le déployer, et vous devez avoir réussi la préparation du schéma, de la forêt et du domaine pour votre forêt.
ms.openlocfilehash: 9c43f3bc4574d35577b483cf1ca0748f78f3d04a
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="prepare-single-standard-edition-server-intro"></a>Préparer le serveur Standard Edition (introduction)
 
Pour commencer l’installation d’un Skype pour Business Server 2015 Standard Edition server qui contiendra le magasin Central de gestion et autres services colocalisés que vous sélectionnez, vous devez être connecté en tant que membre du groupe Administrateurs local sur le serveur qui sera devenir le serveur Standard Edition server. La page **Préparer le serveur Standard Edition** détaille les conditions requises pour l’installation initiale. L’ordinateur doit être membre du domaine dans lequel vous allez le déployer, et vous devez avoir réussi la préparation du schéma, de la forêt et du domaine pour votre forêt.
  
Cette tâche particulière est conçue pour configurer un serveur Standard Edition comme premier serveur de votre infrastructure. Cela installe le magasin Central de gestion qui est SQL Server Express, sur le serveur Standard Edition server. Si vous disposez déjà d’un autre serveur Standard Edition ou d’un pool frontal déployé, vous devez cliquer sur **Annuler**.
  
> [!NOTE]
> Après avoir complété cette tâche, vous installerez le Générateur de topologie (si elle n’avez pas déjà installé) et configurer votre document de topologie. Vous ne pouvez publier votre document de topologie jusqu'à ce que vous ayez un magasin Central de gestion disponible, ce qui est déployé en effectuant les tâches décrites dans cette rubrique. 
  

