---
title: Assigner l’étendue de stratégie d’emplacement dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planification des stratégies d’emplacement pour un déploiement E9-1-1 dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 26d621877a61f372a6f40d20f8253954e3d43e5d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966277"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Assigner l’étendue de stratégie d’emplacement dans Skype pour Business Server
 
Planification des stratégies d’emplacement pour un déploiement E9-1-1 dans Skype pour Business Server Enterprise Voice.
  
Avec les autres Skype pour les stratégies de serveur d’entreprise, les stratégies d’emplacement peuvent être affectées à plusieurs niveaux d’étendue : globale, site et utilisateur. Toutefois, l’étendue de stratégies d’emplacement de niveau utilisateur comporte un bit différemment avec d’autres Skype pour les stratégies de serveur d’entreprise. Non seulement les stratégies d’emplacement par utilisateur peuvent être appliqués aux objets de point de terminaison (tels que les utilisateurs et les objets contacts téléphone en zone commune), ils peuvent également s’appliquer à Skype pour les sites de réseau Business Server. Les sites réseau sont des regroupements de sous-réseaux clients associés à un emplacement géographique (mais pas nécessairement tous les sous-réseaux dans un site central ou un site de succursale). Tous les clients connectés aux sous-réseaux dans un site réseau utilisent automatiquement la stratégie d’emplacement affectée à ce site réseau. Dans les cas où une stratégie d’emplacement de niveau utilisateur est affectée à un utilisateur et à un site réseau, la stratégie d’emplacement de site réseau remplace les paramètres de stratégie par utilisateur.
  
Une stratégie d’emplacement est affectée à chaque site réseau. Différentes valeurs d’utilisations PSTN, d’URI de notification et d’URI de conférence sont affectées à chaque stratégie.
  
> [!NOTE]
> La raison associée à ce comportement d’étendue de stratégie particulière est que lorsqu’un utilisateur hébergé sur un pool dans un site de bureau visite un autre site et doit passer un appel d’urgence, les paramètres de routage d’appels E9-1-1 adaptés à ce réseau sont appliqués, indépendamment du pool ou du site auquel l’utilisateur est affecté. 
  

