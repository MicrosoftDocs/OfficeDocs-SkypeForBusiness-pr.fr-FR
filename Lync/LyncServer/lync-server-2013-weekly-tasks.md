---
title: 'Skype Entreprise Server 2015 : tâches hebdomadaires'
TOCTitle: Tâches hebdomadaires
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn722432(v=OCS.15)
ms:contentKeyID: 62281957
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tâches hebdomadaires dans Skype Entreprise Server 2015

 

_**Dernière rubrique modifiée :** 2016-12-08_

Les tâches hebdomadaires sont généralement liées à la collecte et à l’analyse des journaux et des rapports.

## Archivage des journaux des événements

Si les journaux des événements ne sont pas configurés pour remplacer des événements, en fonction des besoins, ils doivent être archivés et supprimés régulièrement. Cette action est particulièrement importante pour les journaux de sécurité, qui peuvent être nécessaires pour examiner les tentatives de violation de la sécurité.

Votre organisation devra définir des stratégies et des procédures d’archivage des journaux.

## Création de rapports

Créez des rapports de statut afin de faciliter la planification des capacités, l’examen des contrats de niveau de service (SLA) et l’analyse des performances. Créez des rapports sur l’utilisation des disques, de la mémoire et du processeur à l’aide des données quotidiennes issues du journal des événements et du moniteur système. Générez des rapports de temps de fonctionnement et de disponibilité à l’aide de System Center Operations Manager.

Votre organisation devra définir des stratégies et des procédures pour les rapports de statut.

## Rapports d’incident

Effectuez un audit hebdomadaire des rapports d’incident liés à Lync Server de votre organisation. Cet audit doit inclure les éléments suivants :

  - Principaux incidents générés, résolus et en attente

  - Solutions pour les incidents non résolus

  - Mise à jour des rapports afin d’inclure les nouveaux tickets d’incident

  - Mise à jour d’un référentiel de documents pour les manuels de résolution des problèmes et les post-mortems concernant des pannes.

Dans la mesure où le système de suivi des incidents de votre organisation relève d’un choix indépendant de Lync Server, il n’y a pas d’instructions ou de pointeurs spécifiques. Consultez la documentation du système utilisé par votre organisation.

## Consultation des journaux et des performances des services Internet (IIS)

