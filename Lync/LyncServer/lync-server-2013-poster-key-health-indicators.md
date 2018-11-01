---
title: Key Health Indicators
TOCTitle: 'Affiche : Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084842
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Key Health Indicators

 

_**Dernière rubrique modifiée :** 2016-12-08_

Le présent article complète l'affiche [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](http://go.microsoft.com/fwlink/?linkid=391838), que vous pouvez télécharger à partir du Centre de téléchargement.

![Poster décrivant le dépannage à l’aide des données KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster décrivant le dépannage à l’aide des données KHI")

Vous pouvez utiliser cette affiche pour en savoir davantage sur les indicateurs KHI (Key Health Indicators), les compteurs de performance avec des seuils destinés à révéler les problèmes rencontrés lors de l'expérience utilisateur. La collecte des données KHI constitue généralement la première étape vers l'implémentation du CQM (Call Quality Methodology), dont la finalité est d'assurer une expérience audio de qualité pour les utilisateurs Lync.

Si vous avez des questions sur la façon d'utiliser CQM, vous pouvez les soumettre à cqmfeedback@microsoft.com.

L'affiche explique les points suivants :

  - Que sont les Key Health Indicators ?

  - Pour collecter des données KHI

  - Flux de correction pour tous les rôles de serveur

  - Glossaire

  - Serveurs frontaux

  - Serveurs SQL principaux

  - Serveurs de médiation

  - Serveurs Edge

## Que sont les Key Health Indicators ?

Les Key Health Indicators (KHI) sont des compteurs de performance avec des seuils destinés à révéler les problèmes lors de l'expérience utilisateur. La collecte des données KHI est généralement la première étape vers l'implémentation du CQM (Call Quality Methodology), dont la finalité est d'assurer une expérience audio de qualité pour les utilisateurs Lync.

Les indicateurs KHI complètent les solutions de surveillance Lync standard (à savoir, System Center Operations Manager, Synthetic Transactions, Monitoring Server) et ne les remplacent pas.

Collectez les compteurs de performance KHI et remplissez le tableur KHI accompagnant le guide réseau (Networking Guide) afin d'obtenir une carte de performance vous permettant de déterminer l'état d'intégrité d'un serveur lors d'un déploiement Lync. Une fois remplie, cette carte vous aide à réparer l'environnement et vous apporte un éclairage supplémentaire sur d'autres éléments de l'infrastructure. Évaluez les indicateurs KHI à une fréquence mensuelle et incorporez-les dans tous les processus opérationnels de votre déploiement.

Téléchargez [Lync Server Networking Guide](http://go.microsoft.com/fwlink/p/?linkid=390677) pour obtenir la liste complète des indicateurs KHI et les tableurs associés.

## Pour collecter des données KHI

1.  Exécutez le script KHI inclus avec le guide réseau Lync Server sur chaque serveur Lync. Un collecteur de données est créé dans l'Analyseur de performances, nommez-le KHI. Par défaut, les données sont interrogées toutes les 15 secondes.

2.  Avant de commencer la journée de travail, accédez à chaque serveur Lync Server et démarrez le collecteur de données KHI.

3.  À la fin de la journée, arrêtez la collecteur de données KHI et copiez les données vers un emplacement centralisé.

4.  Après avoir utilisé l'Analyseur de performances pour remplir le tableur KHI inclus dans le téléchargement du guide réseau Lync Server, comparez les résultats aux valeurs cibles recommandées.

## Flux de correction pour tous les rôles serveur

Pour chaque serveur de votre implémentation Lync, commencez par vérifier que l'intégrité du serveur et les performances du système se situent au niveau voulu ou au-dessus de celui-ci. Ce n'est qu'ensuite que vous pouvez examiner les indicateurs concernant le rôle de serveur dans l'implémentation globale Lync.

Commencez par collecter les données de performance KHI pour tous les serveurs. Pour chaque rôle de système (voir plus loin dans ce document pour les détails), déterminez si les composants du système de base respectent les valeurs cibles recommandées. Sinon, corrigez les performances du système, recollectez les données KHI et vérifiez l'intégrité du système avant d'examiner les métriques propres au rôle de serveur dans l'implémentation Lync. L'intégrité des composants pour tous les rôles est définie comme suit :

  - Utilisation du processeur \< 80%

  - Moyenne des écritures sur disque \< 10 ms

  - Moyenne des lectures sur disque \< 10 ms

  - Available memory  \>20% System Total MB

  - Longueur de la file d'attente réseau \< 2

  - Paquets ignorés (entrée/sortie) = 0

## Glossaire

Cette affiche utilise les termes et acronymes suivants :

AS MCU = Application Sharing Multi-point Control Unit

MCU AV = MCU Audio-Vidéo

MCU MI = MCU de messagerie instantanée

UCWA = Unified Communications Web API (API Web de communications unifiées)

AV Edge = Traversée audio/vidéo via edge

Auth AV = Authentification audio/vidéo

Pile SIP = Contient l'implémentation SIP de base Lync

Proxy de données = Utilisé pour les conférences Edge

LySS = Lync Storage Service (service de stockage Lync)

## Serveurs frontaux

Les valeurs cibles KHI suivantes recommandées sont spécifiques aux serveurs frontaux en plus de l'intégrité de base des composants :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zone fonctionnelle</th>
<th>Métriques cibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AS/AV/IM MCU</p></td>
<td><p>État intégrité MCU &lt;2</p></td>
</tr>
<tr class="even">
<td><p>Composants Web</p></td>
<td><p>Délais AD de l'expansion de la liste de distribution &lt;0</p>
<p>Échecs ABWQ = 0</p>
<p>Échecs LIS = 0</p>
<p>Erreurs d'authentification &lt; 1/s</p>
<p>Requêtes ASP.NET v4 rejetées = 0</p></td>
</tr>
<tr class="odd">
<td><p>Pile SIP</p></td>
<td><p>Moyenne des traitements des messages entrants &lt; 1 s</p>
<p>Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</p>
<p>Latence de file d'attente &lt; 100 ms</p>
<p>Latence Sproc &lt; 100 ms</p>
<p>Requêtes limitées = 0</p>
<p>Erreurs d'authentification &lt; 1/s</p>
<p>Expiration des messages entrants &lt; 2</p>
<p>Moyenne des messages entrants mis en attente &lt; 1 s</p>
<p>Connexions avec contrôle de flux &lt; 2</p>
<p>Expiration moyenne de file d'attente &lt; 2 s</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>% d'espace utilisé par la base de données du service de stockage &lt; 80</p>
<p>Nombre d'échecs de réplications de réplicas = 0</p>
<p>Nombre d'événements de pertes de données = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Espérance de vie d'une page &gt; 300 s.</p>
<p>Requêtes de lots / sec &lt; 2500</p></td>
</tr>
</tbody>
</table>


## Serveurs SQL principaux

Les valeurs cibles KHI suivantes recommandées sont spécifiques aux serveurs SQL en plus de l'intégrité de base des composants :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zone fonctionnelle</th>
<th>Métriques cibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Espérance de vie d'une page &gt; 300 s.</p>
<p>Requêtes de lot / s &lt; 2500</p></td>
</tr>
</tbody>
</table>


## Serveurs de médiation

Les valeurs cibles KHI suivantes recommandées sont spécifiques aux serveurs de médiation en plus de l'intégrité de base des composants :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zone fonctionnelle</th>
<th>Métriques cibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Service de serveur de médiation</p></td>
<td><p>Indice d'échec de chargement des appels = 0</p>
<p>Appels n'ayant pas abouti à cause du proxy &lt;10</p>
<p>Appels n'ayant pas abouti à cause de la passerelle &lt;10</p>
<p>Appels (entrants ou sortants) rejetés = 0</p>
<p>Candidats de média manquants = 0</p>
<p>Échecs de vérification de la connectivité des médias = 0</p></td>
</tr>
</tbody>
</table>


## Serveurs Edge

Les valeurs cibles KHI suivantes recommandées sont spécifiques aux serveurs Edge en plus de l'intégrité de base des composants :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zone fonctionnelle</th>
<th>Métriques cibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Auth AV</p></td>
<td><p>Requêtes incorrectes &lt; 20/s</p></td>
</tr>
<tr class="even">
<td><p>Edge AV</p></td>
<td><p>Échec d'authentification &lt;20/s</p>
<p>Échecs d'allocation &lt;20/s</p>
<p>Paquets abandonnés &lt;300/s</p></td>
</tr>
<tr class="odd">
<td><p>Proxy de données</p></td>
<td><p>Connexions serveur limitées &lt; 3</p>
<p>Le système impose une limitation &lt;1</p></td>
</tr>
<tr class="even">
<td><p>Pile SIP</p></td>
<td><p>Connexions au-delà de la limite abandonnées &lt; 1</p>
<p>Expiration des envois &lt;10</p>
<p>Connexions à contrôle de flux &lt;100</p>
<p>Requêtes entrantes abandonnées &lt; 1/s</p>
<p>Traitement moyen des messages &lt; 3 s</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Autres ressources

[Lync Server Networking Guide](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](http://go.microsoft.com/fwlink/?linkid=391838)  
[Lync Call Quality Methodology](http://go.microsoft.com/fwlink/?linkid=391841)

