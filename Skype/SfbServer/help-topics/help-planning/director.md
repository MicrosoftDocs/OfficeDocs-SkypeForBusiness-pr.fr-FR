---
title: Skype Entreprise Server Outil de planification de directeur
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
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
description: Un directeur est un serveur exécutant Skype Entreprise Server 2015 qui peut authentifier les demandes des utilisateurs, mais n’a pas de compte d’utilisateur.
ms.openlocfilehash: 969b45a39da201a1de31fe1cf3261dce2cb20070de454770691a9d6c85dcae3a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344963"
---
# <a name="skype-for-business-server-director-planning-tool"></a>Skype Entreprise Server Outil de planification de directeur
 
Un directeur est un serveur exécutant Skype Entreprise Server 2015 qui peut authentifier les demandes des utilisateurs, mais n’a pas de compte d’utilisateur. 
  
Ce rôle est facultatif, vous pouvez choisir de déployer un directeur dans les deux scénarios suivants :
  
- Si vous activez l’accès par des utilisateurs invités en déployant des serveurs Edge, vous devez également déployer un directeur. Dans ce scénario, le directeur authentifier les invités, puis transmet leur trafic aux serveurs internes. Lorsqu’un directeur est utilisé pour authentifier les invités, il décharge les serveurs du pool frontal de la surcharge de l’authentification de ces utilisateurs. Elle permet également d’isoler les pools frontux internes du trafic malveillant tel que les attaques par déni de service. Si le réseau est saturé par du trafic externe non valide dans le cadre d’une telle attaque, tout ce trafic s’arrête au niveau du directeur.
    
- Si vous déployez plusieurs pools frontux sur un site central, en ajoutant un directeur à ce site, vous pouvez rationaliser les demandes d’authentification et améliorer les performances. Dans ce scénario, toutes les demandes sont d’abord reçues par le directeur, qui les a ensuite route vers le pool frontal correct.
    

