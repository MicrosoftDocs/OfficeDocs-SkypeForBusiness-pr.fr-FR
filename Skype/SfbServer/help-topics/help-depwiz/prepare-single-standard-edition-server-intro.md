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
description: Pour commencer l’installation d’un Skype pour serveur 2015 Business Server Standard Edition qui contiendra le magasin Central de gestion et autres services COLOCALISÉES que vous sélectionnez, vous devez être connecté en tant que membre du groupe Administrateurs local sur le serveur qui sera devient le serveur Standard Edition. La page de serveur de l’Édition Standard unique préparation détaille la configuration requise pour l’installation initiale. L’ordinateur doit être membre du domaine dans lequel vous allez le déployer, et vous devez avoir réussi la préparation du schéma, de la forêt et du domaine pour votre forêt.
ms.openlocfilehash: 9c43f3bc4574d35577b483cf1ca0748f78f3d04a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-single-standard-edition-server-intro"></a>Préparer le serveur Standard Edition (introduction)
 
Pour commencer l’installation d’un Skype pour serveur 2015 Business Server Standard Edition qui contiendra le magasin Central de gestion et autres services COLOCALISÉES que vous sélectionnez, vous devez être connecté en tant que membre du groupe Administrateurs local sur le serveur qui sera devient le serveur Standard Edition. La page **Préparer le serveur Standard Edition** détaille les conditions requises pour l’installation initiale. L’ordinateur doit être membre du domaine dans lequel vous allez le déployer, et vous devez avoir réussi la préparation du schéma, de la forêt et du domaine pour votre forêt.
  
Cette tâche particulière est conçue pour configurer un serveur Standard Edition comme premier serveur de votre infrastructure. Cette tâche installe le magasin Central de gestion, ce qui est de SQL Server Express, sur le serveur Standard Edition. Si vous disposez déjà d’un autre serveur Standard Edition ou d’un pool frontal déployé, vous devez cliquer sur **Annuler**.
  
> [!NOTE]
> À la fin de cette tâche, vous installerez le Générateur de topologies (si vous n’en n'avez pas déjà installé il) et configurer votre document de la topologie. Vous ne pouvez pas publier votre document topologie jusqu'à ce que vous ayez un magasin Central de gestion disponible, lequel est déployée la tâche décrite dans cette rubrique. 
  

