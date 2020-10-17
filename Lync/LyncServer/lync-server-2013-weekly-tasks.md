---
title: 'Lync Server 2013 : tâches hebdomadaires'
description: 'Lync Server 2013 : tâches hebdomadaires.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d818e1140141a470bb57a1471bb04931f505a6bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546140"
---
# <a name="weekly-tasks-in-lync-server-2013"></a>Tâches hebdomadaires dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-08-17_

Les tâches hebdomadaires sont généralement liées à la collecte et à l’analyse des journaux et des rapports.

<div>

## <a name="archive-event-logs"></a>Archiver les journaux des événements

Si les journaux des événements ne sont pas configurés de manière à remplacer les événements au besoin, ils doivent être régulièrement archivés et supprimés. Cette action est particulièrement importante pour les journaux de sécurité, qui peuvent être requis dans le cadre de recherches concernant des tentatives de violation de la sécurité.

Votre organisation devra définir des stratégies et des procédures pour l’archivage des journaux.

</div>

<div>

## <a name="create-reports"></a>Créer des rapports

Créer des rapports d’État pour faciliter la planification de la capacité, les révisions SLA et l’analyse des performances. Utilisez les données quotidiennes du journal des événements et du moniteur système pour créer des rapports sur le disque, la mémoire et l’utilisation du processeur. Utilisez System Center Operations Manager pour générer des rapports de disponibilité et de disponibilité.

Votre organisation devra définir des stratégies et des procédures pour les rapports d’État.

</div>

<div>

## <a name="incident-reports"></a>Rapports d’incident

Effectuez un audit hebdomadaire des rapports d’incident de votre organisation liés à Lync Server. Cet audit doit inclure les éléments suivants :

  - Les incidents les plus fréquents générés, résolus et en attente.

  - Solutions pour les incidents non résolus.

  - Mise à jour des rapports pour inclure de nouveaux tickets de problèmes.

  - Mise à jour d’un référentiel de documents pour des guides de dépannage et des post-mortem à propos des pannes.

Étant donné que le système de suivi des incidents de votre organisation est un choix indépendant de Lync Server, des instructions ou des pointeurs spécifiques ne sont pas disponibles. Consultez la documentation relative au système choisi par votre organisation.

</div>

<div>

## <a name="check-iis-logs-and-performance"></a>Vérifier les journaux et les performances IIS

