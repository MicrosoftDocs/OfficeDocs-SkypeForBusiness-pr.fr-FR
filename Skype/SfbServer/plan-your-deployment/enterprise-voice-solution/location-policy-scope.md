---
title: Affectation de l’étendue de la stratégie d’emplacement dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planification de stratégies d’emplacement pour un déploiement E9-1-1 dans Skype entreprise Server Voice.
ms.openlocfilehash: 3865db146676ed64da9422d2a8731e44451ec6ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802754"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Affectation de l’étendue de la stratégie d’emplacement dans Skype entreprise Server
 
Planification de stratégies d’emplacement pour un déploiement E9-1-1 dans Skype entreprise Server Voice.
  
Comme avec d’autres stratégies serveur Skype entreprise, des stratégies d’emplacement peuvent être affectées à plusieurs niveaux d’étendue : global, site et utilisateur. Toutefois, l’étendue des stratégies d’emplacement utilisateur se comporte de manière légèrement différente de celle des autres stratégies serveur Skype entreprise. Les stratégies d’emplacement par utilisateur ne peuvent pas seulement être appliquées aux objets de point de terminaison (par exemple, les utilisateurs et les objets de contact de zone commune), ils peuvent également être appliqués aux sites du réseau Skype entreprise Server. Les sites réseau sont des regroupements de sous-réseaux clients associés à un emplacement géographique (mais pas nécessairement tous les sous-réseaux dans un site central ou un site de succursale). Tous les clients connectés aux sous-réseaux dans un site réseau utilisent automatiquement la stratégie d’emplacement affectée à ce site réseau. Dans les cas où une stratégie d’emplacement de niveau utilisateur est affectée à un utilisateur et à un site réseau, la stratégie d’emplacement de site réseau remplace les paramètres de stratégie par utilisateur.
  
Une stratégie d’emplacement est affectée à chaque site réseau. Différentes valeurs d’utilisations PSTN, d’URI de notification et d’URI de conférence sont affectées à chaque stratégie.
  
> [!NOTE]
> La raison associée à ce comportement d’étendue de stratégie particulière est que lorsqu’un utilisateur hébergé sur un pool dans un site de bureau visite un autre site et doit passer un appel d’urgence, les paramètres de routage d’appels E9-1-1 adaptés à ce réseau sont appliqués, indépendamment du pool ou du site auquel l’utilisateur est affecté. 
  

