---
title: 'Lync Server 2013: configuration d’intégrité dans Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a719a5e8695dbbd0705aa649d72a32a2bfdc7d38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a>Configuration de l’intégrité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-22_

Entre les différents sites Web, les Articles de la base de connaissances Microsoft et les outils du kit de ressources Lync Server, les administrateurs rencontrant des problèmes d’exécution de Lync Server ne sont jamais loin d’une solution pour résoudre ces problèmes.

Évidemment, il n’existe aucun moyen de garantir que vous ne rencontrerez jamais de problèmes avec Lync Server 2013, car Lync Server peut être touché par de nombreux éléments tels que le blocage du réseau et les défaillances matérielles, que le produit lui-même ne peut pas contrôler. En implémentant le contrôle d’intégrité, les administrateurs peuvent identifier les problèmes potentiels avant qu’ils ne deviennent des problèmes réels. Par exemple, les administrateurs peuvent utiliser le contrôle du serveur Lync pour identifier les tendances et tendances des. Par exemple, une augmentation constante du nombre de conférences audio/vidéo peut vous suggérer de devoir ajouter de la capacité avant que le système ne soit surchargé.

De la même façon, les administrateurs peuvent utiliser System Center Operations Manager pour effectuer les actions suivantes lors de l’exécution d’alertes en temps réel lors de l’exécution d’événements spécifiques et de l’exécution de transactions de synthèse qui testent activement le système. Les transactions synthétiques sont utilisées dans Lync Server pour vérifier que les utilisateurs sont en mesure de réaliser des tâches courantes, telles que la connexion au système, l’échange de messages instantanés ou l’appel d’appels vers un téléphone figurant sur le réseau téléphonique public commuté (RTC). Par exemple, l’exécution périodique de ces tests peut vous avertir en cas de problème avec les utilisateurs qui se connectent à Lync Server et vous permet de corriger le problème avant que votre équipe de support ne puisse se connecter. L’utilisation de System Center Operations Manager pour exécuter ces transactions synthétiques peut surveiller régulièrement le déploiement de Lync Server sur 24 heures sur 24 sans avoir à faire beaucoup de choses au-delà de répondre à des alertes qui pourraient être émis.

<div>


> [!NOTE]  
> Pour Lync Server 2013, le pack d’administration pour System Center Operations Manager est également capable de détecter les problèmes «externes» qui peuvent avoir un impact sur Lync Server. Par exemple, les administrateurs peuvent être avertis si Internet Information Services (IIS) se déconnecte, les ressources système sur un ordinateur Lync Server sont inférieures à un certain nombre de ressources ou un ordinateur serveur Lync rencontre une défaillance matérielle.



</div>

La configuration de l’intégrité de Lync Server 2013 est basée sur System Center Operations Manager et sur l’utilisation des packs de gestion de Lync Server. Les packs d’administration suivants incluent un certain nombre de nouvelles fonctionnalités et améliorations, notamment:

  - **Disponibilité des scénarios à partir de n’importe quel emplacement.** Le pack d’administration de Lync Server 2010 a présenté le concept de surveillance de la disponibilité des scénarios des utilisateurs finaux aux transactions synthétiques. Dans Lync Server 2013, ces agents ont plus de transactions synthétiques et peuvent être exécutés à partir de différents emplacements au sein de l’entreprise, d’emplacements géographiques distants en dehors de l’entreprise, d’appareils de succursale et de Lync Server 2010 les déploiements permettent d’ajouter une couverture aux déploiements de bords anciens.

  - **Journaux de transactions synthétiques.** En cas d’échec d’une transaction synthétique, les administrateurs ont accès aux journaux HTML pour vous aider à déterminer les échecs. Il s’agit notamment de savoir quelle action a échoué, la latence de chaque action, la ligne de commande utilisée pour exécuter le test et l’erreur rencontrée.

  - **Meilleure couverture de la fiabilité des appels.** Le pack d’administration de Lync Server 2010 a présenté une alerte de fiabilité des appels pour détecter des problèmes de connectivité importants qui affectent les appels audio des utilisateurs finaux. Les packs d’administration de Lync Server 2013 ajoutent une couverture pour la messagerie instantanée et d’autres fonctions de base pour la couverture tout en réduisant le bruit.

  - **Analyse des dépendances.** Les scénarios Lync Server peuvent échouer en raison d’un large éventail de facteurs externes tels que les services Internet (IIS) qui sont déconnectés, les ressources de mémoire et d’UC limitées, et les problèmes de disque. Les nouveaux packs de gestion vérifient plusieurs dépendances critiques pour s’assurer que les administrateurs connaissent leurs répercussions.

  - **Rapports améliorés.** Un ensemble de rapports permettant aux administrateurs d’évaluer la disponibilité des scénarios, de planifier la capacité et de voir quels composants rencontrent le plus de problèmes.

