---
title: 'Lync Server 2013 : compteurs de performances de mobilité'
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
ms.openlocfilehash: 439c179476c89de8a5245e80e26586d42f4f6e3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a>Compteurs de performance de mobilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Les tableaux suivants répertorient les noms et descriptions des compteurs de performance que vous pouvez utiliser pour surveiller les serveurs exécutant l’API Unified Communications Web API (UCWA) et le service de mobilité MCX de Lync Server 2013.

Le nom de la catégorie pour les compteurs dans le tableau UCWA est **LS:WEB – UCWA**.

Le nom de la catégorie pour les compteurs dans le tableau Service de mobilité Mcx est **LS:WEB - Mobile Communication Service**.

<div>

## <a name="performance-counters-for-ucwa"></a>Compteurs de performances pour UCWA


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
<td><p>Active Application Count</p></td>
<td><p>Nombre d’applications en cours</p></td>
</tr>
<tr class="even">
<td><p>Active Application Sharing Modality Count</p></td>
<td><p>Nombre actuel de modalités de partage d’applications</p></td>
</tr>
<tr class="odd">
<td><p>Active Audio Modality Count</p></td>
<td><p>Nombre actuel de modalités audio</p></td>
</tr>
<tr class="even">
<td><p>Active Data Collaboration Modality Count</p></td>
<td><p>Nombre actuel de modalités de collaboration de données</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory Photo Get Latency (ms)</p></td>
<td><p>Ce compteur montre le temps moyen (en millisecondes) nécessaire pour récupérer une photo du répertoire actif.</p></td>
</tr>
<tr class="even">
<td><p>Active Messaging Modality Count</p></td>
<td><p>Nombre actuel de modalités de messagerie</p></td>
</tr>
<tr class="odd">
<td><p>Active Panoramic Video Modality Count</p></td>
<td><p>Nombre actuel de modalités de vidéo panoramique</p></td>
</tr>
<tr class="even">
<td><p>Active Pending Get Count</p></td>
<td><p>Nombre de gets actifs en attente ; connexions au serveur conservées depuis longtemps</p></td>
</tr>
<tr class="odd">
<td><p>Active Session Count</p></td>
<td><p>Nombre actuel de points de terminaison enregistrés dans UCWA par application et le total</p></td>
</tr>
<tr class="even">
<td><p>Active User Instance Count</p></td>
<td><p>Nombre d’instances utilisateur en cours</p></td>
</tr>
<tr class="odd">
<td><p>Active User Instances without Application</p></td>
<td><p>Nombre d’instances utilisateur en cours sans application</p></td>
</tr>
<tr class="even">
<td><p>Active Video Modality Count</p></td>
<td><p>Nombre actuel de modalités vidéo</p></td>
</tr>
<tr class="odd">
<td><p>Application Creation Requests Received/Second</p></td>
<td><p>Taux par seconde de demandes de création d’application reçues</p></td>
</tr>
<tr class="even">
<td><p>AS MCU Join Failures</p></td>
<td><p>Nombre d’échecs de connexion au service MCU AS</p></td>
</tr>
<tr class="odd">
<td><p>AV MCU Join Failures</p></td>
<td><p>Nombre d’échecs de connexion au service MCU audio/vidéo</p></td>
</tr>
<tr class="even">
<td><p>Average Application Startup Time (ms)</p></td>
<td><p>Délai de démarrage moyen de l’application en millisecondes</p></td>
</tr>
<tr class="odd">
<td><p>Average Lifetime for Session (ms)</p></td>
<td><p>Durée de vie moyenne pour une session en millisecondes</p></td>
</tr>
<tr class="even">
<td><p>Data MCU Join Failures</p></td>
<td><p>Nombre d’échecs de connexion au service MCU de données</p></td>
</tr>
<tr class="odd">
<td><p>Exchange Contact Search Latency (ms)</p></td>
<td><p>Ce compteur affiche le temps moyen (en millisecondes) nécessaire pour rechercher des contacts dans Exchange</p></td>
</tr>
<tr class="even">
<td><p>Exchange HD Photo Get Latency (ms)</p></td>
<td><p>Ce compteur affiche le temps moyen (en millisecondes) nécessaire pour récupérer une photo HD d’Exchange</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 4xx Responses/Second</p></td>
<td><p>Taux de réponses avec un code 4xx HTTP par seconde</p></td>
</tr>
<tr class="even">
<td><p>HTTP 5xx Responses/Second</p></td>
<td><p>Taux de réponses avec un code 5xx HTTP par seconde</p></td>
</tr>
<tr class="odd">
<td><p>IM MCU Join Failures</p></td>
<td><p>Nombre d’échecs de connexion au service MCU de messagerie instantanée</p></td>
</tr>
<tr class="even">
<td><p>Number of Active Directory Photo Get Failures</p></td>
<td><p>Nombre d’échecs de récupération de photos du répertoire actif</p></td>
</tr>
<tr class="odd">
<td><p>Number of Contact Search failures</p></td>
<td><p>Nombre total d’échecs de recherche de contacts dans Exchange</p></td>
</tr>
<tr class="even">
<td><p>Number of Deserialization Failures</p></td>
<td><p>Nombre total d’échecs de désérialisation</p></td>
</tr>
<tr class="odd">
<td><p>Nombre d’échecs de photo HD</p></td>
<td><p>Nombre total d’échecs de récupération de photos HD depuis Exchange</p></td>
</tr>
<tr class="even">
<td><p>Over The Maximum Subscriptions Per Application</p></td>
<td><p>Nombre de requêtes d’abonnement dépassant le nombre maximal autorisé par application</p></td>
</tr>
<tr class="odd">
<td><p>Over The Maximum Subscriptions Per Batch</p></td>
<td><p>Nombre de requêtes d’abonnement dépassant le nombre maximal autorisé par lot</p></td>
</tr>
<tr class="even">
<td><p>Presence Subscription Failures</p></td>
<td><p>Nombre d’échecs d’abonnement de présence</p></td>
</tr>
<tr class="odd">
<td><p>Registering Endpoint Failures</p></td>
<td><p>Nombre d’échecs d’enregistrement de points de terminaison</p></td>
</tr>
<tr class="even">
<td><p>Requests Received/Second</p></td>
<td><p>Taux de demandes reçues par seconde</p></td>
</tr>
<tr class="odd">
<td><p>Requests Succeeded/Second</p></td>
<td><p>Taux de demandes réussies par seconde (codes de réponse 2xx/3xx HTTP)</p></td>
</tr>
<tr class="even">
<td><p>Succeeded Create Application Requests/Second</p></td>
<td><p>Taux de demandes de création d’application réussies par seconde</p></td>
</tr>
<tr class="odd">
<td><p>Timed Out Pending Get Count</p></td>
<td><p>Nombre de gets en attente ayant expiré</p></td>
</tr>
<tr class="even">
<td><p>Total Application Creation Requests Received</p></td>
<td><p>Nombre total de demandes de création d’application reçues depuis le démarrage du service</p></td>
</tr>
<tr class="odd">
<td><p>Total HTTP 4xx Responses</p></td>
<td><p>Nombre total de réponses 4xx HTTP</p></td>
</tr>
<tr class="even">
<td><p>Total HTTP 5xx Responses</p></td>
<td><p>Nombre total de réponses 5xx HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Total Requests Received on the Command Channel</p></td>
<td><p>Nombre total de demandes reçues sur le canal de commande</p></td>
</tr>
<tr class="even">
<td><p>Total Requests Succeeded</p></td>
<td><p>Nombre total de demandes réussies</p></td>
</tr>
<tr class="odd">
<td><p>Total Sessions Initiated</p></td>
<td><p>Nombre total de sessions initiées depuis le démarrage du service</p></td>
</tr>
<tr class="even">
<td><p>Total Sessions Terminated Because of Idle Timeout</p></td>
<td><p>Nombre total de sessions terminées en raison d’un délai d’expiration d’inactivité</p></td>
</tr>
<tr class="odd">
<td><p>Total Throttled Applications</p></td>
<td><p>Nombre d’applications limitées</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Compteurs de performances pour le service de mobilité Mcx

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
<td><p>Durée de vie moyenne pour une session en millisecondes</p></td>
</tr>
<tr class="even">
<td><p>Abonnements actuels aux notifications push</p></td>
<td><p>Nombre actuel d’abonnements de notification push. Ce chiffre, associé au Nombre de sessions actuellement actives, représente le sous-ensemble de sessions actuellement actives enregistrées pour les appareils Windows Mobile ou iPhone.</p></td>
</tr>
<tr class="odd">
<td><p>Nombre d’interrogations réseau expirées actuellement actives</p></td>
<td><p>Nombre d’interrogations réseau dont le délai d’attente a expiré</p></td>
</tr>
<tr class="even">
<td><p>Nombre d’interrogations actuellement actives</p></td>
<td><p>Nombre d’interrogations actuellement actives (longues connexions au serveur)</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de sessions actuellement actives</p></td>
<td><p>Nombre actuel de points de terminaison enregistrés dans le service de mobilité</p></td>
</tr>
<tr class="even">
<td><p>Nombre de sessions actuellement actives avec abonnements de présence actifs</p></td>
<td><p>Nombre de sessions actuellement actives avec abonnements de présence actifs</p></td>
</tr>
<tr class="odd">
<td><p>Demandes de notifications push ayant échoué/seconde</p></td>
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
<td><p>Demandes ayant échoué/seconde</p></td>
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
<td><p>Nombre total d’appels vocaux entrants refusés</p></td>
<td><p>Nombre total d’appels vocaux entrants ayant été refusés</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total d’appels vocaux entrants ayant échoué</p></td>
<td><p>Nombre total d’appels vocaux entrants ayant échoué</p></td>
</tr>
<tr class="even">
<td><p>Nombre total d’appels vocaux sortants ayant échoué</p></td>
<td><p>Nombre total d’appels vocaux sortants ayant échoué</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total de sessions terminées par l’utilisateur</p></td>
<td><p>Nombre total de sessions auxquelles les utilisateurs ont mis fin</p></td>
</tr>
<tr class="even">
<td><p>Nombre total de demandes de notifications push</p></td>
<td><p>Nombre total de demandes de notifications push</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total de demandes de notifications push ayant échoué</p></td>
<td><p>Nombre total de demandes de notifications push ayant échoué</p></td>
</tr>
<tr class="even">
<td><p>Nombre total de demandes de notifications push réussies</p></td>
<td><p>Nombre total de demandes de notifications push ayant réussi</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total de demandes de notifications push limitées</p></td>
<td><p>Nombre total de demandes de notifications push ayant limitées</p></td>
</tr>
<tr class="even">
<td><p>Nombre total de demandes ayant échoué</p></td>
<td><p>Nombre total de demandes ayant échoué</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total de demandes reçues sur le canal de commande</p></td>
<td><p>Nombre total de demandes reçues sur le canal de commande</p></td>
</tr>
<tr class="even">
<td><p>Nombre total de demandes rejetées</p></td>
<td><p>Nombre total de demandes ayant été rejetées</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total de demandes réussies</p></td>
<td><p>Nombre total de demandes effectuées au service de mobilité et ayant réussi</p></td>
</tr>
<tr class="even">
<td><p>Total de sessions initiées</p></td>
<td><p>Nombre total de sessions qui ont été initiées depuis le démarrage du service de mobilité</p></td>
</tr>
<tr class="odd">
<td><p>Total des sessions terminées pour inactivité utilisateur</p></td>
<td><p>Nombre total de sessions terminées en raison d’un délai d’expiration d’inactivité</p></td>
</tr>
<tr class="even">
<td><p>Nombre total d’appels vocaux entrants réussis</p></td>
<td><p>Nombre total d’appels vocaux entrants ayant été réussis</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total d’appels vocaux sortants réussis</p></td>
<td><p>Nombre total d’appels vocaux sortants ayant été réussis</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

