---
title: 'Lync Server 2013 : rapport détaillé des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49eb77ad61b96e9da793bab8054d1557c3d1a77a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a>Rapport détaillé des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-05_

Le rapport sur le détail de l’appel fournit un aperçu détaillé d’un appel individuel ; le rapport inclut presque toutes les mesures de qualité de l’expérience et les statistiques collectées par Lync Server, divisée en sections de rapport, telles que :

  - Informations d’appel

  - Mesures du signal et du périphérique de l’appelant

  - Mesures du signal et du périphérique de l’appelé

  - Événement client de l’appelant

  - Événement client de l’appelé

  - Flux de données audio (de l’appelant vers l’appelé)

  - Flux de données vidéo (de l’appelant vers l’appelé)

  - Flux de données audio (de l’appelé vers l’appelant)

  - Flux de données vidéo (de l’appelé vers l’appelant)

Gardez à l’esprit que les catégories et les mesures qui figurent dans un rapport donné dépendent de deux facteurs : du type de session et du type des systèmes d’extrémité utilisés dans la session. Par exemple, un appel audio ne fait l’objet d’aucune mesure de flux de données vidéo, car il n’en comporte pas. De même, il peut arriver qu’un rapport répertorie des statistiques sur l’appelant mais pas sur l’appelé. En règle générale, cela est dû au fait que l’appelé utilise un appareil non compatible SIP. La génération de statistiques à la fin d’un appel est une tâche qui incombe aux systèmes d’extrémité. Or, un téléphone cellulaire (qui n’a pas connaissance de SIP ni des statistiques SIP) n’est pas capable de fournir ce type d’information. Si vous appelez une personne et qu’elle vous répond sur son téléphone cellulaire, vous n’obtiendrez pas de rapport de ce téléphone à la fin de l’appel.

Le rapport sur le détail de l’appel s’avère particulièrement utile pour identifier les causes exactes des problèmes de qualité des médias rencontrés lors d’un appel donné.

<div>

## <a name="accessing-the-call-detail-report"></a>Accès au rapport sur le détail de l’appel

Le rapport sur le détail de l’appel est accessible à partir des rapports suivants :

  - Le [rapport d’emplacement dans Lync Server 2013](lync-server-2013-location-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)

  - Le [rapport de synthèse de la qualité des médias dans Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)

  - Le [rapport de comparaison de la qualité des médias dans Lync server 2013](lync-server-2013-media-quality-comparison-report.md) (en cliquant sur le [rapport liste des appels dans Lync Server 2013](lync-server-2013-call-list-report.md) , puis en cliquant sur la mesure détail).

  - Le [rapport de performances du serveur dans Lync server 2013](lync-server-2013-server-performance-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)

  - Le [rapport liste des appels dans Lync Server 2013](lync-server-2013-call-list-report.md) (en cliquant sur la mesure détail)

À partir du rapport sur le détail de l’appel, vous pouvez accéder au [rapport de périphérique dans Lync Server 2013](lync-server-2013-device-report.md) en cliquant sur l’une des mesures suivantes :

  - Périphérique de capture

  - Périphérique de rendu

Vous pouvez aussi accéder au Rapport de tendance générale de la qualité des médias serveur en cliquant sur la mesure Serveur Edge A/V.

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a>Utilisation optimale du rapport sur le détail de l’appel

En règle générale, le rapport sur le détail de l’appel comprend plus de 250 mesures différentes, avec notamment les éléments Dérive d’horodatage du microphone, Durée du SNR faible et Durée de l’écho au point de terminaison. Si vous ne vous rappelez pas de la fonction de l’une de ces nombreuses mesures, placez le curseur de la souris sur l’étiquette de la mesure ; vous devriez obtenir une info-bulle décrivant cette mesure.

Si vous avez des difficultés à retrouver une mesure, tapez une partie de son nom dans la zone de recherche et cliquez sur Rechercher. Par exemple, si vous ne trouvez pas la mesure Durée du SNR faible, tapez SNR dans la zone de recherche, puis cliquez sur Rechercher.

Notez que le rapport effectue uniquement le suivi des informations relatives à un appel. L’appel lui-même n’est pas enregistré.

</div>

<div>

## <a name="filters"></a>Filtres

Aucun. Vous ne pouvez pas filtrer le rapport sur le détail de l’appel.

