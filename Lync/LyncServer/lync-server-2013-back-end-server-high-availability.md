---
title: 'Lync Server 2013 : Haute disponibilité des serveurs principaux'
TOCTitle: aute disponibilité des serveurs principaux
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205248(v=OCS.15)
ms:contentKeyID: 49298804
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Haute disponibilité des serveurs principaux dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-08-12_

Pour assurer une haute disponibilité pour vos serveurs principaux, vous pouvez utiliser la mise en miroir SQL synchrone ou le clustering SQL. L’utilisation d’une de ces solutions est facultative mais est recommandée pour préserver la continuité des activités de votre organisation. La mise en miroir SQL asynchrone n’est pas prise en charge pour la haute disponibilité des serveurs principaux dans Lync Server 2013. Dans le reste du document, sauf mention explicite, la mise en miroir SQL sous-entend une mise en miroir SQL synchrone.

Vous pouvez facilement configurer la mise en miroir SQL avec le Générateur de topologie. Pour le clustering SQL avec basculement, vous devez utiliser SQL Server pour la configuration.

Si vous utilisez la mise en miroir SQL ou le clustering SQL dans un pool couplé à un autre pool frontal pour la récupération d’urgence, vous devez utilisez la même solution de haute disponibilité principale dans les deux pools. Vous ne devez pas coupler un pool qui utilise la mise en miroir SQL avec un pool qui utilise le clustering SQL.

Si vous déployez la mise en miroir SQL, toutes les bases de données Lync Server du pool sont mises en miroir, y compris le magasin central de gestion s’il se trouve dans le pool, mais aussi les bases de données de l’application Response Group et de l’application Parcage d’appel si ces applications s’exécutent aussi dans le pool.

La mise en miroir SQL vous permet de ne pas avoir à utiliser de stockage partagé pour les serveurs. Chaque serveur garde sa copie des bases de données en local.

Vous pouvez déployer la mise en miroir SQL avec ou sans témoin. Cela dit, nous vous recommandons d’en utiliser un, car il permet le basculement automatique du serveur principal. Dans le cas contraire, un administrateur doit appeler le basculement manuellement. Notez que même si un témoin est déployé, un administrateur peut au besoin appeler manuellement le basculement du serveur principal.

Si vous utilisez un témoin, celui-ci peut servir pour plusieurs paires de serveurs principaux. Il n’y a aucune correspondance stricte un-à-un entre les témoins et les paires de serveurs principaux. Les déploiements utilisant un seul témoin pour plusieurs paires de serveurs principaux ne sont simplement pas aussi résilients que les topologies faisant appel à un témoin à part pour chaque paire de serveurs principaux.

Pour plus d’informations sur la prise en charge du clustering SQL, reportez-vous à [Prise en charge du logiciel de base de données dans Lync Server 2013](lync-server-2013-database-software-support.md). Pour plus d’informations sur le déploiement du clustering SQL, reportez-vous à [Configurer le clustering SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).

## Temps de récupération pour le basculement automatique de serveur principal avec la mise en miroir SQL

Pour le basculement automatique de serveur principal avec la mise en miroir SQL, la cible d’ingénierie pour la durée maximale d’interruption admissible (RTO, Recovery Time Objective) est de 5 minutes. Par l’usage de la mise en miroir SQL synchrone, nous ne prévoyons pas de perte de données en cas de panne du serveur principal sauf dans de rares cas où les serveurs frontaux et le serveur principal s’arrêtent de fonctionner en même temps pendant un transfert de données entre les serveurs. La cible d’ingénierie pour la perte de données maximale admissible (RPO, Recovery Point Objective) est de 5 minutes.

## Expérience utilisateur en cas de panne du serveur principal avec la mise en miroir SQL

L’expérience utilisateur en cas de panne dépend de la nature de la panne et de votre topologie.

Si vous utilisez la mise en miroir SQL et avez configuré un témoin et qu’une panne se produit au niveau du serveur principal, le basculement du serveur principal se fait automatiquement et rapidement. Les utilisateurs actifs ne devraient pas remarquer d’interruption particulière de leurs sessions actives.

Si aucun témoin n’est configuré, l’administrateur peut perdre du temps à appeler manuellement le basculement. Pendant ce temps, les utilisateurs actifs peuvent s’en trouver affectés. Leurs sessions se poursuivent normalement pendant environ 30 minutes. Si le serveur principal n’est toujours pas restauré ou si un administrateur n’a pas effectué le basculement sur le serveur de secours, le mode de résistance s’active alors pour les utilisateurs, c’est-à-dire qu’ils ne peuvent pas effectuer de tâches nécessitant un changement permanent dans Lync Server (par exemple, l’ajout d’un contact).

Si le serveur principal et les serveurs principaux en miroir tombent en panne, ou si l’un de ces derniers serveurs et le témoin tombent en panne, le serveur principal n’est alors plus disponible (même s’il fonctionne toujours). Dans ce cas, le mode de résistance s’active pour les utilisateurs actifs après une certaine durée.

