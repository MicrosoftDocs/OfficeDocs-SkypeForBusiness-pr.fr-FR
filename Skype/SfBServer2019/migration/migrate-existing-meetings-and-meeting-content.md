---
title: Migration des réunions existantes et du contenu des réunions
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Lorsqu’un compte d’utilisateur est déplacé de vers un serveur Skype entreprise Server 2019, les informations suivantes sont déplacées avec ce compte d’utilisateur :'
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752686"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migration des réunions existantes et du contenu des réunions

Lorsqu’un compte d’utilisateur est déplacé vers un serveur Skype entreprise Server 2019, les informations suivantes sont déplacées avec ce compte d’utilisateur :
  
- **Réunions déjà planifiées par l’utilisateur** : cela comprend le déplacement des répertoires de conférence et des données de conférence.
    
- **Code confidentiel de l’utilisateur**. Le code confidentiel actuel de l’utilisateur continue de fonctionner jusqu’à son expiration ou que l’utilisateur demande un nouveau code confidentiel.
    
Les informations de compte d’utilisateur suivantes ne se déplacent pas vers le nouveau serveur.
  
- **Contenu de la réunion** Pour déplacer le contenu partagé au cours d’une réunion, comme PowerPoint, le tableau blanc, les pièces jointes ou les données de sondage, utilisez le paramètre **-MoveConferenceData** dans le cadre de la cmdlet **Move-Csuser** . 
    

