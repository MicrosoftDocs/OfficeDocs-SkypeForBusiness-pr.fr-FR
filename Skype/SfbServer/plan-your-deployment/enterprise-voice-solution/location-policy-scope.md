---
title: Affectation de l’étendue de la stratégie d’emplacement dans Skype Entreprise Server 2015
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
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planification de stratégies d’emplacement pour un déploiement E9-1-1 dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 472ca2e6382a92005476eb7ed7c6bcfb22e71f85
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="assign-location-policy-scope-in-skype-for-business-server-2015"></a>Affectation de l’étendue de la stratégie d’emplacement dans Skype Entreprise Server 2015
 
Planification de stratégies d’emplacement pour un déploiement E9-1-1 dans Skype pour Business Server Voix Entreprise.
  
Comme avec les autre Skype pour les stratégies de serveur d’entreprise, les stratégies de l’emplacement peuvent être attribuées à plusieurs niveaux de portée : global, site et l’utilisateur. Toutefois, la portée des stratégies de l’emplacement de niveau utilisateur comporte un peu différemment avec les autre Skype pour les stratégies de serveur d’entreprise. Non seulement les stratégies d’emplacement par utilisateur peuvent être appliqués aux objets de point de terminaison (par exemple, les utilisateurs et les objets de contact téléphone de zone commune), il peuvent également être appliquées à Skype pour les sites de réseau de serveur d’entreprise. Les sites réseau sont des regroupements de sous-réseaux clients associés à un emplacement géographique (mais pas nécessairement tous les sous-réseaux dans un site central ou un site de succursale). Tous les clients connectés aux sous-réseaux dans un site réseau utilisent automatiquement la stratégie d’emplacement affectée à ce site réseau. Dans les cas où une stratégie d’emplacement de niveau utilisateur est affectée à un utilisateur et à un site réseau, la stratégie d’emplacement de site réseau remplace les paramètres de stratégie par utilisateur.
  
Une stratégie d’emplacement est affectée à chaque site réseau. Différentes valeurs d’utilisations PSTN, d’URI de notification et d’URI de conférence sont affectées à chaque stratégie.
  
> [!NOTE]
> La raison associée à ce comportement d’étendue de stratégie particulière est que lorsqu’un utilisateur hébergé sur un pool dans un site de bureau visite un autre site et doit passer un appel d’urgence, les paramètres de routage d’appels E9-1-1 adaptés à ce réseau sont appliqués, indépendamment du pool ou du site auquel l’utilisateur est affecté. 
  

