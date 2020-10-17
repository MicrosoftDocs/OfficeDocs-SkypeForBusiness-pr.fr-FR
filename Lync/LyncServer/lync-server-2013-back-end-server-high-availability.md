---
title: 'Lync Server 2013 : haute disponibilité du serveur principal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f5b2fe64b4f32a43ff1462ab27daef04694c99b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515751"
---
# <a name="back-end-server-high-availability-in-lync-server-2013"></a>Haute disponibilité des serveurs principaux dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-08-12_

Pour garantir la haute disponibilité de vos serveurs principaux, vous pouvez utiliser la mise en miroir SQL synchrone ou le clustering SQL. L’utilisation de l’une de ces solutions facultatives, mais est recommandée pour maintenir la continuité de l’activité de votre organisation. La mise en miroir SQL asynchrone n’est pas prise en charge pour la haute disponibilité des serveurs principaux dans Lync Server 2013. Dans le reste du document, sauf mention explicite, la mise en miroir SQL sous-entend une mise en miroir SQL synchrone.

Vous pouvez facilement configurer la mise en miroir SQL avec le générateur de topologie. Pour le clustering SQL avec basculement, vous devez utiliser SQL Server pour le programme d’installation.

Si vous utilisez la mise en miroir SQL ou le clustering SQL dans un pool qui est associé à un autre pool frontal pour la récupération d’urgence, vous devez utiliser la même solution de haute disponibilité principale dans les deux pools. Vous ne devez pas associer un pool à l’aide de la mise en miroir SQL avec un pool à l’aide du clustering SQL.

Lorsque vous déployez la mise en miroir SQL, toutes les bases de données Lync Server du pool sont mises en miroir, notamment le magasin central de gestion, s’il se trouve dans ce pool, ainsi que la base de données de l’application Response Group et la base de données de l’application de parcage d’appel, si ces applications sont en cours d’exécution dans le pool.

La mise en miroir SQL vous permet de ne pas avoir à utiliser de stockage partagé pour les serveurs. Chaque serveur garde sa copie des bases de données en local.

Vous pouvez déployer la mise en miroir SQL avec ou sans témoin. Ceci dit, nous vous recommandons d’en utiliser un, car il permet le basculement automatique du serveur principal. Dans le cas contraire, un administrateur doit appeler le basculement manuellement. Notez que même si un témoin est déployé, un administrateur peut au besoin appeler manuellement le basculement du serveur principal.

Si vous utilisez un témoin, celui-ci peut servir pour plusieurs paires de serveurs principaux. Il n’y a aucune correspondance stricte un-à-un entre les témoins et les paires de serveurs principaux. Les déploiements utilisant un seul témoin pour plusieurs paires de serveurs principaux ne sont simplement pas aussi résilients que les topologies faisant appel à un témoin à part pour chaque paire de serveurs principaux.

Pour plus d’informations sur la prise en charge du clustering SQL, reportez-vous [à Database Software support in Lync Server 2013](lync-server-2013-database-software-support.md). Pour plus d’informations sur le déploiement du clustering SQL, reportez-vous à [configurer le clustering SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>Temps de récupération pour le basculement automatique de serveur principal avec mise en miroir SQL

Pour le basculement automatique automatique avec mise en miroir SQL, le objectif d’ingénierie pour l’objectif de temps de récupération (RTO) est de 5 minutes. Par l’usage de la mise en miroir SQL synchrone, nous ne prévoyons pas de perte de données en cas de panne du serveur principal sauf dans de rares cas où les serveurs frontaux et le serveur principal s’arrêtent de fonctionner en même temps pendant un transfert de données entre les serveurs. La cible d’ingénierie pour la perte de données maximale admissible (RPO, Recovery Point Objective) est de 5 minutes.

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>Expérience utilisateur lors d’une défaillance du serveur principal avec la mise en miroir SQL

L’expérience utilisateur en cas de panne dépend de la nature de la panne et de votre topologie.

Si vous utilisez la mise en miroir SQL et qu’un témoin est configuré, et que le principal échoue, le basculement du serveur principal s’effectue automatiquement et rapidement. Les utilisateurs actifs ne devraient pas remarquer d’interruption particulière de leurs sessions actives.

Si aucun témoin n’est configuré, l’administrateur peut perdre du temps à appeler manuellement le basculement. Pendant ce temps, les utilisateurs actifs peuvent s’en trouver affectés. Leurs sessions se poursuivent normalement pendant environ 30 minutes. Si le serveur principal n’est toujours pas restauré, ou si un administrateur n’a pas basculé vers la sauvegarde, les utilisateurs sont basculés en mode résistance, ce qui signifie qu’ils ne peuvent pas effectuer des tâches nécessitant une modification permanente sur Lync Server (par exemple, l’ajout d’un contact).

Si le serveur principal et les serveurs principaux en miroir tombent en panne, ou si l’un de ces derniers serveurs et le témoin tombent en panne, le serveur principal n’est alors plus disponible (même s’il fonctionne toujours). Dans ce cas, le mode de résilience s’active pour les utilisateurs actifs après une certaine durée.

</div>

</div>

<span> </span>

</div>

</div>

</div>

