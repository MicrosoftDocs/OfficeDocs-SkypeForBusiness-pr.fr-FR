---
title: "Lync Server 2013 : Planification du routage des communications voc. sortantes"
TOCTitle: Planification du routage des communications vocales sortantes
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425853(v=OCS.15)
ms:contentKeyID: 49296874
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification du routage des communications vocales sortantes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le routage des appels sortants s’applique aux appels destinés à une passerelle RTC, une jonction SIP ou un système PBX. Lorsqu’un utilisateur passe un appel, le serveur normalise le numéro de téléphone au format E.164 et tente de le faire correspondre à un URI SIP. Si le serveur ne parvient pas à établir de correspondance, il applique la logique de routage des appels sortants en fonction de la chaîne de numérotation fournie. Les paramètres de serveur du tableau ci-dessous permettent de configurer la logique de routage des appels sortants.

### Paramètres de routage des appels sortants Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Objet</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Plan de numérotation</p></td>
<td><p>Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels.</p></td>
</tr>
<tr class="even">
<td><p>Règle de normalisation</p></td>
<td><p>Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont acheminés vers chaque emplacement, utilisateur ou objet contact. La même chaîne de numérotation peut être interprétée et convertie différemment selon l’emplacement d’origine de la numérotation et la personne ou l’objet contact passant l’appel. Un ensemble de règles de normalisation associées à un emplacement particulier constitue un plan de numérotation.</p></td>
</tr>
<tr class="odd">
<td><p>Stratégie de voix</p></td>
<td><p>Une stratégie de voix associe un ou plusieurs enregistrements d’utilisation RTC à un utilisateur ou groupe d’utilisateurs. Elle fournit également une liste de fonctionnalités d’appel que vous pouvez activer ou désactiver.</p></td>
</tr>
<tr class="even">
<td><p>Enregistrement d’utilisation RTC</p></td>
<td><p>Un enregistrement d’utilisation PTSN indique une classe d’appel (interne, local ou longue distance) qui peut être passée par différents utilisateurs, ou groupes d’utilisateurs, dans une organisation.</p></td>
</tr>
<tr class="odd">
<td><p>Itinéraire d’appel</p></td>
<td><p>Un itinéraire d’appel associe les numéros de téléphone cibles à des jonctions et des enregistrements d’utilisation PTSN spécifiques. Une passerelle RTC est considérée comme une jonction.</p></td>
</tr>
</tbody>
</table>


## Dans cette section

Cette section explique comment configurer les paramètres serveur de routage des appels sortants suivants :

  - [Plans de numérotation et règles de normalisation dans Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)

  - [Stratégies de voix dans Lync Server 2013](lync-server-2013-voice-policies.md)

  - [Enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-pstn-usage-records.md)

  - [Itinéraires des communications vocales dans Lync Server 2013](lync-server-2013-voice-routes.md)

## Voir aussi

#### Concepts

[Jonction SIP dans Lync Server 2013](lync-server-2013-sip-trunking.md)  
[Connexions SIP directes dans Lync Server 2013](lync-server-2013-direct-sip-connections.md)

