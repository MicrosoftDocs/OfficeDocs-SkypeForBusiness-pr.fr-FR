---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Un directeur est un serveur exécutant un logiciel de communication Skype entreprise Server capable d’authentifier les demandes des utilisateurs, mais qui ne possède pas de compte d’utilisateur particulier.
ms.openlocfilehash: 4247642851b104b999521b664931ccbd3d6d5f61
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797335"
---
# <a name="director-planning-tool"></a>Director (Planning Tool)
 
Un directeur est un serveur exécutant un logiciel de communication Skype entreprise Server capable d’authentifier les demandes des utilisateurs, mais qui ne possède pas de compte d’utilisateur particulier. 
  
Ce rôle est facultatif, vous pouvez choisir de déployer un réalisateur dans les deux scénarios suivants :
  
- Si vous autorisez l’accès par des utilisateurs externes en déployant des serveurs de périphérie, vous devez également déployer un directeur. Dans ce scénario, le directeur authentifie les utilisateurs externes, puis transmet leur trafic aux serveurs internes. Lorsqu’un directeur est utilisé pour authentifier des utilisateurs externes, il allège la surcharge des serveurs du pool frontal en effectuant une authentification de ces utilisateurs. Il permet également d’isoler les listes frontales internes du trafic malveillant, par exemple pour les attaques par déni de service. Si le réseau est inondé de trafic externe non valide lors d’une telle attaque, il se termine au directeur.
    
- Si vous déployez plusieurs pools front-end sur un site central, en ajoutant un réalisateur à ce site, vous pouvez rationaliser les demandes d’authentification et améliorer les performances. Dans ce scénario, toutes les demandes sont d’abord adressées au directeur, qui les route vers le pool frontal approprié.
    

