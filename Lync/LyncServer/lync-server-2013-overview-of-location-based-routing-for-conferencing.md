---
title: Vue d’ensemble du routage géodépendant pour les conférences
TOCTitle: Vue d’ensemble du routage géodépendant pour les conférences
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56269625
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble du routage géodépendant pour les conférences

 

_**Dernière rubrique modifiée :** 2015-03-09_

L‘application de conférence avec routage géodépendant offre aux conférences Lync un mécanisme de prévention du contournement des frais de réseau téléphonique commuté. Elle surveille les conférences actives et applique des restrictions de routage géodépendant sur la base de l’emplacement des utilisateurs Lync qui y participent.

L’application de conférence avec routage géodépendant détermine si le routage géodépendant doit être appliqué à une réunion Lync lorsque les critères suivants sont satisfaits :

  - Le routage géodépendant est activé pour l’organisateur de la réunion. Les restrictions de routage géodépendant sont appliquées aux seules conférences organisées par des utilisateurs pour lesquels le routage géodépendant est activé.

  - Au moins un participant à la réunion est un point de terminaison PSTN. Les restrictions de routage géodépendant sont appliquées aux seules conférences incluant des points de terminaison PSTN.

  - Le site réseau sur lequel la passerelle PSTN utilisée pour relier la conférence au réseau téléphonique commuté est localisée, de même que les sites réseau depuis lesquels les organisateurs et les participants se connectent.

L’application de conférence avec routage géodépendant empêche la participation des utilisateurs Lync et des points de terminaison PSTN issus de différents sites réseau à la même conférence. Si le routage géodépendant est activé pour l’organisateur d’une réunion, l’application de conférence applique les restrictions suivantes :

  - Les points de terminaison pouvant rejoindre une réunion Lync dépendent des points de terminaison qui ont déjà rejoint la conférence. Cette restriction s’ajuste à mesure que des points de terminaison ayant rejoint la conférence la quittent et que de nouveaux points de terminaison la rejoignent. Si les organisateurs et les participants rejoignent une réunion Lync à partir du même site réseau, un point de terminaison PSTN, un autre participant issu du même site réseau, un autre participant issu d’un autre site réseau ou un participant issu d’un site réseau inconnu sont autorisés à rejoindre la conférence.

  - Si les organisateurs et les participants rejoignent la réunion à partir d’autres sites réseaux ou de sites réseau inconnus, un point de terminaison PSTN n’est pas autorisé à rejoindre la réunion si l’appel PSTN provient d’une jonction SIP pour laquelle le routage géodépendant est activé.

  - Si les organisateurs et participants rejoignent tous la réunion à partir du même site réseau et que des participants rejoignent la même réunion à partir du réseau téléphonique commuté, un point de terminaison Lync issu d’un autre site réseau n’est pas autorisé à rejoindre la réunion.

Ces restrictions de routage géodépendant appliquées aux conférences sont résumées dans le tableau suivant.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Utilisateur(s) dans une conférence à un moment donné</p></td>
<td><p>Utilisateur(s) autorisés à rejoindre la conférence</p></td>
<td><p>Utilisateur(s) non autorisés à rejoindre la conférence</p></td>
</tr>
<tr class="even">
<td><p>Utilisateur(s) de client VoIP Lync issu(s) d’un seul site réseau</p></td>
<td><p>Utilisateur de client VoIP Lync issu du même site réseau</p>
<p>Utilisateur de client VoIP Lync issu d’un autre site réseau</p>
<p>Utilisateur de client VoIP Lync issu d’un autre site réseau inconnu</p>
<p>Utilisateur de client VoIP Lync fédéré</p>
<p>Utilisateur rejoignant la conférence à partir d’un point de terminaison PSTN</p></td>
<td><p>Aucun</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>Utilisateur(s) de client VoIP Lync issu(s) d’un site réseau inconnu</p></td>
<td><p>Utilisateur de client VoIP Lync issu d’un site quelconque</p>
<p>Utilisateur de client VoIP Lync issu d’un site inconnu</p>
<p>Utilisateur de client VoIP Lync fédéré</p></td>
<td><p>Utilisateur rejoignant la conférence via un point de terminaison PSTN</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>Utilisateurs de client VoIP Lync issus d’autres sites réseau</p></td>
<td><p>Utilisateur de client VoIP Lync issu d’un site réseau quelconque</p>
<p>Utilisateur de client VoIP Lync issu d’un site réseau inconnu</p>
<p>Utilisateur de client VoIP Lync fédéré</p></td>
<td><p>Utilisateur rejoignant la conférence via un point de terminaison PSTN</p></td>
</tr>
<tr class="odd">
<td><p>Utilisateur(s) de client VoIP Lync issu(s) d’un seul site réseau et utilisateurs rejoignant la conférence à partir d’un point de terminaison PSTN</p></td>
<td><p>Utilisateur de client VoIP Lync issu du même site réseau</p>
<p></p></td>
<td><p>Utilisateur de client VoIP Lync issu d’un autre site réseau</p>
<p>Utilisateur de client VoIP Lync issu d’un site réseau inconnu</p>
<p>Utilisateur de client VoIP Lync fédéré</p></td>
</tr>
</tbody>
</table>


L’application de conférence avec routage géodépendant présente les autres caractéristiques suivantes :

  - Lorsqu’un utilisateur nֹ’est pas autorisé à rejoindre une conférence en raison des restrictions de routage géodépendant, l’appel de l’utilisateur à la conférence est rejeté et le client Lync signale que l’appel n’a pas abouti ou s’est terminé.

  - Un point de terminaison PSTN rejoignant une conférence avec des restrictions de routage géodépendant ne sera pas empêché de rejoindre la conférence quel que soit son état, si le point de terminaison rejoint la conférence via un tronçon pour lequel le routage géodépendant n’est pas activé.

  - Un système PBX connecté à un serveur de médiation via un tronçon SIP ne faisant pas sortir les appels vers le réseau téléphonique commuté est soumis aux mêmes restrictions que les utilisateurs Lync situés dans le même site réseau dans lequel la jonction SIP est définie. Par exemple, un point de terminaison PSTN peut rejoindre une conférence avec un utilisateur PBX et un utilisateur Lync si ceux-ci sont situés dans le même site réseau. Sinon, le point de terminaison PSTN n’est pas autorisé à rejoindre la conférence si l’utilisateur PBX est situé dans un autre site réseau que l’utilisateur Lync.

