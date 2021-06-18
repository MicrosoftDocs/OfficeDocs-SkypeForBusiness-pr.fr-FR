---
title: Activer les utilisateurs pour E9-1-1 dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Décisions nécessaires à la stratégie d’emplacement pour un déploiement E9-1-1 dans Skype Entreprise Server Voix Entreprise, y compris les utilisateurs à activer et la prise en charge des utilisateurs itinérants.
ms.openlocfilehash: 9a2ced694357b9225555a05c10e93a1006a771b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825744"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Activer les utilisateurs pour E9-1-1 dans Skype Entreprise Server
 
Décisions nécessaires à la stratégie d’emplacement pour un déploiement E9-1-1 dans Skype Entreprise Server Voix Entreprise, y compris les utilisateurs à activer et la prise en charge des utilisateurs itinérants.
  
Lors de l’inscription du client, Skype Entreprise Server utilise une stratégie d’emplacement pour configurer les propriétés E9-1-1 Voix Entreprise utilisateurs activés. Cette stratégie contient les paramètres qui définissent la façon dont E9-1-1 est implémenté. Par exemple, la stratégie d’emplacement contient des informations telles que la chaîne de numérotation d’urgence, et si un utilisateur doit ou non entrer manuellement un emplacement si le service Informations sur l’emplacement n’en fournit pas automatiquement un. Pour obtenir une définition complète d’une stratégie d’emplacement, voir [Plan location policies for Skype for Business Server](location-policies.md).
  
Skype Entreprise Server peut affecter une stratégie d’emplacement à des clients basés sur un sous-réseau ou à des utilisateurs basés sur une stratégie globale, par site ou par utilisateur. Pour vous aider à prendre une décision quant au mode d’activation des utilisateurs, commencez par répondre aux questions suivantes.
  
 **Envisagez-vous d’activer tous les utilisateurs ou de limiter la prise en charge à des zones géographiques spécifiques de l’entreprise ?**
  
> Vous pouvez assigner un emplacement à tous les utilisateurs de votre entreprise à l’aide d’une stratégie d’emplacement globale. Toutefois, en attribuant une stratégie d’emplacement à un site réseau Skype Entreprise Server, puis en ajoutant des sous-réseaux au site, vous pouvez limiter la prise en charge E9-1-1 à des emplacements sélectionnés au sein de l’entreprise et spécifier un comportement de routage E9-1-1 par site. 
    
 **Envisagez-vous d’activer des utilisateurs individuels au moyen d’une stratégie utilisateur ?**
  
> Vous pouvez assigner directement des stratégies d’emplacement à des utilisateurs ou des objets contact de téléphone de partie commune spécifiques si vous voulez personnaliser leur prise en charge du service E-9-1-1.
    
 **Quand des clients se trouvent en dehors du réseau ou se connectent à partir d’un sous-réseau non défini, ces clients doivent-ils bénéficier du service E9-1-1 ?**
  
> Si une stratégie d’emplacement globale, de site ou par utilisateur est attribuée aux utilisateurs, ils peuvent être tenus d’entrer manuellement un emplacement dans le client si le client n’est pas situé dans un sous-réseau défini ou si aucun emplacement n’a été trouvé par le service d’informations d’emplacement. Pour plus d’informations, voir [Définir l’expérience utilisateur pour](manually-acquiring-a-location.md)l’acquisition manuelle d’un emplacement dans Skype Entreprise Server.
    

