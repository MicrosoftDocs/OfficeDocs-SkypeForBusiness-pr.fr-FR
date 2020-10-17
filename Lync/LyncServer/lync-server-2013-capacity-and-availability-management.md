---
title: 'Lync Server 2013 : gestion de la capacité et de la disponibilité'
description: 'Lync Server 2013 : gestion de la capacité et de la disponibilité.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d498649651f8cfbccc65f5b1b5f010025ac418e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565150"
---
# <a name="capacity-and-availability-management-in-lync-server-2013"></a>Gestion de la capacité et de la disponibilité dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-08-18_

L’objectif de la gestion de la capacité et de la gestion de la disponibilité est de mesurer et de contrôler les performances du système. Nous vous recommandons de mettre en œuvre les procédures de gestion de la capacité et de gestion de la capacité afin de pouvoir mesurer et contrôler les performances du système. Vous devez savoir si le système est disponible et s’il peut gérer les demandes actuelles et prévues en définissant des configurations de référence et en surveillant le système pour rechercher des tendances.

<div>

## <a name="capacity-management"></a>Gestion de la capacité

La gestion de la capacité implique la planification, le dimensionnement et le contrôle de la capacité de service afin de garantir que les niveaux de performances minimaux spécifiés dans votre contrat SLA sont dépassés. La gestion de la capacité permet de garantir que vous pouvez fournir des services informatiques à un coût raisonnable tout en respectant les niveaux de performances définis dans vos accords SLA avec le client. Ces critères peuvent être les suivants :

  - Temps de réponse du **système**     Il s’agit du temps mesuré que le système effectue pour effectuer des actions classiques. Les exemples incluent le temps nécessaire au rôle de serveur audio/vidéo pour traiter le trafic audio/vidéo, le temps nécessaire pour qu’un client crée et participe à une conférence, ou le temps nécessaire pour que la présence soit mise à jour dans tous les clients observateurs.

  - **Capacité**     de stockage Il s’agit de la capacité d’un système de stockage, qu’il s’agisse d’une base de données de contenu, d’une unité de sauvegarde ou d’un lecteur local. Par exemple, l’espace de stockage maximal doit être fourni par site et le temps de stockage des sauvegardes avant leur remplacement.

L’ajustement de la capacité est souvent un cas de s’assurer que suffisamment de ressources physiques sont disponibles, telles que l’espace disque et la bande passante réseau. Le tableau suivant répertorie les résolutions typiques des problèmes liés à la capacité.

### <a name="typical-resolutions-for-capacity-related-issues"></a>Résolutions typiques des problèmes liés à la capacité

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
<td><p>Utilisateurs distants présentant des performances audio/vidéo médiocres</p></td>
<td><p>Vérifiez si la bande passante appropriée est disponible sur les liaisons WAN et si la qualité de service (QoS) est activée et configurée correctement. Vérifier les données QoE.</p></td>
</tr>
<tr class="even">
<td><p>La réponse globale de l’environnement Lync est lente.</p></td>
<td><p>Exécutez des tests pour vérifier que les serveurs frontaux existants peuvent traiter la charge. Introduisez un nouveau serveur frontal si nécessaire. Vérifiez les temps de réponse de la base de données SQL et corrigez les causes de ces retards (par exemple, amélioration des e/s disque).</p></td>
</tr>
</tbody>
</table>


Le dépannage est plus détaillé dans le Guide de mise en réseau Lync Server.

La capacité est affectée par la configuration du système et dépend des ressources physiques telles que la bande passante réseau. Par exemple, si un environnement Lync est configuré pour effectuer une sauvegarde complète nocturne, il convient de s’assurer que l’impact sur les performances interactives prises en charge par les utilisateurs finaux est minimisé.

La gestion de la capacité est le processus qui consiste à maintenir la capacité d’un système dans des limites acceptables et à résoudre les problèmes suivants :

  - **Réaction aux modifications des exigences**     Les besoins en capacité doivent être ajustés pour tenir compte des modifications apportées au sein du système ou de l’organisation. Par exemple, si votre environnement décide d’implémenter voix entreprise, le nombre et l’emplacement des serveurs de médiation et des passerelles PSTN (réseau téléphonique commuté) sont très importants. Si vous effectuez une jonction SIP (Session Initiation Protocol) ou SIP direct, la conception globale sera considérablement modifiée afin de fournir les meilleures performances vocales de l’entreprise.

  - **Prévision des besoins futurs**     Certaines exigences en matière de capacité changent de manière prévisible au fil du temps. Le suivi des tendances vous permet de planifier les mises à niveau à l’avance. Par exemple, la bande passante disponible entre les différents sites Lync doit être surveillée pour créer une configuration de référence. Cette configuration de référence vous permettra de prévoir le moment où vous devez ajouter davantage de bande passante à ces liens, car le nombre d’utilisateurs dans ces sites distants augmente avec le temps.

