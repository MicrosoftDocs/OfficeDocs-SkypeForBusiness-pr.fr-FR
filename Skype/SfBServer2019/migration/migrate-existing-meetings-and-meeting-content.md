---
title: Migration des réunions existantes et du contenu des réunions
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Lorsque vous dépassez un compte d’utilisateur d’un serveur 2019 Skype entreprise Server, les informations suivantes sont déplacées à l’aide de ce compte d’utilisateur:'
ms.openlocfilehash: c8f87b46054a93af87c938d3da7a2a86be9cb0bf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237997"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migration des réunions existantes et du contenu des réunions

Lorsqu’un compte d’utilisateur est déplacé vers un serveur Skype entreprise Server 2019, les informations suivantes sont déplacées à l’aide de ce compte d’utilisateur:
  
- **Réunions déjà planifiées par l’utilisateur**. Cela inclut le déplacement des répertoires de conférences et des données de conférence.
    
- **Code confidentiel (pin) de l’utilisateur**. Le code confidentiel actuel de l’utilisateur continue de fonctionner tant qu’il n’a pas expiré ou que l’utilisateur ne demande pas de nouveau code secret.
    
Les informations de compte d’utilisateur suivantes ne sont pas déplacées vers le nouveau serveur.
  
- **Contenu**de la réunion. Pour déplacer le contenu partagé pendant une réunion, tel que PowerPoint, un tableau blanc, des pièces jointes ou des données de sondage, utilisez le paramètre **-MoveConferenceData** dans le cadre de l’applet de commande **Move-Csuser** . 
    