Effectuez un examen hebdomadaire des journaux et des performances des services Internet (services Internet (IIS)). Pour plus d’informations sur la surveillance des journaux et des performances des services Internet (IIS), voir [Présentation de la journalisation des événements dans les services Internet (IIS) Windows Server 2003](http://go.microsoft.com/fwlink/?linkid=36077) (en anglais). L’examen doit inclure les éléments suivants :

  - Compteurs de mémoire cache des services web pour surveiller la mémoire cache des services WWW

  - Compteurs Active Server Pages (ASP) pour surveiller les applications exécutant des pages ASP

Pour plus d’informations sur la surveillance des journaux et des performances des services Internet (IIS), voir [Présentation de la journalisation des événements dans les services Internet (IIS) Windows Server 2003](http://go.microsoft.com/fwlink/?linkid=36077) (en anglais).

## Génération de rapports de base de données

**Pour générer des rapports sur la base de données SQL**

1.  Ouvrez le Lync Server 2013.

2.  Dans l’arborescence de la console, développez le nœud de la forêt, développez **Pools d’entreprise**, puis cliquez sur le pool pour lequel vous souhaitez générer un rapport de base de données.

3.  Dans le volet d’informations, cliquez sur l’onglet **Base de données**.

4.  Sous l’onglet **Base de données**, effectuez les actions suivantes :
    
    1.  Pour afficher le nom de la base de données, développez **Paramètres généraux** et affichez le nom de la base de données.
    
    2.  Pour extraire le résumé des statistiques utilisateur actuelles du pool, développez **Rapports de synthèse des utilisateurs**, cliquez sur **OK** et affichez les résultats.
    
    3.  Pour extraire les données par utilisateur actuelles pour un utilisateur du pool, développez **Rapports par utilisateur**, tapez l’URI SIP de l’utilisateur, cliquez sur **OK** et affichez les résultats.

Pour extraire le résumé des statistiques des conférences actuelles, développez **Rapports de synthèse des conférences**, cliquez sur **OK** et affichez les résultats.

## Recherche des mises à jour de sécurité et de Lync Server

Identifiez les nouveaux Service Packs, les correctifs ou les mises à jour. Si cela est approprié, testez-les dans un laboratoire de tests et organisez le déploiement sur les serveurs de production à l’aide des procédures de contrôle des modifications. De même, les mises à jour des composants Lync Server sont désormais disponibles dans les mises à jour Windows. Toutes les mises à jour des composants Lync Server doivent être appliquées en même temps sur tous les serveurs exécutant Lync Server pour lequel les mises à jour sont applicables.

## Exécution de Skype Entreprise Server 2013 Best Practice Analyzer

Lync Server 2013 Best Practices Analyzer est un outil de diagnostic qui collecte les informations de configuration et détermine si la configuration est définie conformément aux pratiques recommandées de Microsoft. La documentation de cet outil est disponible dans les rubriques [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md) et [Exécuter Best Practices Analyzer](https://technet.microsoft.com/fr-fr/library/gg398652\(v=ocs.15\)).

L’outil compare les données de configuration de votre déploiement à un ensemble de règles prédéfinies pour Lync Server et signale les problèmes potentiels. Pour chaque problème signalé, l’outil indique la configuration actuelle dans l’environnement Lync Server et la configuration recommandée.

Avec un accès réseau approprié, l’outil peut examiner Active Directory Domain Services (AD DS) et les serveurs qui exécutent Lync Server 2013 pour :

  - contrôler activement l’intégrité en vérifiant que la configuration est définie conformément aux pratiques recommandées ;

  - générer une liste des problèmes, comme des paramètres de configuration sous-optimaux ou des options qui ne sont pas prises en charge ou pas recommandées ;

  - estimer l’intégrité générale d’un système ;

  - aider à résoudre des problèmes spécifiques ;

  - vous inviter à télécharger les mises à jour, le cas échéant ;

  - fournir une documentation en ligne et local sur les problèmes signalés et inclure des conseils pour résoudre les problèmes ;

  - générer des informations de configuration qui peuvent être acquises pour un examen ultérieur.

Assurez-vous que RTCBPA.msi est installé sur tous les serveurs Lync Server 2013 et générez un rapport de contrôle d’intégrité hebdomadaire. Notez les résultats et corrigez, si nécessaire.

## Examen des chiffres des performances du contrat de niveau de service (SLA)

Vérifiez les données de performances principales pour la semaine précédente. Examinez les performances contre les exigences du SLA. Identifiez les tendances et les éléments qui n’ont pas atteint leur cible.

## Examen des rapports du pack de gestion de System Center Operations Manager et de qualité de l’expérience

Procurez-vous les rapports du pack de gestion de Lync Server 2013 et de qualité de l’expérience.

## Génération et affichage de rapports de base de données pour les pools d’entreprise

**Pour générer les rapports de pool**

1.  Ouvrez le Lync Server 2013.

2.  Dans l’arborescence de la console, développez le nœud de la forêt, développez **Pools d’entreprise**, puis cliquez sur le pool pour lequel vous souhaitez générer un rapport de base de données.

3.  Dans le volet d’informations, cliquez sur l’onglet **Base de données**.

4.  Sous l’onglet **Base de données**, effectuez les actions suivantes :
    
    1.  Pour afficher le nom de la base de données, développez **Paramètres généraux** et affichez le nom de la base de données.
    
    2.  Pour extraire le résumé des statistiques utilisateur actuelles du pool, développez **Rapports de synthèse des utilisateurs**, cliquez sur **OK** et affichez les résultats.
    
    3.  Pour extraire les données par utilisateur actuelles pour un utilisateur du pool, développez **Rapports par utilisateur**, tapez l’URI SIP de l’utilisateur, cliquez sur **OK** et affichez les résultats.

Pour extraire le résumé des statistiques des conférences actuelles, développez **Rapports de synthèse des conférences**, cliquez sur **OK** et affichez les résultats.

Pour chaque pool d’entreprise, les administrateurs peuvent afficher le nom de la base de données et extraire et afficher les rapports de la base de données à l’aide de l'onglet **Base de données**.

### Rapports de base de données et descriptions

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
<td><p>Rapports de synthèse des utilisateurs</p></td>
<td><p>Dbanalyze /v /report:diag [/sqlserver:value]</p>
<p>Cette section affiche des informations agrégées sur les utilisateurs d’un pool, comme le nombre d’utilisateurs actifs, le nombre moyen de contacts par utilisateur et le nombre d’utilisateurs de fonctionnalités spécifiques.</p>
<p>Lors de l’utilisation de ces rapports, les informations ci-dessous peuvent être utiles :</p>
<ul>
<li><p>Un utilisateur activé est un utilisateur qui est activé pour Lync Server 2013 en utilisant le composant logiciel enfichable Utilisateurs et ordinateurs Active Directory.</p></li>
<li><p>Un utilisateur actif est un utilisateur qui s’est connecté ou enregistré.</p></li>
<li><p>Les rapports de synthèse contiennent également des informations sur les contacts. Ces statistiques ne sont valides que pour la population d’utilisateurs qui se sont connectés au moins une fois et qui possèdent au moins un contact. Par conséquent, vous ne verrez pas, généralement, de nombre minimal de contacts égal à 0. Compte tenu de ce comportement, si un utilisateur ne possède aucun contact (mais qu’il est actif dans le sens où il s’est enregistré), la valeur « &lt;empty&gt; » peut s’afficher dans certains champs de statistiques.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rapports par utilisateur</p></td>
<td><p>Dbanalyze /v /report:disk [/sqlserver:value]</p>
<p>Contrairement aux rapports de synthèse, qui sont calculés sur une population d’utilisateurs, les rapports ci-après concernent un utilisateur spécifique.</p></td>
</tr>
<tr class="odd">
<td><p>Rapports de synthèse des conférences</p></td>
<td><p>Dbanalyze /v /report:conf [/sqlserver:value]</p>
<p>Cette section affiche des informations agrégées sur le résumé des statistiques des conférences pour le pool, comme le nombre de conférences actives et le nombre total de participants.</p></td>
</tr>
<tr class="even">
<td><p>Rapports de synthèse des utilisateurs</p></td>
<td><p>Dbanalyze /v /report:diag [/sqlserver:value]</p>
<p>Cette section affiche des informations agrégées sur les utilisateurs d’un pool, comme le nombre d’utilisateurs actifs, le nombre moyen de contacts par utilisateur et le nombre d’utilisateurs de fonctionnalités spécifiques.</p>
<p>Lors de l’utilisation de ces rapports, les informations ci-dessous peuvent être utiles :</p>
<ul>
<li><p>Un utilisateur activé est un utilisateur qui est activé pour Lync Server 2013 en utilisant le composant logiciel enfichable Utilisateurs et ordinateurs Active Directory.</p></li>
<li><p>Un utilisateur actif est un utilisateur qui s’est connecté ou enregistré.</p></li>
<li><p>Les rapports de synthèse contiennent également des informations sur les contacts. Ces statistiques ne sont valides que pour la population d’utilisateurs qui se sont connectés au moins une fois et qui possèdent au moins un contact. Par conséquent, vous ne verrez pas, généralement, de nombre minimal de contacts égal à 0. Compte tenu de ce comportement, si un utilisateur ne possède aucun contact (mais qu’il est actif dans le sens où il s’est enregistré), la valeur « &lt;empty&gt; » peut s’afficher dans certains champs de statistiques.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Rapports par utilisateur</p></td>
<td><p>Dbanalyze /v /report:disk [/sqlserver:value]</p>
<p>Contrairement aux rapports de synthèse, qui sont calculés sur une population d’utilisateurs, les rapports ci-après concernent un utilisateur spécifique.</p></td>
</tr>
<tr class="even">
<td><p>Rapports de synthèse des conférences</p></td>
<td><p>Dbanalyze /v /report:conf [/sqlserver:value]</p>
<p>Cette section affiche des informations agrégées sur le résumé des statistiques des conférences pour le pool, comme le nombre de conférences actives et le nombre total de participants.</p></td>
</tr>
</tbody>
</table>


## Exécution de Bandwidth Utilization Analyzer

L’outil Bandwidth Utilization Analyzer crée des rapports sur différents affichages de la consommation de bande passante par les points de terminaison d'UC entre les liaisons de réseau étendu dans le réseau d’entreprise. Ces rapports peuvent être utilisés pour comprendre les tendances d’utilisation de la bande passante et faciliter la planification de la capacité de la bande passante. Il traite également la capacité de bande passante affectée aux différentes liaisons par itération.

L’outil effectue les opérations suivantes :

  - Il génère des rapports spécifiques concernant l’utilisation des fonctions audio sur le réseau.

  - Il permet de planifier la capacité de façon plus efficace et de traiter la capacité de bande passante affectée aux diverses liaisons par itération.

Bandwidth Utilization Analyzer peut représenter graphiquement des tracés de la capacité de la bande passante et des rapports d’utilisation, comme suit :

  - Toutes les liaisons de réseau étendu au sein du réseau d’entreprise

  - Filtrage selon les liaisons de réseau étendu sélectionnées

  - Filtrage selon les liaisons de réseau étendu ayant dépassé leur capacité

  - Filtrage selon les liaisons de réseau étendu sous-utilisant la bande passante à disposition

  - Filtrage selon les liaisons de réseau étendu réagissant aux niveaux critiques (utilisation de la bande passant supérieure à 90 % de la capacité de la bande passante de la liaison de réseau étendu)

  - Filtrage selon le type de liaison de réseau étendu (liaisons réseau/site, liaisons interrégionales et liaisons au sein d'un site)

  - Filtrage par région de réseau

La documentation de cet outil est disponible dans la rubrique [Documentation sur les outils du Kit de ressources techniques Lync Server 2013](https://technet.microsoft.com/fr-fr/library/jj945604\(v=ocs.15\)).

## Voir aussi

#### Autres ressources

[Liste de contrôle des tâches hebdomadaires](lync-server-2013-operations-checklists.md)

