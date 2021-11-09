---
title: Préparer le serveur Standard Edition (introduction)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: Pour commencer l’installation d’un serveur Skype Entreprise Server Édition Standard qui doit contenir le magasin central de gestion et d’autres services cococérés que vous sélectionnez, vous devez être connecté en tant que membre du groupe Administrateurs local sur le serveur qui deviendra le serveur Édition Standard. La page Préparer le serveur Standard Edition détaille les conditions requises pour l’installation initiale. L’ordinateur doit être membre du domaine dans lequel vous allez le déployer, et vous devez avoir réussi la préparation du schéma, de la forêt et du domaine pour votre forêt.
ms.openlocfilehash: 6ed3b804fe2048a5f5da3c0f69676967823388bd
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828307"
---
# <a name="prepare-single-standard-edition-server-intro"></a>Préparer le serveur Standard Edition (introduction)
 
Pour commencer l’installation d’un serveur Skype Entreprise Server Édition Standard qui doit contenir le magasin central de gestion et d’autres services cococérés que vous sélectionnez, vous devez être connecté en tant que membre du groupe Administrateurs local sur le serveur qui deviendra le serveur Édition Standard. La page **Préparer le serveur Standard Edition** détaille les conditions requises pour l’installation initiale. L’ordinateur doit être membre du domaine dans lequel vous allez le déployer, et vous devez avoir réussi la préparation du schéma, de la forêt et du domaine pour votre forêt.
  
Cette tâche particulière est conçue pour configurer un serveur Standard Edition comme premier serveur de votre infrastructure. Cette tâche installe le magasin central de gestion, qui est SQL Server Express, sur le Édition Standard serveur. Si vous disposez déjà d’un autre serveur Standard Edition ou d’un pool frontal déployé, vous devriez cliquer sur **Annuler**.
  
> [!NOTE]
> Après avoir terminé cette tâche, vous installez le Générateur de topologies (si vous ne l’avez pas déjà installé) et configurez votre document de topologie. Vous ne pouvez pas publier votre document de topologie tant qu’un magasin central de gestion n’est pas disponible, ce qui est déployé en effectuant la tâche décrite dans cette rubrique. 
  

