---
title: Affecter l’étendue de la stratégie d’emplacement dans Skype Entreprise Server
ms.reviewer: null
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
ms.custom: null
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planification des stratégies d’emplacement pour un déploiement E9-1-1 dans Skype Entreprise Server Voix Entreprise.
---

# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Affecter l’étendue de la stratégie d’emplacement dans Skype Entreprise Server
 
Planification des stratégies d’emplacement pour un déploiement E9-1-1 dans Skype Entreprise Server Voix Entreprise.
  
Comme avec d’Skype Entreprise Server, les stratégies d’emplacement peuvent être affectées à plusieurs niveaux d’étendue : global, site et utilisateur. Toutefois, l’étendue des stratégies d’emplacement au niveau de l’utilisateur se comporte un peu différemment des autres stratégies Skype Entreprise Server utilisateur. Non seulement les stratégies d’emplacement par utilisateur peuvent être appliquées aux objets de point de terminaison (tels que les objets contact Utilisateurs et zone commune Téléphone), mais elles peuvent également être appliquées à Skype Entreprise Server sites réseau. Les sites réseau sont des regroupements de sous-réseaux clients associés à un emplacement géographique (mais pas nécessairement tous les sous-réseaux dans un site central ou un site de succursale). Tous les clients connectés aux sous-réseaux dans un site réseau utilisent automatiquement la stratégie d’emplacement affectée à ce site réseau. Dans les cas où une stratégie d’emplacement de niveau utilisateur est affectée à un utilisateur et à un site réseau, la stratégie d’emplacement de site réseau remplace les paramètres de stratégie par utilisateur.
  
Une stratégie d’emplacement est affectée à chaque site réseau. Différentes valeurs d’utilisations PSTN, d’URI de notification et d’URI de conférence sont affectées à chaque stratégie.
  
> [!NOTE]
> La raison associée à ce comportement d’étendue de stratégie particulière est que lorsqu’un utilisateur hébergé sur un pool dans un site de bureau visite un autre site et doit passer un appel d’urgence, les paramètres de routage d’appels E9-1-1 adaptés à ce réseau sont appliqués, indépendamment du pool ou du site auquel l’utilisateur est affecté. 
  

