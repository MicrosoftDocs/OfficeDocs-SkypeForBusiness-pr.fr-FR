﻿---
title: 'Lync Server 2013 : Rapport détaillé de session P2P'
TOCTitle: Rapport détaillé de session P2P
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558659(v=OCS.15)
ms:contentKeyID: 49297517
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport détaillé de session P2P dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le rapport détaillé de session P2P renvoie des informations détaillées sur une session P2P. Par exemple, si vous sélectionnez une session de messagerie instantanée, le rapport indique le nombre de messages envoyés par chacun des deux utilisateurs dans la session.

## Accès au rapport détaillé de session P2P

Vous pouvez accéder au rapport de détails de session P2P à partir de l’un des rapports suivants (disponibles en totalité dans la page d’accueil Rapports de surveillance) :

  - Rapport d’inventaire de téléphonie IP

  - Rapport d’activité de l’utilisateur

  - Rapport de contrôle d’admission des appels

  - Rapport de liste des échecs

À partir du rapport rapport détaillé de session P2P, vous pouvez accéder au [Rapport de diagnostic dans Lync Server 2013](lync-server-2013-diagnostic-report.md) en cliquant sur la mesure Rapport de diagnostic (Détails). Vous pouvez aussi accéder au rapport des principales défaillances en cliquant sur l’une de ces deux mesures :

  - Réponse

  - ID de diagnostic

## Exploiter au mieux le rapport détaillé de session P2P

Le rapport détaillé de session P2P comprend un grand nombre de mesures, dont bon nombre peuvent être inconnues des administrateurs système. Cependant, dans bien des cas, vous pouvez afficher une info-bulle qui offre une brève description de cette mesure en maintenant simplement votre souris sur l’étiquette de la mesure.

Note que les mesures qui s’affichent sur un rapport donné dépendent du type de session P2P que vous avez sélectionné. Une session audio/vidéo et une session de messagerie instantanée n’affichent pas le même ensemble de mesures.

Vous pouvez également pointer votre souris sur les mesures Code de réponse et ID de diagnostic pour obtenir une description de ces valeurs :

## Filtres

Aucun. Vous ne pouvez pas filtrer le Rapport détaillé de session P2P.

## Mesures des informations de session

Le tableau ci-dessous liste les informations fournies dans le Rapport détaillé de session P2P de chaque session.

### Mesures des informations de session

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>FQDN du pool</strong></p></td>
<td><p>Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou serveur Edge impliqué dans la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>Heure d’invitation</strong></p></td>
<td><p>Date et heure auxquelles l’invitation a été envoyée à l’origine.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de réponse</strong></p></td>
<td><p>Date et heure auxquelles l’acceptation de l’invitation a été reçue.</p></td>
</tr>
<tr class="even">
<td><p><strong>De l’utilisateur</strong></p></td>
<td><p>Adresse SIP de l’utilisateur ayant initié la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agent utilisateur d’origine</strong></p></td>
<td><p>Logiciel utilisé par le point de terminaison de l’utilisateur ayant initié la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>Interne à l’utilisateur d’origine</strong></p></td>
<td><p>Indique si l’utilisateur qui a initié la session était connecté au réseau interne.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Utilisateur d’origine intégré au téléphone de bureau</strong></p></td>
<td><p>Indique si le point de terminaison utilisé par l’utilisateur qui a démarré la session est intégré à son téléphone de bureau.</p></td>
</tr>
<tr class="even">
<td><p><strong>Priorité de la session</strong></p></td>
<td><p>Priorité affectée à la session. Les priorités valides sont : Inconnu, Non urgent, Normal, Urgent et Urgence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Code de réponse</strong></p></td>
<td><p>Code de réponse SIP envoyé lors de l’échec de session.</p></td>
</tr>
<tr class="even">
<td><p><strong>Frontal</strong></p></td>
<td><p>Nom du serveur frontal utilisé dans la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Délai de capture</strong></p></td>
<td><p>Date et heure auxquelles les informations de session ont été enregistrées.</p></td>
</tr>
<tr class="even">
<td><p><strong>Heure de fin</strong></p></td>
<td><p>Date et heure de fin de la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>À l’utilisateur</strong></p></td>
<td><p>Adresse IP de l’utilisateur ayant été invité à participer à la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agent utilisateur de destination</strong></p></td>
<td><p>Logiciel utilisé par le point de terminaison de l’utilisateur qui a été invité à la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interne à l’utilisateur de destination</strong></p></td>
<td><p>Indique si l’utilisateur qui a été invité à la session était connecté au réseau interne.</p></td>
</tr>
<tr class="even">
<td><p><strong>Utilisateur de destination intégré au téléphone de bureau</strong></p></td>
<td><p>Indique si le point de terminaison utilisé par l’utilisateur qui a été invité à la session est intégré à son téléphone de bureau.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nouvelle tentative de session</strong></p></td>
<td><p>Indique si la session est une nouvelle tentative de session qui a précédemment échoué.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID de diagnostic</strong></p></td>
<td><p>Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles à l’identification et à la résolution des erreurs. Placez la souris au-dessus du numéro d’ID pour afficher des informations supplémentaires sur cet ID.</p></td>
</tr>
</tbody>
</table>


## Mesures des modalités

Le tableau ci-dessous liste les informations fournies dans le Rapport détaillé de session P2P de chaque modalité de session.

### Mesures des modalités

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
<td><p><strong>Modalités</strong></p></td>
<td><p>Non</p></td>
<td><p>Modalités utilisées dans la session. Par exemple, messagerie instantanée ou transfert de fichier.</p></td>
</tr>
<tr class="even">
<td><p><strong>Messages de l’expéditeur</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre de messages envoyés par l’utilisateur qui a démarré la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Messages du destinataire</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre de messages envoyés par l’utilisateur qui a été invité à rejoindre la session.</p></td>
</tr>
</tbody>
</table>


## Mesures pour les rapports de diagnostic

Le tableau ci-dessous liste les informations fournies dans le Rapport détaillé de session P2P pour chaque rapport de diagnostic.

### Mesures pour les rapports de diagnostic

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
<td><p><strong>Détail</strong></p></td>
<td><p>Non</p></td>
<td><p>Lorsque vous cliquez sur cet élément, le rapport montre le rapport de diagnostic pour la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>Heure du rapport</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure d’enregistrement du rapport.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Demande</strong></p></td>
<td><p>Non</p></td>
<td><p>Type de demande SIP. Par exemple, INVITE ou BYE.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID de diagnostic</strong></p></td>
<td><p>Non</p></td>
<td><p>Identifiant unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui procure souvent des informations utiles à des fins d’identification et de résolution des problèmes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type de contenu</strong></p></td>
<td><p>Non</p></td>
<td><p>Type de contenu multimédia utilisé dans la conférence. Par exemple, Application/sdp est un type de contenu commun. Le protocole SDP (Session Description Protocol) est un protocole Internet standard utilisé pour les annonces de session, les invitations aux sessions et autres formes de démarrage de session multimédia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Auteur du rapport</strong></p></td>
<td><p>Non</p></td>
<td><p>Ordinateur (c’est-à-dire, client ou serveur) qui a signalé le problème.</p></td>
</tr>
</tbody>
</table>

