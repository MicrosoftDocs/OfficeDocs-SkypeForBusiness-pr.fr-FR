---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: Un directeur est un serveur exécutant le logiciel de communication Skype Entreprise Server qui peut authentifier les demandes des utilisateurs, mais n’a pas de compte d’utilisateur.
ms.openlocfilehash: 0c76fb5290715bb394b4c84ffadad3a2e9dd74db
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801094"
---
# <a name="director-planning-tool"></a>Director (Planning Tool)
 
Un directeur est un serveur exécutant le logiciel de communication Skype Entreprise Server qui peut authentifier les demandes des utilisateurs, mais n’a pas de compte d’utilisateur. 
  
Ce rôle est facultatif, vous pouvez choisir de déployer un directeur dans les deux scénarios suivants :
  
- Si vous activez l’accès par des utilisateurs externes en déployant des serveurs Edge, vous devez également déployer un directeur. Dans ce scénario, le directeur authentifier les utilisateurs externes, puis transmet leur trafic aux serveurs internes. Lorsqu’un directeur est utilisé pour authentifier des utilisateurs externes, il décharge les serveurs du pool frontal de la surcharge d’authentification de ces utilisateurs. Elle permet également d’isoler les pools frontux internes du trafic malveillant tel que les attaques par déni de service. Si le réseau est saturé par du trafic externe non valide dans le cadre d’une telle attaque, tout ce trafic s’arrête au niveau du directeur.
    
- Si vous déployez plusieurs pools frontux sur un site central, en ajoutant un directeur à ce site, vous pouvez rationaliser les demandes d’authentification et améliorer les performances. Dans ce scénario, toutes les demandes sont d’abord reçues par le directeur, qui les a ensuite route vers le pool frontal correct.
    

