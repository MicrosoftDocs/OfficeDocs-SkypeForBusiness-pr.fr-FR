---
title: Configuration de l’intégrité dans Lync Server 2013
TOCTitle: Configuration de l’intégrité dans Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205234(v=OCS.15)
ms:contentKeyID: 49298711
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de l’intégrité dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Entre les divers sites web, articles de la Base de connaissances Microsoft et outils du Kit de ressources Lync Server qui sont mis à leur disposition, les administrateurs peuvent en principe résoudre rapidement les problèmes qu’ils peuvent rencontrer lors de l’utilisation de Lync Server.

Nous ne pouvons pas objectivement garantir que vous ne serez jamais confronté à aucun problème avec Lync Server 2013 dans la mesure où le fonctionnement de Lync Server peut être altéré par de nombreux facteurs (tels que des pannes réseau ou des défaillances matérielles) qui ne dépendent pas directement du produit. En implémentant la fonctionnalité d’analyse du fonctionnement, les administrateurs peuvent identifier les problèmes potentiels avant que les problèmes ne surviennent réellement. Les administrateurs utiliseront notamment l’analyse de Lync Server pour identifier les tendances et les évolutions : s’ils constatent, par exemple, une hausse régulière du nombre de conférences audio/vidéo, ils sauront qu’il est temps d’augmenter la capacité pour éviter une surcharge du système.

De façon similaire, les administrateurs peuvent utiliser System Center Operations Manager pour effectuer d’autres tâches, comme afficher des alertes en temps réel lorsque des événements particuliers se produisent ou exécuter des transactions synthétiques pour tester le système proactivement. Dans Lync Server, les transactions synthétiques permettent de vérifier que les utilisateurs ont la possibilité de réaliser des tâches courantes, telles que se connecter au système, envoyer et recevoir des messages instantanés, ou passer des appels vers un téléphone du réseau téléphonique commuté (RTC). En procédant périodiquement à ces tests, vous pourrez détecter en amont les problèmes que les utilisateurs sont susceptibles de rencontrer, par exemple, lorsqu’ils se connectent à Lync Server, et résoudre ces problèmes avant que votre équipe de support ne reçoive quantité d’appels d’utilisateurs se plaignant de ne pas réussir à se connecter. En exécutant ces transactions synthétiques à l’aide de System Center Operations Manager, les administrateurs peuvent assurer un contrôle régulier et permanent de leur déploiement de Lync Server, leur travail se limitant à traiter les éventuelles alertes émises.

> [!NOTE]  
> Pour Lync Server 2013, le pack d’administration de System Center Operations Manager peut détecter des problèmes « externes » susceptibles d’avoir un impact sur le fonctionnement de Lync Server. Par exemple, les administrateurs peuvent être avertis si les services Internet (IIS) sont mis hors connexion, si les ressources système disponibles sur l’ordinateur Lync Server sont en deçà de la quantité spécifiée ou si un ordinateur Lync Server rencontre une défaillance matérielle.

Dans Lync Server 2013, la configuration d’analyse est basée sur System Center Operations Manager et sur l’utilisation des packs d’administration de Lync Server. Ces packs d’administration offrent un ensemble de nouvelles fonctionnalités et d’améliorations, détaillées ci-dessous :

  - **Disponibilité des scénarios à partir de n’importe quel emplacement.** Le pack d’administration de Lync Server 2010 avait introduit le concept d’analyse de la disponibilité des scénarios utilisateur avec des transactions synthétiques. Dans Lync Server 2013, ces agents comportent de nouvelles transactions synthétiques qui peuvent être exécutées depuis divers emplacements dans l’entreprise, des emplacements géographiques distants en dehors de l’entreprise, dans des déploiements d’équipements en filiale et dans des déploiements de Lync Server 2010, dans le but d’améliorer la prise en charge des déploiements Edge hérités.

  - **Journaux des transactions synthétiques.** Lorsqu’une transaction synthétique échoue, les administrateurs peuvent examiner les journaux HTML pour essayer de déterminer la cause de l’échec. Ces journaux fournissent les informations suivantes : l’action qui a échoué, la latence de chaque action, la ligne de commande à partir de laquelle a été exécuté le test ainsi que l’erreur rencontrée.

  - **Meilleure couverture de la fiabilité des appels.** La fonctionnalité d’alerte de la fiabilité des appels, introduite dans le pack d’administration de Lync Server 2010, permet de détecter les problèmes de connectivité majeurs affectant les appels audio passés par les utilisateurs. Les packs d’administration de Lync Server 2013 améliorent la couverture de la messagerie instantanée d’égal à égal et d’autres fonctionnalités de conférence de base pour offrir une couverture maximale tout en réduisant les bruits parasites.

  - **Analyse des dépendances.** Les scénarios Lync Server peuvent échouer en raison de divers facteurs externes, tels que la mise hors connexion des services IIS, une insuffisance des ressources processeur et mémoire, ou des problèmes de disque. Les nouveaux packs d’administration vérifient plusieurs dépendances critiques et avertissent les administrateurs de leur impact potentiel.

  - **Rapports enrichis.** Les administrateurs disposent d’un ensemble de rapports qui les aideront à évaluer la disponibilité des scénarios, à planifier la capacité requise et à identifier les composants à l’origine des principaux problèmes.

