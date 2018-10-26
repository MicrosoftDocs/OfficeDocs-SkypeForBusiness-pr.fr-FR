---
title: Configuration d’exemples de scénario incluant la vidéo
TOCTitle: Configuration d’exemples de scénario incluant la vidéo
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205297(v=OCS.15)
ms:contentKeyID: 49299048
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’exemples de scénario incluant la vidéo

 

_**Dernière rubrique modifiée :** 2015-03-09_

Lync 2013 ajoute de nouvelles fonctionnalités vidéo pour prendre en charge la vidéo haute définition (HD) intégrale 1920 x 1080 et la vidéo en mode Galerie. Les mesures basées sur les données des clients indiquent que la bande passante vidéo typique n’a que légèrement augmenté par rapport à Lync 2010, mais que la bande passante de flux vidéo maximal a augmenté en raison de la prise en charge HD intégrale (pour plus d’informations, voir la section « Utilisation du réseau pour le trafic multimédia » dans [Configuration requise de la bande passante pour le trafic multimédia dans Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)). Les administrateurs peuvent donc restreindre la bande passante vidéo pour certains utilisateurs (par exemple, utilisateurs dans une succursale dotée d’une capacité réseau inférieure) et offrir la meilleure qualité vidéo possible pour les autres utilisateurs (par exemple, cadres).

Le tableau suivant fournit la liste des paramètres recommandés pour configurer la vidéo pour différentes capacités réseau. Ces paramètres limiteront dans certains cas l’envoi et la réception de vidéos de résolution plus élevée (voir la colonne la plus à droite). La vidéo en mode Galerie n’est pas disponible si la configuration minimale est utilisée en raison de la faible bande passante réseau de réception maximale.

### Paramètres vidéo recommandés

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
<td><p>Meilleure</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>Égal à égal : résolution vidéo 1920 x 1080 maximum</p>
<p>Mode Galerie : jusqu’à deux vidéos de résolution 1920 x 1080 ou plusieurs vidéos de résolution inférieure</p></td>
</tr>
<tr class="even">
<td><p>Satisfaisante</p></td>
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
<td><p>True</p></td>
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

  - Les employés de la succursale bénéficient d’une qualité vidéo satisfaisante dans la cadre des appels à deux participants lorsque Lync affiche la taille de fenêtre vidéo par défaut. L’affichage de la fenêtre Lync en plein écran n’augmente pas la résolution vidéo. Pour les conférences à plusieurs participants, les employés de la succursale ne voient qu’une seule vidéo active.

