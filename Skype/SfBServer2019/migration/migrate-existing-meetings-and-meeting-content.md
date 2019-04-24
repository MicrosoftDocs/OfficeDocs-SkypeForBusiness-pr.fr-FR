---
title: Migration des réunions existantes et du contenu des réunions
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Lorsqu’un compte d’utilisateur est déplacé à partir d’à un Skype pour Business Server 2019 server, les informations suivantes sont déplacées avec ce compte d’utilisateur :'
ms.openlocfilehash: bf10fa6b4ad4d555ce80dee5ec4e4a6584020ac7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231657"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migration des réunions existantes et du contenu des réunions

Lorsqu’un compte d’utilisateur est déplacé vers un Skype pour Business Server 2019 server, les informations suivantes sont déplacées avec ce compte d’utilisateur :
  
- **Réunions déjà planifiées par l’utilisateur**. Cela inclut le déplacement des annuaires de conférence et données de conférence.
    
- **Confidentiel l’utilisateur (PIN)**. Code confidentiel actuel de l’utilisateur continue de fonctionner jusqu'à ce qu’il expire ou que l’utilisateur demande un nouveau code confidentiel.
    
Les informations de compte d’utilisateur suivantes ne déplacent pas vers le nouveau serveur.
  
- **Contenu de la réunion**. Afin de déplacer le contenu partagé au cours d’une réunion, telles que PowerPoint, tableau blanc, les pièces jointes ou les données de sondage, utilisent le paramètre **- MoveConferenceData** dans le cadre de l’applet de commande **Move-CsUser** . 
    

