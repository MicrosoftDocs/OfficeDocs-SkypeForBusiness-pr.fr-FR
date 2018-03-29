---
title: Activation des utilisateurs pour E9-1-1 dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Décisions nécessaires pour la stratégie de l’emplacement d’un déploiement E9-1-1 dans Skype de Voix Entreprise Server Business, y compris les utilisateurs à activer et à la prise en charge des utilisateurs itinérants.
ms.openlocfilehash: 966344f2cfc7a964c9dda0898b4ba99c42e03193
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server-2015"></a>Activation des utilisateurs pour E9-1-1 dans Skype Entreprise Server 2015
 
Décisions nécessaires pour la stratégie de l’emplacement d’un déploiement E9-1-1 dans Skype de Voix Entreprise Server Business, y compris les utilisateurs à activer et à la prise en charge des utilisateurs itinérants.
  
Lors de l’inscription du client, Skype pour Business Server utilise une stratégie d’emplacement pour configurer les propriétés E9-1-1 pour les utilisateurs disposant d’une Voix Entreprise. Cette stratégie contient les paramètres qui définissent le mode d’implémentation de E9-1-1. Par exemple, la stratégie d’emplacement contient des informations telles que la chaîne de numérotation et de secours ou non un utilisateur est tenu d’entrer manuellement un emplacement si le service d’informations d’emplacement n’est pas automatiquement à en fournir une. Pour une définition complète d’une stratégie d’emplacement, voir [planifier des stratégies d’emplacement pour Skype pour Business Server 2015](location-policies.md).
  
Skype pour Business Server peut affecter une stratégie emplacement aux clients basés sur un sous-réseau ou à des utilisateurs basées sur global, par site, ou la stratégie de l’utilisateur. Pour vous aider à prendre une décision quant au mode d’activation des utilisateurs, commencez par répondre aux questions suivantes.
  
 **Envisagez-vous d’activer tous les utilisateurs ou de limiter la prise en charge à des zones géographiques spécifiques de l’entreprise ?**
  
> Vous pouvez affecter un emplacement à tous les utilisateurs de votre entreprise à l’aide d’une stratégie d’emplacement globale. Toutefois, par l’affectation d’une stratégie de l’emplacement d’un Skype pour un site de réseau de serveur d’entreprise, puis ajouter des sous-réseaux au site, vous pouvez limiter la prise en charge de E9-1-1 pour les emplacements sélectionnés au sein de l’entreprise et spécifier le comportement de routage E9-1-1 sur une base site par site. 
    
 **Envisagez-vous d’activer des utilisateurs individuels par le biais d’une stratégie utilisateur ?**
  
> Vous pouvez affecter directement des stratégies d’emplacement à des utilisateurs ou des objets contact de téléphone de partie commune spécifiques si vous voulez personnaliser leur prise en charge du service E-9-1-1.
    
 **Quand des clients se trouvent en dehors du réseau ou se connectent à partir d’un sous-réseau non défini, doivent-ils bénéficier du service E9-1-1 ?**
  
> Si les utilisateurs sont affectés à une commande globale, de site, ou de la stratégie d’emplacement par utilisateur, ils peuvent être requis pour entrer manuellement un emplacement dans le client si le client n’est pas situé dans un sous-réseau défini ou si aucun emplacement n’a été trouvée par le service d’informations d’emplacement. Pour plus d’informations, consultez [définir l’expérience utilisateur pour l’acquisition d’un emplacement dans Skype pour Business Server 2015 manuellement](manually-acquiring-a-location.md).
    