</div>

<div>

## <a name="availability-management"></a>Gestion de la disponibilité

La gestion de la disponibilité est le processus qui consiste à garantir que tout service informatique se comporte de façon cohérente et rentable le niveau de service cohérent et fiable requis par le client. La gestion de la disponibilité s’occupe de minimiser la perte de service et de s’assurer que l’action appropriée est effectuée en cas de perte du service. Dans un environnement Lync, vous pouvez vous préoccuper de savoir si le service voix entreprise est disponible, si les utilisateurs peuvent participer à des conférences planifiées, etc. Un accord SLA définit une fréquence et une durée de panne acceptables et autorise certaines périodes lorsque le système n’est pas disponible pour une maintenance planifiée.

Si vous devez fournir des rapports à votre gestion sur la disponibilité des systèmes, ou si vous avez des pénalités financières ou d’autres pénalités associées à des objectifs de disponibilité manquants, vous devez enregistrer les données de disponibilité. Même si vous n’avez pas ces exigences formelles, il est judicieux de connaître au moins la fréquence à laquelle un système est tombé en panne pendant une période donnée. Par exemple, la disponibilité du système au cours des 12 derniers mois et la durée de la récupération à partir de chaque défaillance. Ces informations vous aideront à mesurer et à améliorer l’efficacité de votre équipe dans la réponse à une défaillance du système. Elle peut également vous fournir des informations utiles en cas de litige.

Les mesures liées à la disponibilité sont les suivantes :

  - **Disponibilité**     En règle générale, il s’agit du moment où un système ou un service est accessible par rapport à l’heure à laquelle il est inactif. Elle est généralement exprimée sous la forme d’un pourcentage. (Vous pouvez voir les références à « trois neufs » ou à « cinq neuf ». Ces éléments font référence à 99,9% ou 99,999% de disponibilité.)

  - **Fiabilité**     Il s’agit d’une mesure du temps entre les défaillances d’un système et est parfois exprimée en temps moyen (ou en moyenne) entre les défaillances (MTBF).

  - **Temps de réparation**     Il s’agit du temps nécessaire pour récupérer un service après une panne et est souvent exprimé en temps moyen de réparation (MTTR).

La disponibilité, la fiabilité et le temps de réparation sont liés comme suit :

**Disponibilité = (MTBF – MTTR)/MTBF**     Par exemple, si un serveur tombe en panne deux fois pendant une période de six mois et n’est pas disponible pendant une moyenne de 20 minutes, le MTBF est de trois mois ou de 90 jours et le MTTR est de 20 minutes. Par conséquent, la disponibilité = (90 jours – 20 minutes)/90 jours = 99,985%.

La gestion de la disponibilité est le processus qui consiste à s’assurer que la disponibilité est optimisée et conservée dans les paramètres définis dans SLA. La gestion de la disponibilité inclut les processus suivants :

  - **Surveillance**     Examen du délai et de la durée pendant laquelle les services ne sont pas disponibles.

  - **Création de rapports**     Les chiffres de disponibilité doivent être régulièrement fournis aux équipes de gestion, des utilisateurs et des opérations. Ces rapports doivent mettre en évidence des tendances et identifier les domaines qui nécessitent une attention particulière. Le rapport doit résumer la conformité aux objectifs définis dans les SLA.

  - **Amélioration**     Si la disponibilité ne répond pas aux objectifs définis dans les SLA ou lorsque la tendance est à réduire la disponibilité, le processus de gestion de la disponibilité doit planifier les étapes de réparation. Cela doit inclure la collaboration avec d’autres équipes responsables pour mettre en évidence les raisons des pannes et planifier des actions correctives afin d’éviter une réapparition des pannes.

Les mesures de capacité et de disponibilité sont des tâches répétitives qui conviennent parfaitement aux outils et scripts automatisés, tels que Microsoft System Center Operations Manager (anciennement Microsoft Operations Manager), qui est abordé plus loin dans ce document.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Surveillance de Lync Server 2013 avec System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

