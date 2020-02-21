---
title: 'Lync Server 2013 : rapport de diagnostic'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e95d746d323e803bf7dbc37e8cdaebcdd1d655c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a>Rapport de diagnostic dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-07_

Le Rapport de diagnostic fournit des informations de diagnostic et de dépannage pour les sessions ayant échoué. Ces informations incluent à la fois l’ID de diagnostic et l’en-tête de diagnostic qui ont été signalés lorsque la session a échoué. L’ID de diagnostic est un identificateur unique (sous la forme d’un en-tête ms-diagnostics) qui est joint à un message SIP, tandis que l’en-tête de diagnostic fournit une description d’accompagnement pour l’ID de diagnostic. Ce rapport peut également contenir des informations de dépannage précieuses qui sont connues par le composant de rapport. Par exemple :

  - Code de motif fourni par la passerelle PSTN qui a généré la défaillance. Quand un appel sortant échoue sur le réseau téléphonique commuté, un code de motif de la « partie Usager RNIS » (ISUP) est automatiquement généré. Par exemple, une passerelle PSTN peut retourner le code de motif 34, indiquant ainsi qu’aucun circuit ou canal n’était disponible pour terminer l’appel.

  - Nom de domaine complet (FQDN), port et erreurs Winsock de l’homologue pour les échecs de connectivité.

  - Noms recherchés pour les échecs de résolution DNS. La résolution DNS a lieu chaque fois qu’un client contacte un serveur de noms et demande l’adresse IP correspondant au nom du périphérique spécifié

<div>

## <a name="accessing-the-diagnostic-report"></a>Accès au Rapport de diagnostic

Le rapport de diagnostic est accessible en cliquant sur la mesure rapport de diagnostic (détail) sur le [rapport détaillé de session P2P dans Lync Server 2013 ou dans](lync-server-2013-peer-to-peer-session-detail-report.md) le rapport détaillé de conférence.

</div>

<div>

## <a name="filters"></a>Filtres

Aucun. Il est impossible de filtrer le rapport de diagnostic.

</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de diagnostic pour chaque session.

### <a name="diagnostic-report-metrics"></a>Mesures du rapport de diagnostic

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
<td><p>Identifiant unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui procure souvent des informations utiles à des fins de dépannage.</p></td>
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


Une liste des erreurs de diagnostic se trouve dans la [page d’en-tête MS-Diagnostics](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

