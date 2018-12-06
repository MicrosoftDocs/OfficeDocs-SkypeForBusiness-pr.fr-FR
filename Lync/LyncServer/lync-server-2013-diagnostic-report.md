﻿---
title: 'Lync Server 2013 : Rapport de diagnostic'
TOCTitle: Rapport de diagnostic
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615445(v=OCS.15)
ms:contentKeyID: 49298570
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport de diagnostic dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Le Rapport de diagnostic fournit des informations de diagnostic et d’identification et de résolution des problèmes pour les sessions ayant échoué. Ces informations incluent à la fois l’ID de diagnostic et l’en-tête de diagnostic qui ont été signalés lorsque la session a échoué. L’ID de diagnostic est un identificateur unique (sous la forme d’un en-tête ms-diagnostics) qui est joint à un message SIP, tandis que l’en-tête de diagnostic fournit une description d’accompagnement pour l’ID de diagnostic. Ce rapport peut également contenir des informations d’identification et de résolution des problèmes précieuses qui sont connues par le composant de rapport. Par exemple :

  - Code de motif fourni par la passerelle RTC qui a généré la défaillance. Quand un appel sortant échoue sur le réseau téléphonique commuté, un code de motif de la « partie Usager RNIS » (ISUP) est automatiquement généré. Par exemple, une passerelle RTC peut renvoyer le code de motif 34, indiquant ainsi qu’aucun circuit ou canal n’était disponible pour terminer l’appel.

  - Nom de domaine complet (FQDN), port et erreurs Winsock de l’homologue pour les échecs de connectivité.

  - Noms recherchés pour les échecs de résolution DNS. La résolution DNS a lieu chaque fois qu’un client contacte un serveur de noms et demande l’adresse IP correspondant au nom du périphérique spécifié

## Accès au Rapport de diagnostic

Le Rapport de diagnostic est accessible en cliquant sur la métrique Rapport de diagnostic (Détail) sur le [Rapport détaillé de session P2P dans Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) ou le Rapport détaillé de conférence.

## Filtres

Aucun. Il est impossible de filtrer le rapport de diagnostic.

## Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de diagnostic pour chaque session.

### Mesures du rapport de diagnostic

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Est-il possible d’effectuer un tri sur cet élément ?</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Heure du rapport</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure d’enregistrement du rapport.</p></td>
</tr>
<tr class="even">
<td><p><strong>Code de réponse</strong></p></td>
<td><p>Non</p></td>
<td><p>Code de réponse SIP envoyé lors de l’échec de session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type de demande</strong></p></td>
<td><p>Non</p></td>
<td><p>Type de demande SIP ayant échoué. Par exemple, INVITE, BYE ou SERVICE.</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>Non</p></td>
<td><p>Source de l’erreur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URI de l’utilisateur d’origine</strong></p></td>
<td><p>Non</p></td>
<td><p>Adresse SIP de l’utilisateur ayant initié la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agent utilisateur d’origine</strong></p></td>
<td><p>Non</p></td>
<td><p>Logiciel utilisé par le point de terminaison de l’utilisateur ayant initié la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ID de diagnostic</strong></p></td>
<td><p>Non</p></td>
<td><p>Identifiant unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui procure souvent des informations utiles à des fins d’identification et de résolution des erreurs.</p></td>
</tr>
<tr class="even">
<td><p><strong>Type de contenu</strong></p></td>
<td><p>Non</p></td>
<td><p>Type de contenu multimédia ayant échoué. Par exemple, un type de contenu courant est Application/sdp. Session Description Protocol (SDP) est un protocole Internet standard utilisé pour les annonces de session, les invitations de session et autres formes d’initiation de session multimédia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Application</strong></p></td>
<td><p>Non</p></td>
<td><p>Application impliquée dans l’erreur.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI de l’utilisateur de destination</strong></p></td>
<td><p>Non</p></td>
<td><p>Adresse IP de l’utilisateur ayant été invité à participer à la session.</p></td>
</tr>
<tr class="odd">
<td><p>Temps de connexion à la conférence (ms)</p></td>
<td><p>Non</p></td>
<td><p>Temps (en millisecondes) utilisé pour que l’utilisateur rejoigne la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>En-tête de diagnostic</strong></p></td>
<td><p>Non</p></td>
<td><p>Description de l’ID de diagnostic.</p></td>
</tr>
</tbody>
</table>


Vous trouverez une liste d’erreurs de diagnostic à la page [Ms-Diagnostics Header](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx).

