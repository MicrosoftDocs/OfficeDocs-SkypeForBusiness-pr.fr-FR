---
title: Outil de planification de directeur
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
  - ms.lync.plan.Director
  - ms.lync.plan.Director
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: 'Un directeur est un serveur exécutant Skype Entreprise Server 2015 qui peut authentifier les demandes des utilisateurs, mais qui n’a pas de compte d’utilisateur.'
---

# <a name="director-planning-tool"></a>Outil de planification de directeur
 
Un directeur est un serveur exécutant Skype Entreprise Server 2015 qui peut authentifier les demandes des utilisateurs, mais qui n’a pas de compte d’utilisateur. 
  
Ce rôle est facultatif, vous pouvez choisir de déployer un directeur dans les deux scénarios suivants :
  
- Si vous activez l’accès par des utilisateurs invités en déployant des serveurs Edge, vous devez également déployer un directeur. Dans ce scénario, le directeur authentifier les invités, puis transmet leur trafic aux serveurs internes. Lorsqu’un directeur est utilisé pour authentifier les invités, il décharge les serveurs du pool frontal de la surcharge d’authentification de ces utilisateurs. Il permet également d’isoler les pools frontux internes du trafic malveillant tel que les attaques par déni de service. Si le réseau est saturé par du trafic externe non valide dans le cadre d’une telle attaque, tout ce trafic s’arrête au niveau du directeur.
    
- Si vous déployez plusieurs pools frontux sur un site central, en ajoutant un directeur à ce site, vous pouvez rationaliser les demandes d’authentification et améliorer les performances. Dans ce scénario, toutes les demandes sont d’abord reçues par le directeur, qui les a ensuite route vers le pool frontal correct.
    