Effectuer une révision hebdomadaire des journaux et des performances des services IIS (Internet Information Services). Pour plus d’informations sur la surveillance des performances et des journaux IIS, voir [Windows Server 2003 Internet Information Services (IIS) Logging Logging Overview](https://go.microsoft.com/fwlink/?linkid=36077). La révision doit inclure les éléments suivants :

  - Compteurs de cache de service Web permettant de surveiller le cache du service WWW.

  - Compteurs ASP (Active Server Pages) pour surveiller les applications qui s’exécutent en tant qu’ASP.

</div>

<div>

## <a name="generate-database-reports"></a>Générer des rapports de base de données

**Pour générer des rapports sur la base de données SQL**

1.  Ouvrez Lync Server 2013.

2.  Dans l’arborescence de la console, développez le nœud de la forêt, développez **pools d’entreprise**, puis cliquez sur le pool pour lequel vous souhaitez générer un rapport de base de données.

3.  Dans le volet d’informations, cliquez sur l’onglet **base de données** .

4.  Sous l’onglet **base de données** , procédez comme suit :
    
    1.  Pour afficher le nom de la base de données, développez **paramètres généraux**, puis affichez le nom de la base de données.
    
    2.  Pour récupérer les statistiques de résumé de l’utilisateur actuel pour le pool, développez **rapports de résumé**de l’utilisateur, cliquez sur **atteindre**et affichez les résultats.
    
    3.  Pour récupérer les données par utilisateur actuelles pour un seul utilisateur du pool, développez **rapports par utilisateur**, tapez l’URI SIP de l’utilisateur, cliquez sur **atteindre**et affichez les résultats.

Pour récupérer les statistiques de synthèse de conférence actuelles pour le pool, développez **rapports de synthèse de conférence**, cliquez sur **atteindre**et affichez les résultats.

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a>Vérifier les mises à jour de sécurité et de Lync Server

Identifiez les nouveaux Service Packs, correctifs ou mises à jour. Si nécessaire, testez-les dans un laboratoire de test et utilisez les procédures de contrôle des modifications pour organiser le déploiement vers les serveurs de production. De plus, les mises à jour de composants Lync Server sont désormais disponibles dans le cadre de Windows Update. Toutes les mises à jour de composants Lync Server doivent être mises à jour en même temps sur tous les serveurs qui exécutent Lync Server et pour lesquels les mises à jour sont applicables.

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a>Exécuter l’outil Best Practices Analyzer Lync Server 2013

L’outil de diagnostic Lync Server 2013 Best Practices Analyzer est un outil de diagnostic qui collecte des informations de configuration et détermine si la configuration est définie conformément aux meilleures pratiques de Microsoft. La documentation relative à cet outil se trouve sur [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).

L’outil compare les données de configuration de votre déploiement par rapport à un ensemble de règles prédéfinies pour Lync Server et signale les problèmes potentiels. Pour chaque problème signalé, l’outil fournit la configuration actuelle dans l’environnement Lync Server et la configuration recommandée.

Avec l’accès réseau approprié, l’outil peut examiner vos services de domaine Active Directory et vos serveurs exécutant Lync Server 2013 pour effectuer les opérations suivantes :

  - Effectuer des vérifications d’intégrité de manière proactive, en vérifiant que la configuration est définie conformément aux meilleures pratiques recommandées

  - Générer une liste de problèmes, tels que des paramètres de configuration sous-optimaux ou des options non prises en charge ou non prises en charge

  - Évaluer l’état général d’un système

  - Aider à résoudre des problèmes spécifiques

  - Vous demander de télécharger les mises à jour si elles sont disponibles

  - Fournir une documentation en ligne et locale sur les problèmes signalés et inclure des conseils de dépannage

  - Générer des informations de configuration pouvant être capturées à des fins de révision ultérieure

Assurez-vous que le RTCBPA.msi est installé sur tous les serveurs Lync Server 2013 et générez un rapport de vérification de l’intégrité hebdomadaire. Notez les résultats et corrigez, si nécessaire.

</div>

<div>

## <a name="review-sla-performance-figures"></a>Passer en revue les chiffres de performances SLA

Vérifiez les données de performances clés pour la semaine précédente. Passez en revue les performances par rapport aux exigences du contrat SLA. Identifiez les tendances et les éléments pour lesquels les objectifs n'ont pas été satisfaits.

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a>Examen du pack d’administration et des rapports de qualité de l’expérience System Center Operations Manager

Procurez-vous et passez en revue le pack d’administration Lync Server 2013 et les rapports de qualité de l’expérience.

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a>Génération et affichage de rapports de base de données pour les pools d’entreprise

**Pour générer des rapports de pool**

1.  Ouvrez Lync Server 2013.

2.  Dans l’arborescence de la console, développez le nœud de la forêt, développez **pools d’entreprise**, puis cliquez sur le pool pour lequel vous souhaitez générer un rapport de base de données.

3.  Dans le volet d’informations, cliquez sur l’onglet **base de données** .

4.  Sous l’onglet **base de données** , procédez comme suit :
    
    1.  Pour afficher le nom de la base de données, développez **paramètres généraux**, puis affichez le nom de la base de données.
    
    2.  Pour récupérer les statistiques de résumé de l’utilisateur actuel pour le pool, développez **rapports de résumé**de l’utilisateur, cliquez sur **atteindre**et affichez les résultats.
    
    3.  Pour récupérer les données par utilisateur actuelles pour un seul utilisateur du pool, développez **rapports par utilisateur**, tapez l’URI SIP de l’utilisateur, cliquez sur **atteindre**et affichez les résultats.

Pour récupérer les statistiques de synthèse de conférence actuelles pour le pool, développez **rapports de synthèse de conférence**, cliquez sur **atteindre**et affichez les résultats.

Pour chaque pool d’entreprise, les administrateurs peuvent utiliser l’onglet **base de données** pour afficher le nom de la base de données et en extraire et afficher les rapports à partir de la base de données.

### <a name="database-reports-and-descriptions"></a>Rapports et descriptions de la base de données

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Section</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rapports de résumé des utilisateurs</p></td>
<td><p>DbAnalyze/v/Report : diag [/SqlServer : valeur]</p>
<p>Cette section affiche des informations agrégées sur les utilisateurs d’un pool, telles que le nombre d’utilisateurs activés, le nombre moyen de contacts par utilisateur et le nombre d’utilisateurs pour des fonctionnalités spécifiques.</p>
<p>Lors de l’utilisation de ces rapports, les informations suivantes peuvent être utiles :</p>
<ul>
<li><p>Un utilisateur activé est un utilisateur qui est activé pour Lync Server 2013 à l’aide du composant logiciel enfichable utilisateurs et ordinateurs Active Directory.</p></li>
<li><p>Un utilisateur actif est un utilisateur qui a ouvert une session ou a enregistré.</p></li>
<li><p>Les rapports de synthèse fournissent également un ensemble d’informations statistiques sur les contacts. Ces statistiques ne sont valides que pour la population des utilisateurs qui ont ouvert une session au moins une fois et qui disposent au moins d’un contact. Par conséquent, vous ne verrez généralement pas de nombre minimal de contacts de 0. En raison de ce comportement, si un utilisateur ne dispose d’aucun contact (mais est actif, et que l’utilisateur s’est inscrit), vous pouvez voir : &lt; vide &gt; pour certains champs de statistiques.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rapports Per-User</p></td>
<td><p>DbAnalyze/v/Report : disque [/SqlServer : valeur]</p>
<p>Contrairement aux rapports de synthèse, qui sont calculés sur une population d’utilisateurs, il s’agit de rapports sur un utilisateur spécifique.</p></td>
</tr>
<tr class="odd">
<td><p>Rapports de synthèse de conférence</p></td>
<td><p>DbAnalyze/v/Report : conf [/SqlServer : valeur]</p>
<p>Cette section affiche des informations agrégées sur les statistiques de résumé de conférence pour le pool, telles que le nombre de conférences actives et le nombre total de participants.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a>Exécution de l’analyseur d’utilisation de la bande passante

L’analyseur d’utilisation de la bande passante est un outil qui crée des rapports sur les différentes vues de la consommation de bande passante par les points de terminaison UC sur les liaisons de réseau étendu dans le réseau d’entreprise. Ces rapports peuvent être utilisés pour comprendre le modèle de consommation de bande passante actuel et contribuer à la planification de la capacité de bande passante. Elle effectue également une itération sur la capacité de bande passante affectée à différents liens.

Cet outil effectue les opérations suivantes :

  - Génère des rapports spécifiques pour l’utilisation audio sur le réseau

  - Permet une planification et une itération de capacité plus efficaces sur la capacité de bande passante affectée à différents liens

Bandwidth utilization Analyzer peut générer des tracés graphiques de la capacité de bande passante et des rapports d’utilisation. Ils sont les suivants :

  - Toutes les liaisons de réseau étendu dans le réseau d’entreprise

  - Filtré par les liaisons de réseau étendu sélectionnées

  - Filtrés par des liaisons de réseau étendu ayant dépassé la capacité de liaison

  - Filtré par les liaisons de réseau étendu qui étaient sous-utilisant la bande passante approvisionnée

  - Filtrer par les liaisons de réseau étendu qui atteignent des niveaux critiques (une utilisation de bande passante supérieure à 90% de la capacité de bande passante de la liaison de réseau étendu)

  - Filtré par type de lien WAN — liaisons de sites réseau, liens interrégionaux et liens à l’intérieur d’un site

  - Filtré par région réseau

La documentation relative à cet outil est disponible dans [la documentation sur les outils du kit de ressources Lync Server 2013](https://go.microsoft.com/fwlink/?linkid=623245).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Liste de vérification des tâches hebdomadaires](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

