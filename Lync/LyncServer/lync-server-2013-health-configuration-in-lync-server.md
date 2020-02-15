---
title: 'Lync Server 2013 : configuration de l’intégrité dans Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 831dd021799f658ae9ce332935ff2381e5d79bef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a>Configuration de l’intégrité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Entre différents sites Web, les Articles de la base de connaissances Microsoft et les outils du kit de ressources Lync Server, les administrateurs qui rencontrent des problèmes lors de l’exécution de Lync Server ne sont pas loin d’un moyen de résoudre ces problèmes.

Évidemment, il n’est pas possible de vous assurer que vous ne rencontrerez jamais de problèmes avec Lync Server 2013 car Lync Server peut être affecté par de nombreux éléments, tels que les pannes de réseau et les défaillances matérielles, que le produit lui-même ne peut pas contrôler. En implémentant la surveillance de l’intégrité, les administrateurs peuvent identifier les problèmes potentiels avant de se transformer en problèmes réels. Par exemple, les administrateurs peuvent utiliser la surveillance de Lync Server pour identifier des tendances et des Tendencies. Par exemple, une augmentation constante du nombre de conférences audio/vidéo peut suggérer de devoir ajouter de la capacité avant que le système ne soit surchargé.

De la même manière, les administrateurs peuvent utiliser System Center Operations Manager pour effectuer des alertes en temps réel lorsque des événements spécifiés se produisent, et pour exécuter des transactions synthétiques qui testent le système de manière proactive. Les transactions synthétiques sont utilisées dans Lync Server pour vérifier que les utilisateurs peuvent effectuer correctement des tâches courantes, telles que la connexion au système, l’échange de messages instantanés ou l’appel à un téléphone situé sur le réseau téléphonique commuté (RTC). Par exemple, l’exécution périodique de ces tests peut vous avertir en cas de problème avec les utilisateurs qui se connectent à Lync Server, et vous donner la possibilité de corriger le problème avant que votre équipe de support ne soit saturée d’appels provenant d’utilisateurs incapables d’établir une connexion. À l’aide de System Center Operations Manager pour exécuter ces transactions synthétiques, les administrateurs peuvent surveiller régulièrement leur déploiement de Lync Server en continu pendant 24 heures sur 24, sans avoir à effectuer une grande partie des alertes pouvant être émis.

<div>


> [!NOTE]  
> Pour Lync Server 2013, le pack d’administration de System Center Operations Manager peut également détecter les problèmes « externes » susceptibles d’avoir un impact négatif sur Lync Server. Par exemple, les administrateurs peuvent être avertis si les services Internet (IIS) se déconnectent, les ressources système sur un ordinateur Lync Server descendent en dessous d’une quantité spécifiée, ou un ordinateur Lync Server rencontre une défaillance matérielle.



</div>

La configuration de l’intégrité dans Lync Server 2013 est basée sur System Center Operations Manager et sur l’utilisation des packs d’administration Lync Server. Ces packs d’administration incluent un certain nombre de nouvelles fonctionnalités et d’améliorations, notamment :

  - **Disponibilité des scénarios à partir de n’importe quel emplacement.** Le pack d’administration Lync Server 2010 a introduit le concept de surveillance de la disponibilité des scénarios des utilisateurs finaux avec les transactions synthétiques. Dans Lync Server 2013, ces agents ont plus de transactions synthétiques et peuvent être exécutés à partir d’un grand nombre d’emplacements à l’intérieur de l’entreprise, à partir d’emplacements géographiques distants en dehors de l’entreprise, sur des appareils de succursale et sur Lync Server 2010 les déploiements pour ajouter la couverture aux déploiements de serveurs Edge hérités.

  - **Journaux de transactions synthétiques.** Lorsqu’une transaction synthétique échoue, les administrateurs ont accès aux journaux HTML afin de déterminer ce qui a échoué. Cela inclut la compréhension de l’action qui a échoué, de la latence de chaque action, de la ligne de commande utilisée pour exécuter le test et de l’erreur rencontrée.

  - **Couverture accrue des appels.** Le pack d’administration Lync Server 2010 a introduit les alertes de fiabilité des appels pour détecter les problèmes de connectivité graves affectant les appels audio des utilisateurs finaux. Les packs d’administration Lync Server 2013 ajoutent une couverture pour la messagerie instantanée d’égal à égal et d’autres fonctionnalités de conférence de base pour maximiser la couverture tout en réduisant le bruit.

  - **Surveillance des dépendances.** Les scénarios Lync Server peuvent échouer en raison d’un certain nombre de facteurs externes, tels que les services Internet (IIS) hors connexion, les ressources de mémoire et de processeur limitées, ainsi que les problèmes de disque. Les nouveaux packs d’administration vérifient plusieurs dépendances critiques afin de s’assurer que les administrateurs connaissent leur impact.

  - **Création de rapports améliorée.** Ensemble de rapports permettant aux administrateurs d’estimer la disponibilité des scénarios, de planifier la capacité et de voir les composants qui rencontrent le plus de problèmes.

