---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Un directeur est un serveur qui utilise le logiciel de communication 2015 de Skype entreprise Server qui peut authentifier les demandes des utilisateurs, mais n’est pas un compte d’utilisateur particulier.
ms.openlocfilehash: 48b691262dc638faf6f0aa9910a5adac3c1f0e46
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684247"
---
# <a name="director-planning-tool"></a>Director (Planning Tool)
 
Un directeur est un serveur qui utilise le logiciel de communication 2015 de Skype entreprise Server qui peut authentifier les demandes des utilisateurs, mais n’est pas un compte d’utilisateur particulier. 
  
Ce rôle est facultatif, vous pouvez choisir de déployer un réalisateur dans les deux scénarios suivants :
  
- Si vous autorisez l’accès par des utilisateurs externes en déployant des serveurs de périphérie, vous devez également déployer un directeur. Dans ce scénario, le directeur authentifie les utilisateurs externes, puis transmet leur trafic aux serveurs internes. Lorsqu’un directeur est utilisé pour authentifier des utilisateurs externes, il allège la surcharge des serveurs du pool frontal en effectuant une authentification de ces utilisateurs. Il permet également d’isoler les listes frontales internes du trafic malveillant, par exemple pour les attaques par déni de service. Si le réseau est inondé de trafic externe non valide lors d’une telle attaque, il se termine au directeur.
    
- Si vous déployez plusieurs pools front-end sur un site central, en ajoutant un réalisateur à ce site, vous pouvez rationaliser les demandes d’authentification et améliorer les performances. Dans ce scénario, toutes les demandes sont d’abord adressées au directeur, qui les route vers le pool frontal approprié.
    

