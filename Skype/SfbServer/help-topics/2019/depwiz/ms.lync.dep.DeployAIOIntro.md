---
title: Préparer le serveur Standard Edition (introduction)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: Pour commencer l’installation d’un serveur Skype entreprise Server Standard Edition qui doit contenir le magasin de gestion central et d’autres services colocalisés que vous sélectionnez, vous devez être connecté en tant que membre du groupe d’administrateurs locaux sur le serveur qui deviendra serveur Standard Edition. La page Préparer le serveur Standard Edition détaille les conditions requises pour l’installation initiale. L’ordinateur doit être membre du domaine dans lequel vous allez le déployer, et vous devez avoir réussi la préparation du schéma, de la forêt et du domaine pour votre forêt.
ms.openlocfilehash: e1d9119e07a813476fddf39ee46e43bc686cab45
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692229"
---
# <a name="prepare-single-standard-edition-server-intro"></a>Préparer le serveur Standard Edition (introduction)
 
Pour commencer l’installation d’un serveur Skype entreprise Server Standard Edition qui doit contenir le magasin de gestion central et d’autres services colocalisés que vous sélectionnez, vous devez être connecté en tant que membre du groupe d’administrateurs locaux sur le serveur qui deviendra serveur Standard Edition. La page **Préparer le serveur Standard Edition** détaille les conditions requises pour l’installation initiale. L’ordinateur doit être membre du domaine dans lequel vous allez le déployer, et vous devez avoir réussi la préparation du schéma, de la forêt et du domaine pour votre forêt.
  
Cette tâche particulière est conçue pour configurer un serveur Standard Edition comme premier serveur de votre infrastructure. Cette tâche installe le magasin de gestion central, qui est SQL Server Express, sur le serveur Standard Edition Server. Si vous disposez déjà d’un autre serveur Standard Edition ou d’un pool frontal déployé, vous devez cliquer sur **Annuler**.
  
> [!NOTE]
> À l’issue de cette tâche, vous allez installer le générateur de topologie (si vous ne l’avez pas déjà installé) et configurer votre document topologique. Vous ne pouvez pas publier votre document topologique tant que vous n’avez pas de banque d’administration centrale disponible, qui est déployée en exécutant la tâche décrite dans cette rubrique. 
  

