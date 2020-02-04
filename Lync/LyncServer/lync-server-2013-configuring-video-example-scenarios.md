---
title: 'Lync Server 2013 : configuration de scénarios d’exemples vidéo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd47056b97da1ba3ac1bf884cc3e8bd9aaf43f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>Configuration de scénarios d’exemples vidéo pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Lync 2013 ajoute de nouvelles fonctionnalités vidéo pour la prise en charge des vidéos d’affichage de la vidéo HD 1920 x 1080. Les mesures sur la base des données client indiquent que la bande passante vidéo type n’est plus légèrement comparée à Lync 2010, mais que la bande passante maximale de la bande passante augmente en raison de la prise en charge complète HD (pour plus de détails, voir la section « utilisation du réseau du trafic multimédia » dans les [exigences de bande passante réseau de Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)). Les administrateurs peuvent donc vouloir limiter la bande passante vidéo pour certains utilisateurs (par exemple, les utilisateurs d’une succursale qui ont moins de capacités réseau) et permettent de garantir la meilleure qualité vidéo possible pour les autres utilisateurs (comme les dirigeants).

Le tableau suivant répertorie les paramètres recommandés pour la configuration de la vidéo pour différentes capacités du réseau. Ces paramètres restreignent certains scénarios d’utilisation et de réception de vidéos de haute résolution (voir la colonne la plus à droite). Le paramètre minimum entraîne l’indisponibilité de la vidéo de la galerie en raison de la bande passante réseau faible de réception.

### <a name="recommended-video-settings"></a>Paramètres vidéo recommandés

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th>AllowMultiView</th>
<th>EnableMultiViewJoin</th>
<th>VideoBitRateKB</th>
<th>TotalReceiveVideoBitRateKB</th>
<th>Résolution vidéo prévue pour une vidéo de qualité optimale</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Optimal</p></td>
<td><p>Vrai</p></td>
<td><p>Vrai</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>Poste à poste : résolution vidéo de 1920 x 1080</p>
<p>Affichage Galerie : jusqu’à 2 1920 x 1080 vidéos ou plusieurs vidéos de résolution réduite</p></td>
</tr>
<tr class="even">
<td><p>Good</p></td>
<td><p>Vrai</p></td>
<td><p>Vrai</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>Poste à poste : résolution vidéo de 1280 x 720</p>
<p>Vue Galerie : vidéo de résolution de 5 640 x 360</p></td>
</tr>
<tr class="odd">
<td><p>Moyen</p></td>
<td><p>Vrai</p></td>
<td><p>Vrai</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>Poste à poste : résolution vidéo de 960 x 540</p>
<p>Vue Galerie : vidéo de résolution de 5 424 x 240</p></td>
</tr>
<tr class="even">
<td><p>Requise</p></td>
<td><p>Vrai</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>Poste à poste : résolution vidéo de 424 x 240</p>
<p>Affichage Galerie : indisponible</p></td>
</tr>
</tbody>
</table>


Vous pouvez utiliser les informations contenues dans le tableau ci-dessus pour déployer les nouvelles fonctionnalités de visioconférence et de vidéoconférence HD pour certains utilisateurs de votre organisation, tout en autorisant des résolutions vidéo différentes pour les autres utilisateurs.

Dans l’exemple suivant, l’administrateur déploie les nouvelles fonctions vidéo avec la meilleure qualité vidéo disponible uniquement aux dirigeants. Pour les employés d’une succursale distante disposant d’une faible capacité réseau, le paramètre minimum du tableau précédent est déployé. Pour tous les autres employés, le paramètre « Good » du tableau précédent est déployé.

Pour déployer les nouvelles fonctionnalités aux dirigeants, l’administrateur crée une stratégie de conférence nommée ExecutiveVideo. Cette stratégie de conférence a les paramètres suivants :

  - VideoBitRateKB est défini sur 8000 kbps

  - TotalReceiveVideoBitRateKB est défini sur 8000 kbps

  - AllowMultiview est défini sur true.

  - EnableMultiviewJoin est défini sur true.

Pour les employés de la succursale, l’administrateur crée une stratégie de conférence nommée BranchOfficeVideo. Cette stratégie de conférence a les paramètres suivants :

  - VideoBitRateKB est défini sur 350 kbps

  - TotalReceiveVideoBitRateKB est défini sur 350 kbps

  - AllowMultiview est défini sur true.

  - EnableMultiviewJoin est défini sur false.

Pour tous les autres employés, l’administrateur crée une stratégie de conférence nommée StandardVideo. Cette stratégie de conférence a les paramètres suivants :

  - VideoBitRateKB est défini sur 2500 kbps

  - TotalReceiveVideoBitRateKB est défini sur 2500 kbps

  - AllowMultiview est défini sur true.

  - EnableMultiviewJoin est défini sur true.

L’administrateur affecte la stratégie de conférence aux utilisateurs comme suit :

  - La stratégie de conférence ExecutiveVideo est affectée aux dirigeants.

  - La stratégie de conférence BranchOfficeVideo est affectée à tous les employés de l’succursale.

  - La stratégie de conférence StandardVideo est affectée à tous les autres employés.

Ces attributions de stratégie de conférence génèrent l’interface utilisateur suivante :

  - Toutes les conférences organisées par tout type d’affichage Galerie de support utilisateur, mais les employés dans la succursale ne peuvent pas accéder à l’affichage Galerie.

  - Dans le cadre d’une conférence à deux ou à plusieurs, les dirigeants peuvent envoyer une vidéo HD HD de 1920 x 1080, si leur matériel et leur lien réseau le prennent en charge, et qu’ils peuvent recevoir une vidéo HD de 1920 x 1080, au sein desquels les autres clients participants le prennent en charge.

  - Les employés qui ne sont pas des dirigeants disposent de résolutions plus basses que celles des dirigeants dans leurs conférences à deux ou à plusieurs, mais ils continuent à utiliser une bonne résolution.

  - Les employés qui se trouvent dans la succursale disposent d’une bonne qualité vidéo dans les appels à deux participants lorsque Lync affiche la taille de la fenêtre vidéo par défaut ; Toutefois, si la fenêtre Lync est agrandie en plein écran, la résolution vidéo n’augmentera pas. Dans le cadre de conférences à plusieurs, les employés de la succursale ne verront qu’une vidéo active.

</div>

<span> </span>

</div>

</div>

</div>

