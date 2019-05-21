---
title: Migration des réunions existantes et du contenu des réunions
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Lorsque vous dépassez un compte d’utilisateur d’un serveur 2019 Skype entreprise Server, les informations suivantes sont déplacées à l’aide de ce compte d’utilisateur:'
ms.openlocfilehash: 4b5c7981374f3e2bf6dc2d87a0b21d972ddb14ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288599"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migration des réunions existantes et du contenu des réunions

Lorsqu’un compte d’utilisateur est déplacé vers un serveur Skype entreprise Server 2019, les informations suivantes sont déplacées à l’aide de ce compte d’utilisateur:
  
- **Réunions déjà planifiées par l’utilisateur**. Cela inclut le déplacement des répertoires de conférences et des données de conférence.
    
- **Code confidentiel (pin) de l’utilisateur**. Le code confidentiel actuel de l’utilisateur continue de fonctionner tant qu’il n’a pas expiré ou que l’utilisateur ne demande pas de nouveau code secret.
    
Les informations de compte d’utilisateur suivantes ne sont pas déplacées vers le nouveau serveur.
  
- **Contenu**de la réunion. Pour déplacer le contenu partagé pendant une réunion, tel que PowerPoint, un tableau blanc, des pièces jointes ou des données de sondage, utilisez le paramètre **-MoveConferenceData** dans le cadre de l’applet de commande **Move-Csuser** . 
    

