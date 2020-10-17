---
title: 'Lync Server 2013 : compteurs de performances de mobilité'
description: 'Lync Server 2013 : compteurs de performances de mobilité.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 922288f6c026f088d651dc61afdcb6ba04fed30a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550530"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a>Compteurs de performances de mobilité dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Les tableaux suivants répertorient les noms et les descriptions des compteurs de performance que vous pouvez utiliser pour surveiller les serveurs exécutant l’API Web Unified Communications (UCWA) et le service Lync Server 2013 MCX Mobility.

Le nom de catégorie pour les compteurs dans la table UCWA est **ls : Web – UCWA**.

Le nom de catégorie pour les compteurs dans la table MCX Mobility service est **ls : Web-mobile communication service**.

<div>

## <a name="performance-counters-for-ucwa"></a>Compteurs de performance pour UCWA


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Compteur</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre d’applications actives</p></td>
<td><p>Nombre actuel d’applications</p></td>
</tr>
<tr class="even">
<td><p>Nombre de modalités de partage d’applications actives</p></td>
<td><p>Le nombre actuel de modalités de partage d’application</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de passes actives audio</p></td>
<td><p>Nombre actuel de modalités audio</p></td>
</tr>
<tr class="even">
<td><p>Nombre de MODALITES de collaboration de données actives</p></td>
<td><p>Le nombre actuel de modalités de collaboration de données ;</p></td>
</tr>
<tr class="odd">
<td><p>Latence d’obtention de photos Active Directory (MS)</p></td>
<td><p>Ce compteur indique le temps moyen (en millisecondes) nécessaire pour récupérer une photo à partir d’Active Directory</p></td>
</tr>
<tr class="even">
<td><p>Nombre de modalités de messagerie active</p></td>
<td><p>Nombre actuel de modalités de messagerie</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de passes vidéo panoramique actif</p></td>
<td><p>Nombre actuel de modalité vidéo panoramique</p></td>
</tr>
<tr class="even">
<td><p>Nombre d’obtentions actives en attente</p></td>
<td><p>Le nombre de gets actuellement en attente ; connexions de longue durée vers le serveur</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de sessions actives</p></td>
<td><p>Nombre actuel de points de terminaison inscrits dans UCWA par application et total</p></td>
</tr>
<tr class="even">
<td><p>Nombre d’instances de l’utilisateur actif</p></td>
<td><p>Nombre actuel d’instances utilisateur</p></td>
</tr>
<tr class="odd">
<td><p>Instances utilisateur actives sans application</p></td>
<td><p>Nombre actuel d’instances utilisateur sans application</p></td>
</tr>
<tr class="even">
<td><p>Nombre de passes de vidéo actives</p></td>
<td><p>Nombre actuel de modalités vidéo</p></td>
</tr>
<tr class="odd">
<td><p>Demandes de création d’application reçues/seconde</p></td>
<td><p>Taux de demandes de création d’application reçues par seconde</p></td>
</tr>
<tr class="even">
<td><p>En tant qu’échecs de jonction MCU</p></td>
<td><p>Nombre d’échecs de jointures MCU</p></td>
</tr>
<tr class="odd">
<td><p>Échecs de participation de la MCU AV</p></td>
<td><p>Nombre d’échecs de participation de la MCU AV</p></td>
</tr>
<tr class="even">
<td><p>Durée moyenne de démarrage de l’application (MS)</p></td>
<td><p>Durée moyenne de démarrage de l’application en millisecondes</p></td>
</tr>
<tr class="odd">
<td><p>Durée de vie moyenne de la session (MS)</p></td>
<td><p>Durée de vie moyenne d’une session en millisecondes</p></td>
</tr>
<tr class="even">
<td><p>Échecs de jonction de MCU de données</p></td>
<td><p>Nombre d’échecs de jonctions de MCU de données</p></td>
</tr>
<tr class="odd">
<td><p>Latence de recherche de contact Exchange (MS)</p></td>
<td><p>Ce compteur indique le temps moyen (en millisecondes) entre le contact de recherche dans Exchange</p></td>
</tr>
<tr class="even">
<td><p>Latence d’obtention de photo HD Exchange (MS)</p></td>
<td><p>Ce compteur indique le temps moyen (en millisecondes) nécessaire pour récupérer une photo à partir d’Exchange</p></td>
</tr>
<tr class="odd">
<td><p>Réponses 4xx HTTP/seconde</p></td>
<td><p>Taux de réponses par seconde avec le code HTTP 4xx</p></td>
</tr>
<tr class="even">
<td><p>Réponses 5xx HTTP/seconde</p></td>
<td><p>Taux de réponses par seconde avec du code HTTP 5xx</p></td>
</tr>
<tr class="odd">
<td><p>Échecs de jonctions de la MCU de messagerie instantanée</p></td>
<td><p>Nombre d’échecs de jonctions de la MCU de messagerie instantanée</p></td>
</tr>
<tr class="even">
<td><p>Nombre d’échecs d’obtention de photos Active Directory</p></td>
<td><p>Nombre total d’échecs de récupération de photos à partir d’Active Directory</p></td>
</tr>
<tr class="odd">
<td><p>Nombre d’échecs de recherche de contacts</p></td>
<td><p>Nombre total d’échecs de recherche de contacts dans Exchange</p></td>
</tr>
<tr class="even">
<td><p>Nombre d’échecs de désérialisation</p></td>
<td><p>Nombre total d’échecs de désérialisation</p></td>
</tr>
<tr class="odd">
<td><p>Nombre d’échecs de la photo HD</p></td>
<td><p>Nombre total d’échecs de récupération de photos HD à partir d’Exchange</p></td>
</tr>
<tr class="even">
<td><p>Sur le nombre maximal d’abonnements par application</p></td>
<td><p>Nombre de demandes d’abonnement sur le maximum autorisé par application</p></td>
</tr>
<tr class="odd">
<td><p>Sur le nombre maximal d’abonnements par lot</p></td>
<td><p>Nombre de demandes d’abonnement sur le maximum autorisé par lot</p></td>
</tr>
<tr class="even">
<td><p>Échecs d’abonnements de présence</p></td>
<td><p>Nombre d’échecs d’abonnement à la présence</p></td>
</tr>
<tr class="odd">
<td><p>Enregistrement des défaillances du point de terminaison</p></td>
<td><p>Nombre d’échecs d’enregistrement des points de terminaison</p></td>
</tr>
<tr class="even">
<td><p>Demandes reçues/seconde</p></td>
<td><p>Taux de demandes reçues par seconde</p></td>
</tr>
<tr class="odd">
<td><p>Demandes réussies/seconde</p></td>
<td><p>Taux de demandes réussies (codes de réponse HTTPs/3xx) par seconde</p></td>
</tr>
<tr class="even">
<td><p>Réussite de la création des demandes d’application/seconde</p></td>
<td><p>Taux de demandes de création d’application réussies par seconde</p></td>
</tr>
<tr class="odd">
<td><p>Expiration du nombre d’obtentions en attente</p></td>
<td><p>Nombre de récupérations en attente qui ont expiré</p></td>
</tr>
<tr class="even">
<td><p>Nombre total de demandes de création d’application reçues</p></td>
<td><p>Nombre total de demandes de création d’application reçues depuis le démarrage du service</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total de réponses HTTP 4xx</p></td>
<td><p>Nombre total de réponses HTTP 4xx</p></td>
</tr>
<tr class="even">
<td><p>Nombre total de réponses 5xx HTTP</p></td>
<td><p>Nombre total de réponses 5xx HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total de demandes reçues sur le canal de commande</p></td>
<td><p>Quantité totale de demandes reçues sur le canal de commande</p></td>
</tr>
<tr class="even">
<td><p>Quantité totale de demandes réussies</p></td>
<td><p>Nombre total de demandes ayant réussi</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total de sessions lancées</p></td>
<td><p>Nombre total de sessions qui ont été initiées depuis le démarrage du service</p></td>
</tr>
<tr class="even">
<td><p>Nombre total de sessions terminées en raison d’un délai d’inactivité</p></td>
<td><p>Quantité totale de sessions qui ont été terminées suite à l’expiration du délai d’inactivité utilisateur</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total d’applications limitées</p></td>
<td><p>Nombre d’applications limitées</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Compteurs de performances pour le service de mobilité MCX

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Compteur</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Durée de vie moyenne d’une session en millisecondes</p></td>
<td><p>Durée de vie moyenne d’une session en millisecondes</p></td>
</tr>
<tr class="even">
<td><p>Abonnements actuels aux notifications push</p></td>
<td><p>Quantité actuelle d’abonnements aux notifications push. Ce nombre, en association avec le nombre de sessions actuellement actives, représente le sous-ensemble des sessions actuellement actives qui sont inscrites pour les appareils Windows Mobile ou iPhone.</p></td>
</tr>
<tr class="odd">
<td><p>Nombre d’interrogations réseau expirées actuellement actives</p></td>
<td><p>Nombre d’interrogations réseau sont le délai d’attente a expiré</p></td>
</tr>
<tr class="even">
<td><p>Nombre d’interrogations actuellement actives</p></td>
<td><p>Nombre d’interrogations actuellement actives (longues connexions au serveur)</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de sessions actuellement actives</p></td>
<td><p>Quantité actuelle de points de terminaison enregistrés dans le service de mobilité</p></td>
</tr>
<tr class="even">
<td><p>Nombre de sessions actuellement actives avec abonnements de présence actifs</p></td>
<td><p>Nombre de sessions actuellement actives avec abonnements de présence actifs</p></td>
</tr>
<tr class="odd">
<td><p>Demandes de notifications push échouées/seconde</p></td>
<td><p>Taux de notifications push ayant échoué par seconde</p></td>
</tr>
<tr class="even">
<td><p>Demandes de notifications push réussies/seconde</p></td>
<td><p>Taux de notifications push ayant réussi par seconde</p></td>
</tr>
<tr class="odd">
<td><p>Demandes de notifications push limitées/seconde</p></td>
<td><p>Taux de notifications push ayant été limitées par seconde</p></td>
</tr>
<tr class="even">
<td><p>Demandes de notifications push/seconde</p></td>
<td><p>Taux de notifications push envoyées par seconde</p></td>
</tr>
<tr class="odd">
<td><p>Demandes échouées/seconde</p></td>
<td><p>Taux de demandes ayant échoué par seconde</p></td>
</tr>
<tr class="even">
<td><p>Demandes reçues/seconde</p></td>
<td><p>Taux de demandes reçues par seconde</p></td>
</tr>
<tr class="odd">
<td><p>Demandes rejetées/seconde</p></td>
<td><p>Taux de demandes rejetées par seconde</p></td>
</tr>
<tr class="even">
<td><p>Demandes réussies/seconde</p></td>
<td><p>Taux de demandes réussies par seconde</p></td>
</tr>
<tr class="odd">
<td><p>Demandes de lancement de session réussies/seconde</p></td>
<td><p>Taux de demandes Get Location réussies par seconde. Les demandes de lancement de session consomment le plus de puissance de traitement sur le serveur. La charge maximale prise en charge est de 12 par seconde. La capacité à soutenir ces charges dépend des autres charges imposées sur le serveur. Le lancement d’une session signifie généralement la connexion d’un utilisateur ayant été déconnecté depuis un laps de temps étendu.</p></td>
</tr>
<tr class="even">
<td><p>Quantité totale d’appels vocaux entrants refusés</p></td>
<td><p>Quantité totale d’appels vocaux entrants ayant été refusés</p></td>
</tr>
<tr class="odd">
<td><p>Quantité totale d’appels vocaux entrants échoués</p></td>
<td><p>Quantité totale d’appels vocaux entrants ayant échoué</p></td>
</tr>
<tr class="even">
<td><p>Quantité totale d’appels vocaux sortants échoués</p></td>
<td><p>Quantité totale d’appels vocaux sortants ayant échoué</p></td>
</tr>
<tr class="odd">
<td><p>Quantité totale de sessions terminées par l’utilisateur</p></td>
<td><p>Quantité totale de sessions auxquelles les utilisateurs ont mis fin</p></td>
</tr>
<tr class="even">
<td><p>Quantité totale de demandes de notifications push</p></td>
<td><p>Quantité totale de demandes de notifications push</p></td>
</tr>
<tr class="odd">
<td><p>Quantité totale de demandes de notifications push échouées</p></td>
<td><p>Quantité totale de demandes de notifications push ayant échoué</p></td>
</tr>
<tr class="even">
<td><p>Quantité totale de demandes de notifications push réussies</p></td>
<td><p>Quantité totale de demandes de notifications push ayant réussi</p></td>
</tr>
<tr class="odd">
<td><p>Quantité totale de demandes de notifications push limitées</p></td>
<td><p>Quantité totale de demandes de notifications push ayant limitées</p></td>
</tr>
<tr class="even">
<td><p>Quantité totale de demandes échouées</p></td>
<td><p>Quantité totale de demandes ayant échoué</p></td>
</tr>
<tr class="odd">
<td><p>Quantité totale de demandes reçues sur le canal de commande</p></td>
<td><p>Quantité totale de demandes reçues sur le canal de commande</p></td>
</tr>
<tr class="even">
<td><p>Quantité totale de demandes rejetées</p></td>
<td><p>Quantité totale de demandes ayant été rejetées</p></td>
</tr>
<tr class="odd">
<td><p>Quantité totale de demandes réussies</p></td>
<td><p>Quantité totale de demandes effectuées au service de mobilité et ayant réussi</p></td>
</tr>
<tr class="even">
<td><p>Total de sessions initiées</p></td>
<td><p>Quantité totale de sessions qui ont été initiées depuis le démarrage du service de mobilité</p></td>
</tr>
<tr class="odd">
<td><p>Total des sessions terminées pour inactivité utilisateur</p></td>
<td><p>Quantité totale de sessions qui ont été terminées suite à l’expiration du délai d’inactivité utilisateur</p></td>
</tr>
<tr class="even">
<td><p>Quantité totale d’appels vocaux entrants réussis</p></td>
<td><p>Quantité totale d’appels vocaux entrants ayant été réussis</p></td>
</tr>
<tr class="odd">
<td><p>Quantité totale d’appels vocaux sortants réussis</p></td>
<td><p>Quantité totale d’appels vocaux sortants ayant été réussis</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

