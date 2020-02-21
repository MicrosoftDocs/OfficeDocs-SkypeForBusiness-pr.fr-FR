---
title: 'Lync Server 2013 : configuration des exemples de scénarios vidéo'
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
ms.openlocfilehash: 128703a39563124f6abfc4ae44143d274fd3a7c5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>Configuration d’exemples de scénarios vidéo pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Lync 2013 ajoute de nouvelles fonctionnalités de vidéo pour la prise en charge de la vidéo et de la Galerie (HD) 1920 x 1080. Les mesures basées sur les données client indiquent que la bande passante vidéo classique n’a pas été légèrement comparée à Lync 2010, mais que la bande passante de flux vidéo maximale a augmenté en raison de la prise en charge Full HD (pour plus d’informations, consultez la section « utilisation du réseau multimédia » dans la [bande passante réseau requise pour le trafic multimédia dans Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)). Les administrateurs peuvent donc restreindre la bande passante vidéo pour certains utilisateurs (par exemple, utilisateurs dans une succursale dotée d’une capacité réseau inférieure) et offrir la meilleure qualité vidéo possible pour les autres utilisateurs (par exemple, cadres).

Le tableau suivant fournit la liste des paramètres recommandés pour configurer la vidéo pour différentes capacités réseau. Ces paramètres limiteront dans certains cas l’envoi et la réception de vidéos de résolution plus élevée (voir la colonne la plus à droite). La vidéo en mode Galerie n’est pas disponible si la configuration minimale est utilisée en raison de la faible bande passante réseau de réception maximale.

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
<th>Résolution vidéo attendue pour une vidéo de bonne qualité</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Idéale</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>Égal à égal : résolution vidéo 1920 x 1080 maximum</p>
<p>Mode Galerie : jusqu’à deux vidéos de résolution 1920 x 1080 ou plusieurs vidéos de résolution inférieure</p></td>
</tr>
<tr class="even">
<td><p>Good</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>Égal à égal : résolution vidéo 1280 x 720 maximum</p>
<p>Mode Galerie : jusqu’à cinq vidéos de résolution 640 x 360</p></td>
</tr>
<tr class="odd">
<td><p>Moyenne</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>Égal à égal : résolution vidéo 960 x 540 maximum</p>
<p>Mode Galerie : jusqu’à cinq vidéos de résolution 424 x 240</p></td>
</tr>
<tr class="even">
<td><p>Minimale</p></td>
<td><p>Vrai</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>Égal à égal : résolution vidéo 424 x 240 maximum</p>
<p>Mode Galerie : non disponible</p></td>
</tr>
</tbody>
</table>


Vous pouvez utiliser les informations du tableau précédent pour déployer les nouvelles fonctionnalités de conférence vidéo HD et en mode Galerie pour certains utilisateurs dans votre organisation, tout en autorisant des résolutions vidéo différentes pour d’autres.

Dans l’exemple suivant, l’administrateur déploie les nouvelles fonctionnalités vidéo avec la meilleure qualité vidéo disponible pour les seuls cadres. Pour les employés d’une succursale dotée d’une faible capacité réseau, seule la configuration minimale du tableau précédent est déployée. Pour tous les autres employés, la configuration « Satisfaisante » est déployée.

Pour déployer les nouvelles fonctionnalités pour les cadres, l’administrateur crée la stratégie de conférence ExecutiveVideo avec les paramètres suivants :

  - VideoBitRateKB est défini sur 8 000 Kbits/s.

  - TotalReceiveVideoBitRateKB est défini sur 8 000 Kbits/s.

  - AllowMultiview est défini sur True.

  - EnableMultiviewJoin est défini sur True.

Pour les employés de la succursale, l’administrateur crée la stratégie de conférence BranchOfficeVideo avec les paramètres suivants :

  - VideoBitRateKB est défini sur 350 Kbits/s.

  - TotalReceiveVideoBitRateKB est défini sur 350 Kbits/s.

  - AllowMultiview est défini sur True.

  - EnableMultiviewJoin est défini sur False.

Pour tous les autres employés, l’administrateur crée la stratégie de conférence StandardVideo avec les paramètres suivants :

  - VideoBitRateKB est défini sur 2 500 Kbits/s.

  - TotalReceiveVideoBitRateKB est défini sur 2 500 Kbits/s.

  - AllowMultiview est défini sur True.

  - EnableMultiviewJoin est défini sur True.

L’administrateur affecte les stratégies de conférence aux utilisateurs comme suit :

  - La stratégie de conférence ExecutiveVideo est affectée aux cadres.

  - La stratégie de conférence BranchOfficeVideo est affectée à tous les employés de la succursale.

  - La stratégie de conférence StandardVideo est affectée à tous les autres employés.

Il en résulte l’expérience utilisateur suivante :

  - Toutes les conférences organisées par les utilisateurs prennent en charge le mode Galerie, mais les employés de la succursale ne peuvent pas l’utiliser.

  - Pour toutes les conférences incluant plusieurs participants, les cadres peuvent envoyer la vidéo HD intégrale 1920 x 1080 (si leur matériel et leur liaison réseau la prennent en charge) et peuvent recevoir la vidéo HD intégrale 1920 x 1080 si les clients des autres participants la prennent en charge.

  - S’ils bénéficient de résolutions inférieures par rapport aux cadres dans le cadre des conférences à plusieurs participants, les employés qui ne sont pas des cadres obtiennent tout de même une résolution satisfaisante.

  - Les employés de la filiale obtiendront une bonne qualité vidéo dans les appels à deux parties lorsque Lync affiche la taille de la fenêtre vidéo par défaut ; Toutefois, si la fenêtre Lync est agrandie en plein écran, la résolution vidéo n’augmente pas. Pour les conférences à plusieurs, les employés de la succursale ne verront qu’une seule vidéo active.

</div>

<span> </span>

</div>

</div>

</div>

