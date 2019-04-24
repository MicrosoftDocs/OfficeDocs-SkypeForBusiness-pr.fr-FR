---
title: Activer les utilisateurs pour E9-1-1 dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Décisions nécessaires pour la stratégie d’emplacement pour un déploiement E9-1-1 dans Skype pour Business Server Enterprise Voice, y compris les utilisateurs à activer et comment prendre en charge des utilisateurs itinérants.
ms.openlocfilehash: 57a84d18bec0547f1179e62013c9b957afdd2c53
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206921"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Activer les utilisateurs pour E9-1-1 dans Skype pour Business Server
 
Décisions nécessaires pour la stratégie d’emplacement pour un déploiement E9-1-1 dans Skype pour Business Server Enterprise Voice, y compris les utilisateurs à activer et comment prendre en charge des utilisateurs itinérants.
  
Lors de l’inscription du client, Skype pour Business Server utilise une stratégie d’emplacement pour configurer les propriétés E9-1-1 pour les utilisateurs Enterprise Voice. Cette stratégie contient les paramètres qui définissent le mode d’implémentation E9-1-1. Par exemple, la stratégie d’emplacement contient des informations telles que la chaîne de numérotation et si un utilisateur est invité à entrer manuellement un emplacement si le service informations d’emplacement ne sont pas automatiquement en fournir un. Pour une définition complète d’une stratégie d’emplacement, voir [planifier des stratégies d’emplacement pour Skype pour Business Server](location-policies.md).
  
Skype pour Business Server peut affecter une stratégie d’emplacement aux clients en fonction de sous-réseau ou aux utilisateurs selon un global par site ou stratégie par utilisateur. Pour vous aider à prendre une décision quant au mode d’activation des utilisateurs, commencez par répondre aux questions suivantes.
  
 **Envisagez-vous d’activer tous les utilisateurs ou de limiter la prise en charge à des zones géographiques spécifiques de l’entreprise ?**
  
> Vous pouvez affecter un emplacement à tous les utilisateurs de votre entreprise à l’aide d’une stratégie d’emplacement globale. Toutefois, par l’affectation d’une stratégie d’emplacement à un Skype pour le site de réseau Business Server, puis ajouter des sous-réseaux au site, vous pouvez limiter la prise en charge E9-1-1 pour les emplacements sélectionnés au sein de l’entreprise et spécifier le comportement du routage E9-1-1 sur site par site. 
    
 **Envisagez-vous d’activer des utilisateurs individuels par le biais d’une stratégie utilisateur ?**
  
> Vous pouvez affecter directement des stratégies d’emplacement à des utilisateurs ou des objets contact de téléphone de partie commune spécifiques si vous voulez personnaliser leur prise en charge du service E-9-1-1.
    
 **Quand des clients se trouvent en dehors du réseau ou se connectent à partir d’un sous-réseau non défini, doivent-ils bénéficier du service E9-1-1 ?**
  
> Si les utilisateurs sont affectés global, site, ou de la stratégie d’emplacement par utilisateur, ils peuvent être requis pour entrer manuellement un emplacement dans le client, si le client n’est pas situé dans un sous-réseau défini ou si aucun emplacement n’a été trouvée par le service informations d’emplacement. Pour plus d’informations, voir [définir l’expérience utilisateur pour acquérir manuellement un emplacement dans Skype pour Business Server](manually-acquiring-a-location.md).
    

