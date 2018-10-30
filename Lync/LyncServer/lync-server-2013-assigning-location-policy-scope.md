---
title: 'Lync Server 2013 : Affectation de l’étendue de la stratégie d’emplacement'
TOCTitle: Affectation de l’étendue de la stratégie d’emplacement
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205360(v=OCS.15)
ms:contentKeyID: 49299156
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affectation de l’étendue de la stratégie d’emplacement dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-06-06_

Comme avec les autres stratégies Lync Server, les stratégies d’emplacement peuvent être affectées à différents niveaux de portée : global, site et utilisateur. Cependant, la portée des stratégies d’emplacement au niveau de l’utilisateur se comporte de manière légèrement différente des autres stratégies Lync Server. Non seulement les stratégies d’emplacement par utilisateur peuvent être appliquées à des objets de point de terminaison (tels que les objets contact Utilisateurs ou Téléphone de partie commune), mais elles peuvent aussi s’appliquer aux sites réseau Lync Server. Les sites réseau sont des regroupements de sous-réseaux clients associés à un emplacement géographique (mais pas nécessairement tous les sous-réseaux dans un site central ou un site de succursale). Tous les clients connectés aux sous-réseaux dans un site réseau utilisent automatiquement la stratégie d’emplacement affectée à ce site réseau. Dans les cas où une stratégie d’emplacement de niveau utilisateur est affectée à un utilisateur et à un site réseau, la stratégie d’emplacement de site réseau remplace les paramètres de stratégie par utilisateur.

Une stratégie d’emplacement est affectée à chaque site réseau. Différentes valeurs d’utilisations RTC, d’URI de notification et d’URI de conférence sont affectées à chaque stratégie.

> [!NOTE]  
> La raison associée à ce comportement d’étendue de stratégie particulière est que lorsqu’un utilisateur hébergé sur un pool dans un site de bureau visite un autre site et doit passer un appel d’urgence, les paramètres de routage d’appels E9-1-1 adaptés à ce réseau sont appliqués, indépendamment du pool ou du site auquel l’utilisateur est affecté.