</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau suivant liste les informations fournies dans le rapport sur le détail de l’appel pour chaque appel.

### <a name="call-detail-report-metrics"></a>Mesures du rapport sur le détail de l’appel

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
<td><p><strong>PAI de l’appelant</strong></p></td>
<td><p>Non</p></td>
<td><p>PAI (P-Asserted-Identity) de l’utilisateur qui a initié l’appel. La PAI sert à transmettre l’identité prouvée d’un utilisateur au sein d’un réseau approuvé.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI de l’appelant</strong></p></td>
<td><p>Non</p></td>
<td><p>Adresse SIP de l’utilisateur qui a initié l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Système d’extrémité de l’appelant</strong></p></td>
<td><p>Non</p></td>
<td><p>Appareil utilisé pour passer l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agent utilisateur de l’appelant</strong></p></td>
<td><p>Non</p></td>
<td><p>Logiciel utilisé sur l’appareil utilisé pour passer l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Début de l’appel</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure où l’appel a été passé.</p></td>
</tr>
<tr class="even">
<td><p><strong>Appel de contournement du serveur de médiation</strong></p></td>
<td><p>Non</p></td>
<td><p>Indique si l’appel connecté à une passerelle vocale PSTN ou IP-PBX qualifié sans passer par le serveur de médiation.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SE de l’appelant</strong></p></td>
<td><p>Non</p></td>
<td><p>Système d’exploitation de l’ordinateur de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p><strong>UC de l’appelant</strong></p></td>
<td><p>Non</p></td>
<td><p>UC installée dans l’ordinateur de l’utilisateur qui a passé l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Numéro principal de l’UC de l’appelant</strong></p></td>
<td><p>Non</p></td>
<td><p>Numéro de processeur dans l’ordinateur utilisé par la personne qui a passé l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>Vitesse de l’UC de l’appelant</strong></p></td>
<td><p>Non</p></td>
<td><p>Vitesse d’horloge de l’UC de l’ordinateur utilisé par la personne qui a initié l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Virtualisation de l’UC de l’appelant</strong></p></td>
<td><p>Non</p></td>
<td><p>Virtualisation (le cas échéant) utilisée sur l’ordinateur utilisé par la personne qui a initié l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>PAI de l’appelé</strong></p></td>
<td><p>Non</p></td>
<td><p>PAI (P-Asserted-Identity) de l’utilisateur qui a été invité à participer à l’appel. La PAI sert à transmettre l’identité prouvée d’un utilisateur au sein d’un réseau approuvé.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URI de l’appelé</strong></p></td>
<td><p>Non</p></td>
<td><p>Adresse SIP de l’utilisateur appelé.</p></td>
</tr>
<tr class="even">
<td><p><strong>Système d’extrémité de l’appelé</strong></p></td>
<td><p>Non</p></td>
<td><p>Appareil utilisé pour recevoir l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agent utilisateur de l’appelé</strong></p></td>
<td><p>Non</p></td>
<td><p>Logiciel utilisé sur l’appareil qui a reçu l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>Duration</strong></p></td>
<td><p>Non</p></td>
<td><p>Durée de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Indicateur d’avertissement de contournement de média</strong></p></td>
<td><p>Non</p></td>
<td><p>Avertissement paru quand le serveur de médiation a été contourné.</p></td>
</tr>
<tr class="even">
<td><p><strong>SE de l’appelé</strong></p></td>
<td><p>Non</p></td>
<td><p>Système d’exploitation de l’ordinateur de l’appelé.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UC de l’appelé</strong></p></td>
<td><p>Non</p></td>
<td><p>UC installée dans l’ordinateur de l’utilisateur qui a été appelé.</p></td>
</tr>
<tr class="even">
<td><p><strong>Numéro principal de l’UC de l’appelé</strong></p></td>
<td><p>Non</p></td>
<td><p>Numéro de processeur dans l’ordinateur utilisé par la personne qui a été appelée.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Vitesse de l’UC de l’appelé</strong></p></td>
<td><p>Non</p></td>
<td><p>Vitesse d’horloge de l’UC de l’ordinateur utilisé par la personne qui a été appelée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Virtualisation de l’UC de l’appelé</strong></p></td>
<td><p>Non</p></td>
<td><p>Virtualisation (le cas échéant) utilisée sur l’ordinateur utilisé par la personne qui a été appelée.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

