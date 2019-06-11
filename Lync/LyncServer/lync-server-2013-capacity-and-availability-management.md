---
title: 'Lync Server 2013: gestion des capacités et de la disponibilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 923dd7a4133da52a68e4d66ee6d5c7c47e7c0421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a>Gestion de la capacité et de la disponibilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-08-18_

L’objectif de la gestion de la capacité et de la gestion de la disponibilité est de mesurer et de contrôler les performances du système. Nous vous recommandons de mettre en œuvre des procédures de gestion de la capacité et de gestion de la disponibilité pour pouvoir mesurer et contrôler les performances du système. Vous devez savoir si le système est disponible et s’il peut gérer les demandes actuelles et projetées en définissant des plannings de référence et en analysant le système pour trouver des tendances.

<div>

## <a name="capacity-management"></a>Gestion de la capacité

La gestion de la capacité implique la planification, le dimensionnement et la gestion de la capacité de service pour garantir que les niveaux de performance minimum spécifiés dans votre SLA soient dépassés. La gestion de la capacité est un bon moyen de garantir que vous pouvez fournir des services informatiques à un tarif raisonnable tout en respectant les niveaux de performance définis dans les SLA avec le client. Ces critères peuvent être les suivants:

  - **Temps de réponse système**   il s’agit de la durée mesurée que le système exécute pour effectuer des actions courantes. Par exemple, le temps nécessaire au rôle du serveur audio/vidéo pour le traitement du trafic audio et vidéo, le temps nécessaire à un client pour la création et la participation à une conférence, ou le temps nécessaire pour la mise à jour de la présence dans tous les clients FileSystemWatcher.

  - **Capacité de stockage**   il s’agit de la capacité d’un système de stockage, qu’il s’agisse d’une base de données de contenu, d’un périphérique de sauvegarde ou d’un disque local. Par exemple, vous pouvez inclure le volume maximal d’espace de stockage par site, ainsi que l’heure de stockage des copies de sauvegarde avant leur remplacement.

La modification de la capacité est souvent le cas pour garantir la disponibilité de ressources physiques suffisantes, telles que l’espace disque et la bande passante réseau. Le tableau suivant répertorie les résolutions typiques des problèmes liés à la capacité.

### <a name="typical-resolutions-for-capacity-related-issues"></a>Résolution standard pour les problèmes liés à la capacité

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Problème</th>
<th>Résolution possible</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateurs distants ayant des performances audio/vidéo médiocres</p></td>
<td><p>Vérifiez si la bande passante appropriée est disponible sur les liaisons WAN et si la QoS est activée et configurée correctement. Vérifiez les données QoE.</p></td>
</tr>
<tr class="even">
<td><p>La réponse globale de l’environnement Lync est lente.</p></td>
<td><p>Exécutez des tests pour vérifier que les serveurs frontaux existants peuvent gérer le chargement. Introduisez un nouveau serveur frontal le cas échéant. Vérifiez les temps de réponse de la base de données SQL et résolvez les causes des retards (par exemple, amélioration du disque e/s).</p></td>
</tr>
</tbody>
</table>


Pour plus d’informations, reportez-vous à la section Guide de mise en réseau de Lync Server.

La capacité est affectée par la configuration du système et dépend des ressources physiques telles que la bande passante réseau. Par exemple, si un environnement Lync est configuré pour effectuer une sauvegarde complète nocturne, il est nécessaire de veiller à ce qu’il soit possible de réduire l’impact sur les performances interactives de l’utilisateur final.

La gestion de la capacité est le processus de conservation de la capacité d’un système dans des niveaux acceptables et répond aux problèmes suivants:

  - **La réaction aux modifications des exigences de capacité requise**   doit être ajustée pour tenir compte des modifications apportées au système ou à l’organisation. Par exemple, si votre environnement décide de mettre en place une voix entreprise, le nombre et l’emplacement des passerelles de réseau téléphonique commuté (PSTN) et du réseau public commuté (RTC) seront très importants. Si vous enverrez le trunking SIP (Session Initiation Protocol) ou le SIP direct, le design global sera considérablement modifié pour offrir les meilleures performances vocales pour l’entreprise.

  - **Prévoir les exigences**   futures les exigences en matière de capacités évoluent dans le temps. En effectuant le suivi des tendances, vous pouvez planifier des mises à jour à l’avance. Par exemple, la bande passante disponible entre divers sites Lync doit être contrôlée pour créer un planning de référence. Ce planning de référence vous permettra d’augmenter la quantité de bande passante que vous devez ajouter à ces liens, car le nombre d’utilisateurs dans ces sites distants augmente avec le temps.

