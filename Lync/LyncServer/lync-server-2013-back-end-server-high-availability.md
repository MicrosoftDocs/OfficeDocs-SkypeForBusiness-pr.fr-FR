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
ms.openlocfilehash: 5708212aa2eb30cfcc3c3d40894ca2340475bd8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a>Haute disponibilité du serveur principal dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-08-12_

Pour garantir la disponibilité de votre serveur principal, vous pouvez utiliser la mise en miroir SQL synchrone ou le regroupement SQL. Vous pouvez utiliser l’une de ces solutions en option, mais nous vous recommandons de préserver la continuité d’activité de votre organisation. La mise en miroir SQL asynchrone n’est pas prise en charge pour la haute disponibilité du serveur principal dans Lync Server 2013. Dans le reste de ce document, la mise en miroir SQL désigne la mise en miroir SQL synchrone, sauf mention contraire explicite.

Vous pouvez facilement configurer la mise en miroir SQL avec le générateur de topologie. Pour le clustering SQL avec basculement, vous devez utiliser SQL Server pour la configuration.

Si vous utilisez la mise en miroir SQL ou le regroupement SQL dans un pool qui est associé à un autre pool frontal pour la récupération après sinistre, vous devez utiliser la même solution de haute disponibilité back-end dans les deux pools. Vous ne devez pas associer un pool à l’aide de la mise en miroir SQL avec un pool utilisant le regroupement SQL.

Lorsque vous déployez la mise en miroir SQL, toutes les bases de données du serveur Lync dans le pool sont mises en miroir, y compris la Banque centrale de gestion, si elles se trouvent dans ce pool, ainsi que la base de données d’application du groupe de réponse et la base de données d’application du parc d’appels, si ces applications s’exécutent dans la liste.

Avec la mise en miroir SQL, vous n’avez pas besoin d’utiliser le stockage partagé pour les serveurs. Chaque serveur garde sa copie des bases de données en local.

Vous pouvez choisir de déployer la mise en miroir SQL avec ou sans témoin. Cela dit, nous vous recommandons d’en utiliser un, car il permet le basculement automatique du serveur principal. Dans le cas contraire, un administrateur doit appeler le basculement manuellement. Notez que même si un témoin est déployé, un administrateur peut au besoin appeler manuellement le basculement du serveur principal.

Si vous utilisez un témoin, celui-ci peut servir pour plusieurs paires de serveurs principaux. Il n’y a aucune correspondance stricte un-à-un entre les témoins et les paires de serveurs principaux. Les déploiements utilisant un seul témoin pour plusieurs paires de serveurs principaux ne sont simplement pas aussi résilients que les topologies faisant appel à un témoin à part pour chaque paire de serveurs principaux.

Pour plus d’informations sur la prise en charge des clusters SQL, voir [prise en charge de logiciels de base de données dans Lync Server 2013](lync-server-2013-database-software-support.md). Pour plus d’informations sur le déploiement de clusters SQL, voir [configurer le regroupement SQL Server pour Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>Temps de récupération pour le basculement automatique du serveur principal avec la mise en miroir SQL

Pour le basculement de bout en bout automatique avec la mise en miroir SQL, l’objectif d’ingénierie pour le temps de récupération (RTO) est de 5 minutes. En raison de la mise en miroir SQL synchrone, nous ne prévoyons pas la perte de données en cas d’échec du serveur principal, sauf dans de rares cas où les données sont déplacées sur les serveurs. La cible d’ingénierie pour la perte de données maximale admissible (RPO, Recovery Point Objective) est de 5 minutes.

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>Utilisation de l’interface utilisateur lors de l’échec du serveur principal avec la mise en miroir SQL

L’expérience utilisateur en cas de panne dépend de la nature de la panne et de votre topologie.

Si vous utilisez la mise en miroir SQL et que vous avez configuré un témoin, le basculement du serveur principal se produit automatiquement et rapidement. Les utilisateurs actifs ne devraient pas remarquer d’interruption particulière de leurs sessions actives.

Si aucun témoin n’est configuré, l’administrateur peut perdre du temps à appeler manuellement le basculement. Pendant ce temps, les utilisateurs actifs peuvent s’en trouver affectés. Leurs sessions se poursuivent normalement pendant environ 30 minutes. Si le serveur principal n’est toujours pas restauré ou s’il n’a pas pu basculer vers la sauvegarde, les utilisateurs sont basculés vers le mode de résilience, ce qui signifie qu’ils ne sont pas en mesure d’effectuer des tâches nécessitant un changement permanent sur le serveur Lync (par exemple, ajouter un contact).

Si le serveur principal et les serveurs principaux en miroir tombent en panne, ou si l’un de ces derniers serveurs et le témoin tombent en panne, le serveur principal n’est alors plus disponible (même s’il fonctionne toujours). Dans ce cas, le mode de résistance s’active pour les utilisateurs actifs après une certaine durée.

</div>

</div>

<span> </span>

</div>

</div>

</div>

