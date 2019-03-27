---
title: Director (Planning Tool)
ms.reviewer: ''
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
description: Un directeur est un serveur exécutant Skype pour le logiciel de communication Business Server 2015 qui peut authentifier les demandes des utilisateurs, mais qui n’héberge pas des comptes d’utilisateurs.
ms.openlocfilehash: b6cdecd01183f8e249aaf97e6b4e7bbbbfcbe7cd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885304"
---
# <a name="director-planning-tool"></a>Director (Planning Tool)
 
Un directeur est un serveur exécutant Skype pour le logiciel de communication Business Server 2015 qui peut authentifier les demandes des utilisateurs, mais qui n’héberge pas des comptes d’utilisateurs. 
  
Ce rôle est facultatif, que choisissez de déployer un directeur dans les deux scénarios suivants :
  
- Si vous activez l’accès des utilisateurs externes en déployant des serveurs de périphérie, vous devez également déployer un directeur. Dans ce scénario, le directeur authentifie les utilisateurs externes, puis transmet le trafic sur les serveurs internes. Lorsqu’un directeur est utilisé pour authentifier des utilisateurs externes, il évite les serveurs du pool frontal à partir de la charge de l’authentification de ces utilisateurs. Il permet également d’isoler les pools frontaux internes du trafic malveillant, telles que les attaques par déni de service. Si le réseau est réparti avec le trafic externe non valide dans ce type d’attaque, ce trafic se termine sur le directeur.
    
- Si vous déployez plusieurs pools frontaux à un site central, vous pouvez simplifier les demandes d’authentification et améliorer les performances en ajoutant un directeur à ce site. Dans ce scénario, toutes les demandes en premier pour le directeur, qui route vers le pool frontal correct.
    

