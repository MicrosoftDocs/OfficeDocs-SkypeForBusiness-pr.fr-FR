---
title: Préparer le serveur Standard Edition (introduction)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: Pour commencer l’installation d’un serveur Édition Standard Skype Entreprise Server 2015 qui doit contenir le magasin central de gestion et d’autres services cococérés que vous sélectionnez, vous devez être connecté en tant que membre du groupe Administrateurs local sur le serveur qui deviendra le serveur Édition Standard. La page Préparer le serveur Standard Edition détaille les conditions requises pour l’installation initiale. L’ordinateur doit être membre du domaine dans lequel vous allez le déployer, et vous devez avoir réussi la préparation du schéma, de la forêt et du domaine pour votre forêt.
ms.openlocfilehash: daca3f64809b6ea6d2ed5e94cdaf3a38ebef6f4d9ba75885b6d6d0aff50ecfd3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313522"
---
# <a name="prepare-single-standard-edition-server-intro"></a>Préparer le serveur Standard Edition (introduction)
 
Pour commencer l’installation d’un serveur Édition Standard Skype Entreprise Server 2015 qui doit contenir le magasin central de gestion et d’autres services cococérés que vous sélectionnez, vous devez être connecté en tant que membre du groupe Administrateurs local sur le serveur qui deviendra le serveur Édition Standard. La page **Préparer le serveur Standard Edition** détaille les conditions requises pour l’installation initiale. L’ordinateur doit être membre du domaine dans lequel vous allez le déployer, et vous devez avoir réussi la préparation du schéma, de la forêt et du domaine pour votre forêt.
  
Cette tâche particulière est conçue pour configurer un serveur Standard Edition comme premier serveur de votre infrastructure. Cette tâche installe le magasin central de gestion, qui est SQL Server Express, sur le Édition Standard serveur. Si vous disposez déjà d’un autre serveur Standard Edition ou d’un pool frontal déployé, vous devriez cliquer sur **Annuler**.
  
> [!NOTE]
> Après avoir terminé cette tâche, vous installez le Générateur de topologies (si vous ne l’avez pas déjà installé) et configurez votre document de topologie. Vous ne pouvez pas publier votre document de topologie tant que vous n’avez pas de magasin central de gestion disponible, qui est déployé en effectuant la tâche décrite dans cette rubrique. 
  