Les packs de gestion incluent également diverses fonctionnalités qui permettent de détecter et de diagnostiquer une visibilité en temps réel dans le déploiement de Lync Server. Ces fonctionnalités sont indiquées dans le tableau suivant.

### <a name="management-pack-features"></a>Fonctionnalités du pack d’administration

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Fonctionnalité</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Transactions synthétiques</p></td>
<td><p>Les applets de connexion Windows PowerShell peuvent être exécutées à partir de différents emplacements pour s’assurer que les scénarios utilisateur finaux tels que la connexion, la présence, la messagerie instantanée et les conférences sont facilement accessibles aux utilisateurs finaux.</p></td>
</tr>
<tr class="even">
<td><p>Alertes de fiabilité des appels</p></td>
<td><p>Requêtes de base de données pour les enregistrements des détails des appels (CDR). Ces enregistrements sont écrits par des serveurs frontaux pour indiquer si les utilisateurs finaux étaient en mesure de se connecter à un appel ou la fin d’un appel. Ces requêtes génèrent des alertes indiquant qu’un grand nombre d’utilisateurs finaux rencontrent des problèmes de connectivité pour les appels d’égal à égal ou les fonctionnalités de conférence de base.</p></td>
</tr>
<tr class="odd">
<td><p>Alertes de qualité multimédia</p></td>
<td><p>Requêtes de base de données qui observent les rapports de qualité d’expérimentation (QoE) publiés par les clients à la fin de chaque appel. Ces requêtes génèrent des alertes qui identifient les scénarios dans lesquels les utilisateurs risquent de rencontrer des problèmes de qualité de média lors des appels et des conférences. Les données sont bâties sur des indicateurs clés, comme la latence et la perte de paquets, des métriques connues pour contribuer directement à la qualité des appels.</p></td>
</tr>
<tr class="even">
<td><p>État du composant</p></td>
<td><p>Les composants serveur individuels déclenchent des alertes à l’aide de journaux d’événements et de compteurs de performance. Ces alertes indiquent des conditions d’échec qui peuvent avoir un impact important sur un ou plusieurs scénarios utilisateur finaux. Ces alertes peuvent également indiquer un grand nombre de conditions d’échec, y compris les services qui ne sont pas en cours d’exécution, les taux d’échec élevés, la latence des messages importants ou les problèmes de connectivité.</p></td>
</tr>
<tr class="odd">
<td><p>État de dépendance</p></td>
<td><p>Des échecs peuvent se produire pour diverses raisons externes. Les packs de gestion contrôlent et recueillent désormais des données pour certaines des dépendances externes critiques susceptibles d’indiquer des problèmes importants, y compris la disponibilité d’IIS, l’utilisation du processeur et de la mémoire de serveurs et de processus, et des métriques de disque.</p></td>
</tr>
</tbody>
</table>


Les alertes émises par le système sont classées en trois catégories générales:

  - **Alertes à priorité élevée.** Ces alertes indiquent des conditions qui engendreront des interruptions de service pour de grands groupes d’utilisateurs. Par exemple, une défaillance de composant sur un seul ordinateur n’est pas une alerte de priorité élevée, car Lync Server 2013 inclut des fonctionnalités de haute disponibilité intégrées. Au lieu de cela, les alertes de priorité élevée représentent des problèmes importants» pour réactiver les administrateurs de la journée.» Les pannes détectées par les transactions synthétiques et les services hors connexion (par exemple, les conférences audio/vidéo) sont éligibles en tant qu’alertes à priorité élevée.

  - **Alertes de priorité moyenne.**.. Ces alertes indiquent des conditions qui affectent un sous-ensemble d’utilisateurs ou indiquent la dégradation de la qualité d’appel. Cela inclut les problèmes tels que les défaillances de composant, la latence dans l’établissement d’appel ou la qualité audio détériorée lors d’un appel. Les alertes de cette catégorie sont avec état et indiquent l’état actuel du problème. Par exemple, supposons que la durée de votre établissement d’appel dépasse le seuil d’alerte. Si les heures d’établissement d’appel retournent à normal, ces alertes sont résolues automatiquement dans System Center Operations Manager. Le préversion de ces alertes est qu’un administrateur le verra sur la même journée de travail.

  - **Autres alertes.** Il s’agit d’alertes provenant de composants susceptibles d’affecter un utilisateur ou un sous-ensemble d’utilisateurs spécifiques. Par exemple, il est possible que le service de carnet d’adresses ne puisse pas analyser l’entrée Active Directory d’un utilisateur donné. L’attente de ces alertes est que les administrateurs y accrire lorsque le temps est disponible.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration de Lync Server 2013 pour fonctionner avec System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Utilisation de la journalisation détaillée pour les transactions synthétiques dans Lync Server 2013](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Utilisation de Microsoft SQL Server 2008 R2 en tant que base de données Gestionnaire d’opérations System Center pour Lync Server 2013](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