Les packs d’administration contiennent également plusieurs fonctionnalités permettant aux administrateurs de détecter et diagnostiquer plus rapidement les problèmes, et d’avoir une analyse en temps réel du fonctionnement de leur déploiement de Lync Server. Ces fonctionnalités sont répertoriées dans le tableau suivant.

### Fonctionnalités des packs d’administration

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
<td><p>Applets de commande Windows PowerShell qui peuvent être exécutées à partir de différents emplacements pour vérifier la disponibilité immédiate des scénarios utilisateur, tels que la connexion, la présence, la messagerie instantanée et la conférence.</p></td>
</tr>
<tr class="even">
<td><p>Alertes de fiabilité des appels</p></td>
<td><p>Requêtes de base de données pour l’enregistrement des détails des appels. Ces enregistrements écrits par les serveurs frontaux indiquent si les utilisateurs ont réussi à effectuer un appel ou, en cas d’échec d’un appel, la raison. Ces requêtes donnent lieu à des alertes qui s’affichent lorsque de nombreux utilisateurs rencontrent des problèmes de connectivité liés à des appels d’égal à égal ou à des fonctionnalités de conférence de base.</p></td>
</tr>
<tr class="odd">
<td><p>Alertes de qualité des médias</p></td>
<td><p>Requêtes de base de données qui analysent les rapports QoE publiés par les clients à la fin de chaque appel. Ces requêtes affichent des alertes qui avertissent que les utilisateurs des scénarios signalés risquent d’être confrontés à une dégradation de la qualité des médias lors des appels et des conférences. Les données sont établies à partir de mesures clés, telles que la latence et la perte de paquets, qui s’avèrent décisives pour le niveau de qualité des appels.</p></td>
</tr>
<tr class="even">
<td><p>Intégrité des composants</p></td>
<td><p>Les composants serveur déclenchent des alertes d’après les données des journaux d’événements et des compteurs de performances. Ces alertes signalent les conditions d’échec qui peuvent avoir un impact sérieux sur un ou plusieurs scénarios utilisateur. Elles peuvent également indiquer diverses autres conditions d’échec, parmi lesquelles l’arrêt de services, des taux d’échec élevés ou des problèmes de connectivité.</p></td>
</tr>
<tr class="odd">
<td><p>Intégrité des dépendances</p></td>
<td><p>Divers facteurs externes peuvent expliquer les échecs. Les nouveaux packs d’administration analysent et collectent les données relatives à certaines dépendances externes critiques qui peuvent indiquer des problèmes majeurs, concernant notamment la disponibilité des services IIS, l’utilisation du processeur et de la mémoire par les serveurs et les processus, ainsi que les mesures de disque.</p></td>
</tr>
</tbody>
</table>


Les alertes affichées par le système se classent en trois catégories générales :

  - **Alertes de haute priorité.** Ces alertes signalent des conditions qui occasionneront des interruptions de service pour un grand nombre d’utilisateurs. Par exemple, l’échec d’un composant sur un seul ordinateur ne donne pas lieu à une alerte de haute priorité, car Lync Server 2013 intègre des fonctionnalités de haute disponibilité. Les alertes de haute priorité concernent des problèmes suffisamment sérieux pour inquiéter les administrateurs. Les pannes détectées par les transactions synthétiques ainsi que les services hors connexion (tels que la conférence audio/vidéo) font figure d’alertes de haute priorité.

  - **Alertes de priorité moyenne.** Ces alertes signalent des conditions qui ont un impact sur un groupe d’utilisateurs ou elles indiquent une dégradation de la qualité des appels. Les problèmes détectés par ces alertes peuvent être des pannes de composants, une latence d’établissement des appels ou une baisse de la qualité des appels audio. Les alertes de cette catégorie sont des alertes avec état qui indiquent l’état actuel du problème. À titre d’exemple, supposons que la durée d’établissement des appels dépasse actuellement le seuil d’alerte défini. Si cette durée revient à des valeurs normales, ces alertes sont résolues automatiquement dans System Center Operations Manager. Le système part du principe que ces alertes seront examinées dans la journée par un administrateur.

  - **Autres alertes.** Il s’agit des alertes qui concernent des composants susceptibles d’avoir un impact sur un ou plusieurs utilisateurs. Par exemple, l’alerte peut signaler que le service de carnet d’adresses n’a pas pu analyser l’entrée Active Directory d’un utilisateur spécifique. Le système part du principe que ces alertes seront examinées lorsqu’un administrateur aura le temps.

## Dans cette section

  - [Configuration de Lync Server pour le fonctionnement avec System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Utilisation de la journalisation enrichie pour les transactions synthétiques](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Utilisation de Microsoft SQL Server 2008 R2 comme base de données System Center Operations Manager](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