</div>

<div>

## <a name="availability-management"></a>Gestion de la disponibilité

La gestion de la disponibilité est le processus qui permet de garantir le bon respect de tout service informatique et d’offrir le niveau de service cohérent et fiable requis par le client. La gestion de la disponibilité implique de limiter la perte de services et de vérifier que l’action appropriée est effectuée en cas de perte de service. Dans un environnement Lync, vous voudrez peut-être savoir si le service voix entreprise est disponible, si les utilisateurs peuvent participer à des conférences planifiées, etc. Un SLA définit une fréquence et une durée acceptables d’arrêts et autorise des périodes lorsque le système n’est pas disponible pour la maintenance planifiée.

Si vous devez fournir des rapports à votre gestion concernant la disponibilité des systèmes, ou si vous avez des pénalités financières ou d’autres pénalités associées à des cibles de disponibilité manquantes, vous devez enregistrer les données de disponibilité. Même si vous n’avez pas cette configuration, il est conseillé de savoir au moins le nombre d’échecs d’un système pendant une période donnée. Par exemple, la disponibilité du système au cours des 12 derniers mois et le temps nécessaire à la récupération de chaque échec. Ces informations vous permettront de mesurer et d’améliorer l’efficacité de votre équipe en réponse à une panne système. Il peut également vous fournir des informations utiles en cas de litige.

Les mesures liées à la disponibilité sont les suivantes:

  - **Disponibilité**   en règle générale, il s’agit du temps d’accès d’un système ou d’un service par rapport au temps qu’il est fixé. Elle est généralement exprimée en pourcentage. (Il est possible que vous voyiez des références à «trois neuf» ou «cinq neuf». Celles-ci se réfèrent à la disponibilité de 99,9% ou 99,999%.)

  - **Fiabilité**   il s’agit d’une mesure du temps entre les échecs d’un système et est parfois exprimée en temps moyenne (ou moyenne) entre les échecs (MTBF).

  - **Temps de réparation**   il s’agit du temps nécessaire pour récupérer un service après une période d’indisponibilité et est souvent exprimé par le temps moyen de réparation (MTTR).

La disponibilité, la fiabilité et le temps de réparation sont liés comme suit:

**Disponibilité = (MTBF-MTTR)/MTBF**   (par exemple, si un serveur tombe sur une période de six mois et n’est pas disponible pendant une moyenne de 20 minutes, le temps de MTBF est d’au moins trois mois ou 90, et le MTTR est de 20 minutes. Par conséquent, la disponibilité = (90 jours – 20 minutes)/90 jours = 99,985%.

La gestion de la disponibilité est le processus de vérification de l’agrandissement et de la disponibilité de la disponibilité dans les paramètres définis dans les SLA. La gestion de la disponibilité comprend les processus suivants:

  - **Surveillance**     de l’analyse du temps et des services indisponibles.

  - **La création de rapports**   de disponibilité doit être fournie régulièrement aux équipes gestion, utilisateurs et opérations. Ce rapport doit mettre en évidence des tendances et identifier les domaines qui nécessitent une attention particulière. Le rapport doit résumer la conformité aux cibles définies dans les SLA.

  - **** Si la disponibilité ne correspond pas aux cibles définies dans les SLA ou lorsque la tendance est une disponibilité réduite, le processus de gestion de la disponibilité doit planifier les étapes de remédiation.    Cela devrait inclure le fait de travailler avec d’autres équipes responsables pour mettre en évidence les raisons des pannes et de planifier des actions de remédiation pour éviter toute réapparition des pannes.

Les mesures de capacité et de disponibilité sont des tâches répétées qui conviennent idéalement aux outils et scripts automatisés tels que Microsoft System Center Operations Manager (anciennement Microsoft Operations Manager), qui est abordé plus loin dans ce document.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Surveiller Lync Server 2013 avec System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