Les packs d’administration incluent également un grand nombre de fonctionnalités pour vous aider à détecter et à diagnostiquer une visibilité en temps réel sur l’état de votre déploiement Lync Server. Ces fonctions sont répertoriées dans le tableau suivant.

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
<td><p>Applets de commande Windows PowerShell pouvant être exécutées à partir de différents emplacements afin de s’assurer que les scénarios d’utilisateur final, tels que la connexion, la présence, la messagerie instantanée et la Conférence, sont immédiatement disponibles pour les utilisateurs finaux.</p></td>
</tr>
<tr class="even">
<td><p>Alertes de fiabilité des appels</p></td>
<td><p>Requêtes de base de données pour les enregistrements des détails des appels (CDR). Ces enregistrements sont écrits par les serveurs frontaux pour indiquer si les utilisateurs finaux ont pu se connecter à un appel ou la raison de l’arrêt d’un appel. Ces requêtes génèrent des alertes qui indiquent quand un grand nombre d’utilisateurs finaux rencontrent des problèmes de connectivité pour les appels P2P ou les fonctionnalités de conférence de base.</p></td>
</tr>
<tr class="odd">
<td><p>Alertes de qualité des médias</p></td>
<td><p>Requêtes de base de données qui examinent les rapports de qualité de l’expérience publiés par les clients à la fin de chaque appel. Ces requêtes génèrent des alertes qui identifient les scénarios dans lesquels les utilisateurs sont susceptibles de rencontrer des problèmes de qualité des médias pendant les appels et les conférences. Les données sont basées sur des mesures clés, telles que la latence et la perte de paquets, qui sont connues pour contribuer directement à la qualité des appels.</p></td>
</tr>
<tr class="even">
<td><p>Intégrité des composants</p></td>
<td><p>Les composants serveur individuels déclenchent des alertes à l’aide de journaux d’événements et de compteurs de performance. Ces alertes indiquent des conditions d’échec qui peuvent sérieusement affecter un ou plusieurs scénarios d’utilisateur final. Ces alertes peuvent également indiquer diverses autres conditions d’échec, notamment les services non exécutés, les taux d’échec élevés, la latence de messages élevée ou des problèmes de connectivité.</p></td>
</tr>
<tr class="odd">
<td><p>Intégrité des dépendances</p></td>
<td><p>Des échecs peuvent se produire pour diverses raisons externes. Les packs d’administration surveillent et collectent des données pour certaines dépendances externes critiques susceptibles d’indiquer des problèmes sérieux, notamment la disponibilité des services Internet, l’utilisation du processeur et de la mémoire des serveurs et des processus, ainsi que les mesures de disque.</p></td>
</tr>
</tbody>
</table>


Les alertes émises par le système ont été classées en trois catégories générales :

  - **Alertes à priorité élevée.** Ces alertes indiquent les conditions qui provoquent des pannes de service pour des groupes d’utilisateurs importants. Par exemple, une défaillance de composant sur un seul ordinateur n’est pas une alerte de haute priorité, car Lync Server 2013 possède des fonctionnalités de haute disponibilité intégrées. Au lieu de cela, les alertes de haute priorité représentent des problèmes assez graves» pour réveiller les administrateurs la nuit. Les pannes détectées par les transactions synthétiques et les services hors ligne (par exemple, conférence audio/vidéo) sont considérées comme des alertes de haute priorité.

  - **Alertes de priorité moyenne.**. Ces alertes indiquent les conditions qui affectent un sous-ensemble d’utilisateurs ou indiquent une dégradation de la qualité des appels. Cela inclut des problèmes comme les défaillances de composants, la latence dans l’établissement d’appel ou la qualité audio dégradée dans l’appel. Les alertes de cette catégorie sont avec état et indiquent l’état actuel du problème. Par exemple, supposons que les heures d’établissement de votre appel dépassent le seuil d’alerte. Si les heures d’établissement d’appel reviennent à la normale, ces alertes seront résolues automatiquement dans System Center Operations Manager. L’attente de ces alertes est qu’un administrateur les consultera le même jour ouvré.

  - **Autres alertes.** Il s’agit d’alertes provenant de composants susceptibles d’affecter un utilisateur spécifique ou un sous-ensemble d’utilisateurs. Par exemple, le service de carnet d’adresses n’a peut-être pas pu analyser l’entrée Active Directory d’un utilisateur donné. L’attente de ces alertes est que les administrateurs y accéderont lorsqu’ils auront le temps de se rendre disponible.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration de Lync Server 2013 pour qu’il fonctionne avec System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Utilisation d’une journalisation enrichie pour les transactions synthétiques dans Lync Server 2013](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Utilisation de Microsoft SQL Server 2008 R2 comme base de données System Center Operations Manager pour Lync Server 2013](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

