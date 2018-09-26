---
title: Migration des réunions existantes et du contenu de la réunion
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Lorsqu’un compte d’utilisateur est déplacé à partir d’à un Skype pour Business Server 2019 server, les informations suivantes sont déplacées avec ce compte d’utilisateur :'
ms.openlocfilehash: 03ccad0498af777c7d93765af7df2baf5da51f83
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030370"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migration des réunions existantes et du contenu de la réunion

Lorsqu’un compte d’utilisateur est déplacé vers un Skype pour Business Server 2019 server, les informations suivantes sont déplacées avec ce compte d’utilisateur :
  
- **Réunions déjà planifiées par l’utilisateur**. Cela inclut le déplacement des annuaires de conférence et données de conférence.
    
- **Confidentiel l’utilisateur (PIN)**. Code confidentiel actuel de l’utilisateur continue de fonctionner jusqu'à ce qu’il expire ou que l’utilisateur demande un nouveau code confidentiel.
    
Les informations de compte d’utilisateur suivantes ne déplacent pas vers le nouveau serveur.
  
- **Contenu de la réunion**. Afin de déplacer le contenu partagé au cours d’une réunion, telles que PowerPoint, tableau blanc, les pièces jointes ou les données de sondage, utilisent le paramètre **- MoveConferenceData** dans le cadre de l’applet de commande **Move-CsUser** . 
    

