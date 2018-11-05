---
title: 'Lync Server 2013 : Enregistrements d’utilisation RTC'
TOCTitle: enregistrements d’utilisation RTC
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412878(v=OCS.15)
ms:contentKeyID: 49298605
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enregistrements d’utilisation RTC dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La planification des enregistrements d’utilisation RTC consiste principalement à répertorier toutes les autorisations d’appel actuellement en vigueur dans votre organisation, du PDG aux travailleurs temporaires, consultants et subordonnés. Ce processus donne également la possibilité de revérifier les autorisations d’appel existantes et de les modifier. Vous pouvez créer des enregistrements d’utilisation RTC uniquement pour les autorisations qui s’appliquent aux utilisateurs Voix Entreprise prévus, mais une meilleure solution à long terme peut consister à créer des enregistrements d’utilisation RTC pour toutes les autorisations d’appel, même si certaines d’entre elles peuvent ne pas s’appliquer actuellement au groupe d’utilisateurs à activer pour Voix Entreprise. Si les autorisations d’appel changent ou que de nouveaux utilisateurs avec des autorisations d’appel différentes sont ajoutés, vous aurez déjà créé les enregistrements d’utilisation RTC requis.

Le tableau ci-dessous présente un exemple d’utilisation RTC standard :

### Enregistrements d’utilisation RTC

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut de téléphone</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Local</p></td>
<td><p>Appels locaux</p></td>
</tr>
<tr class="even">
<td><p>Longue distance</p></td>
<td><p>Appels longue distance</p></td>
</tr>
<tr class="odd">
<td><p>International</p></td>
<td><p>Appels internationaux</p></td>
</tr>
<tr class="even">
<td><p>Delhi</p></td>
<td><p>Employés à temps plein à Delhi</p></td>
</tr>
<tr class="odd">
<td><p>Redmond</p></td>
<td><p>Employés à temps plein à Redmond</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>Employés temporaires à Redmond</p></td>
</tr>
<tr class="odd">
<td><p>Zurich</p></td>
<td><p>Employés à temps plein à Zurich</p></td>
</tr>
</tbody>
</table>


Les enregistrements d’utilisation RTC n’effectuent aucune action par eux-mêmes. Pour qu’ils fonctionnent, vous devez les associer aux éléments suivants :

  - des stratégies de voix, affectées aux utilisateurs ;

  - des itinéraires, affectés aux numéros de téléphone.

Pour plus d’informations sur les stratégies de voix et les itinéraires, reportez-vous à [Stratégies de voix dans Lync Server 2013](lync-server-2013-voice-policies.md) et [Itinéraires des communications vocales dans Lync Server 2013](lync-server-2013-voice-routes.md). Pour plus d’informations sur leur création et leur configuration, reportez-vous à [Configuration des itinéraires de communications vocales pour les appels sortants dans Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).

