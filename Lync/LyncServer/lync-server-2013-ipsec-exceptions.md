---
title: Exceptions Ipsec dans Lync Server 2013
TOCTitle: Exceptions Ipsec dans Lync Server 2013
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425719(v=OCS.15)
ms:contentKeyID: 49296577
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exceptions Ipsec dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Dans les réseaux d’entreprise où la sécurité du protocole Internet (IPsec, Internet Protocol security) a été déployée (voir les RFC 4301-4309 de l’IETF), IPsec doit être désactivée sur la plage de ports utilisée pour la transmission des données audio/vidéo et des panoramas vidéo. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.

Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec.

### Exceptions recommandées pour IPsec

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom de la règle</th>
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Protocole</th>
<th>Port source</th>
<th>Port de destination</th>
<th>Besoin d’authentification</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur Edge A/V, ports internes/entrants</p></td>
<td><p>Indifférente</p></td>
<td><p>Serveur Edge A/V - interne</p></td>
<td><p>UDP et TCP</p></td>
<td><p>Indifférent</p></td>
<td><p>Indifférent</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="even">
<td><p>Serveur Edge A/V, ports externes/entrants</p></td>
<td><p>Indifférente</p></td>
<td><p>Serveur Edge A/V - externe</p></td>
<td><p>UDP et TCP</p></td>
<td><p>Indifférent</p></td>
<td><p>Indifférent</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="odd">
<td><p>Serveur Edge A/V, ports internes/sortants</p></td>
<td><p>Serveur Edge A/V - interne</p></td>
<td><p>Indifférente</p></td>
<td><p>TCP et UDP</p></td>
<td><p>Indifférent</p></td>
<td><p>Indifférent</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="even">
<td><p>Serveur Edge A/V, ports externes/sortants</p></td>
<td><p>Serveur Edge A/V - externe</p></td>
<td><p>Indifférente</p></td>
<td><p>UDP et TCP</p></td>
<td><p>Indifférent</p></td>
<td><p>Indifférent</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="odd">
<td><p>Serveur de médiation, ports entrants</p></td>
<td><p>Indifférente</p></td>
<td><p>Serveur(s)</p>
<p>de médiation</p></td>
<td><p>UDP et TCP</p></td>
<td><p>Indifférent</p></td>
<td><p>Indifférent</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="even">
<td><p>Serveur de médiation, ports sortants</p></td>
<td><p>Serveur(s)</p>
<p>de médiation</p></td>
<td><p>Indifférente</p></td>
<td><p>UDP et TCP</p></td>
<td><p>Indifférent</p></td>
<td><p>Indifférent</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="odd">
<td><p>Intendant Conférence entrant</p></td>
<td><p>Indifférente</p></td>
<td><p>Serveur frontal exécutant l’Intendant Conférence</p></td>
<td><p>UDP et TCP</p></td>
<td><p>Indifférente</p></td>
<td><p>Indifférent</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="even">
<td><p>Intendant Conférence sortant</p></td>
<td><p>Serveur frontal exécutant l’Intendant Conférence</p></td>
<td><p>Indifférent</p></td>
<td><p>UDP et TCP</p></td>
<td><p>Indifférente</p></td>
<td><p>Indifférente</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="odd">
<td><p>Serveur de conférence A/V, ports entrants</p></td>
<td><p>Indifférent</p></td>
<td><p>Serveurs frontaux</p></td>
<td><p>UDP et TCP</p></td>
<td><p>Indifférent</p></td>
<td><p>Indifférente</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="even">
<td><p>Conférence A/V, ports sortants</p></td>
<td><p>Serveurs frontaux</p></td>
<td><p>Indifférent</p></td>
<td><p>UDP et TCP</p></td>
<td><p>Indifférent</p></td>
<td><p>Indifférente</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="odd">
<td><p>Exchange, ports entrants</p></td>
<td><p>Indifférent</p></td>
<td><p>Messagerie unifiée Exchange</p></td>
<td><p>UDP et TCP</p></td>
<td><p>Indifférent</p></td>
<td><p>Indifférente</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="even">
<td><p>Serveurs de partage d’application, ports entrants</p></td>
<td><p>Indifférent</p></td>
<td><p>Serveurs de partage d’application</p></td>
<td><p>TCP</p></td>
<td><p>Indifférent</p></td>
<td><p>Indifférente</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="odd">
<td><p>Serveur de partage d’application, ports sortants</p></td>
<td><p>Serveurs de partage d’application</p></td>
<td><p>Indifférent</p></td>
<td><p>TCP</p></td>
<td><p>Indifférent</p></td>
<td><p>Indifférente</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="even">
<td><p>Exchange, ports sortants</p></td>
<td><p>Messagerie unifiée Exchange</p></td>
<td><p>Indifférent</p></td>
<td><p>UDP et TCP</p></td>
<td><p>Indifférent</p></td>
<td><p>Indifférente</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>Indifférent</p></td>
<td><p>Indifférent</p></td>
<td><p>UDP</p></td>
<td><p>Plage de ports multimédias définie</p></td>
<td><p>Indifférente</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
</tbody>
</table>

