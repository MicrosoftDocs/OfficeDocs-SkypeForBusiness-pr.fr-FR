---
title: Activer les utilisateurs pour E9-1-1 dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Décisions nécessaires à la stratégie d’emplacement pour un déploiement E9-1-1 dans Skype Entreprise Server Voix Entreprise, y compris les utilisateurs à activer et la prise en charge des utilisateurs itinérants.
ms.openlocfilehash: 877e813df4d1ace9084586702836db96dbb149a5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392426"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Activer les utilisateurs pour E9-1-1 dans Skype Entreprise Server
 
Décisions nécessaires à la stratégie d’emplacement pour un déploiement E9-1-1 dans Skype Entreprise Server Voix Entreprise, y compris les utilisateurs à activer et la prise en charge des utilisateurs itinérants.
  
Lors de l’inscription du client, Skype Entreprise Server utilise une stratégie d’emplacement pour configurer les propriétés E9-1-1 Voix Entreprise utilisateurs à accès unique. Cette stratégie contient les paramètres qui définissent la façon dont E9-1-1 est implémenté. Par exemple, la stratégie d’emplacement contient des informations telles que la chaîne de numérotation d’urgence, et si un utilisateur doit ou non entrer manuellement un emplacement si le service Informations sur l’emplacement n’en fournit pas automatiquement un. Pour obtenir une définition complète d’une stratégie d’emplacement, voir [Plan location policies for Skype Entreprise Server](location-policies.md).
  
Skype Entreprise Server pouvez affecter une stratégie d’emplacement à des clients basés sur un sous-réseau ou à des utilisateurs basés sur une stratégie globale, par site ou par utilisateur. Pour vous aider à prendre une décision quant au mode d’activation des utilisateurs, commencez par répondre aux questions suivantes.
  
 **Envisagez-vous d’activer tous les utilisateurs ou de limiter la prise en charge à des zones géographiques spécifiques de l’entreprise ?**
  
> Vous pouvez assigner un emplacement à tous les utilisateurs de votre entreprise à l’aide d’une stratégie d’emplacement globale. Toutefois, en attribuant une stratégie d’emplacement à un site réseau Skype Entreprise Server, puis en ajoutant des sous-réseaux au site, vous pouvez limiter la prise en charge E9-1-1 à des emplacements sélectionnés au sein de l’entreprise et spécifier un comportement de routage E9-1-1 par site. 
    
 **Envisagez-vous d’activer des utilisateurs individuels au moyen d’une stratégie utilisateur ?**
  
> Vous pouvez assigner directement des stratégies d’emplacement à des utilisateurs ou des objets contact de téléphone de partie commune spécifiques si vous voulez personnaliser leur prise en charge du service E-9-1-1.
    
 **Quand des clients se trouvent en dehors du réseau ou se connectent à partir d’un sous-réseau non défini, ces clients doivent-ils bénéficier du service E9-1-1 ?**
  
> Si une stratégie d’emplacement globale, de site ou par utilisateur est attribuée aux utilisateurs, ils peuvent être tenus d’entrer manuellement un emplacement dans le client si le client ne se trouve pas dans un sous-réseau défini ou si aucun emplacement n’a été trouvé par le service Informations d’emplacement. Pour plus d’informations, voir [Définir l’expérience utilisateur pour](manually-acquiring-a-location.md) l’acquisition manuelle d’un emplacement dans Skype Entreprise Server.
    

