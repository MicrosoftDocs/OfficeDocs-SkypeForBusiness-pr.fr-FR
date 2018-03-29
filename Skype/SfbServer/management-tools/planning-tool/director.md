---
title: Directeur (outil de planification)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Un directeur est un serveur exécutant Skype pour le logiciel de communication Business Server 2015 qui peut authentifier les demandes de l’utilisateur, mais ne pas accueil des comptes d’utilisateurs.
ms.openlocfilehash: b379388b05e4beda934b13517f36bc792b6f0748
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="director-planning-tool"></a>Directeur (outil de planification)
 
Un directeur est un serveur exécutant Skype pour le logiciel de communication Business Server 2015 qui peut authentifier les demandes de l’utilisateur, mais ne pas accueil des comptes d’utilisateurs. 
  
Ce rôle est facultatif, que vous choisissez de déployer un directeur dans les deux scénarios suivants :
  
- Si vous activez l’accès par des utilisateurs externes en déployant les serveurs Edge, vous devez également déployer un directeur. Dans ce scénario, le directeur authentifie les utilisateurs externes et transmet ensuite le trafic vers les serveurs internes. Lorsqu’un directeur est utilisé pour authentifier les utilisateurs externes, il évite les serveurs du pool Front-End de la charge de l’authentification de ces utilisateurs. Il permet également d’isoler les pools de Front-End internes de trafic malveillant, comme les attaques de déni de service. Si le réseau est inondé de trafic d’externe non valide dans une telle attaque, ce trafic se termine sur le directeur.
    
- Si vous déployez plusieurs pools de Front-End sur un site central, vous pouvez rationaliser les demandes d’authentification et améliorer les performances en ajoutant un directeur à ce site. Dans ce scénario, toutes les demandes en premier au directeur, qui les achemine ensuite dans le pool de Front-End approprié.
    

