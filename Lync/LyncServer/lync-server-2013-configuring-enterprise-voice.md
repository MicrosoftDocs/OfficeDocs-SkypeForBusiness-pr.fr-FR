---
title: Configuration de Voix Entreprise dans Lync Server 2013
TOCTitle: Configuration de Voix Entreprise dans Lync Server 2013
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994041(v=OCS.15)
ms:contentKeyID: 53095459
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de Voix Entreprise dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Pour déployer Voix Entreprise, vous devez effectuer les opérations suivantes :

  - création de jonctions ;

  - définition de stratégies de voix ;

  - définition d’itinéraires des communications vocales ;

  - activation de Voix Entreprise pour les utilisateurs.

## Créer des jonctions

Vous devez définir des jonctions dans votre déploiement de Voix Entreprise. Pour le routage géodépendant, vous devez créer une configuration par jonction. Utilisez l’Lync ServerGénérateur de topologie pour définir vos jonctions et la commande Lync ServerWindows PowerShell New-CsTrunkConfiguration ou le Panneau de configuration Lync Server pour définir les configurations de jonction correspondantes. Pour plus d’informations sur l’activation du routage géodépendant sur les configurations de jonction, voir la section « Activation du routage géodépendant sur les jonctions » de la rubrique [Activation du routage géodépendant dans Lync Server 2013](lync-server-2013-enabling-location-based-routing.md). Pour cet exemple, le tableau suivant illustre les jonctions utilisées dans ce scénario.

Pour plus d’informations, voir [Définition d’autres jonctions dans le Gestionnaire de topologies dans Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom de la jonction</th>
<th>Type de système</th>
<th>Nom</th>
<th>Emplacement</th>
<th>serveur de médiation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Trunk 1 DEL-GW</p></td>
<td><p>Passerelle PSTN</p></td>
<td><p>DEL-GW</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Trunk 2 HYD-GW</p></td>
<td><p>Passerelle PSTN</p></td>
<td><p>HYD-GW</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>Trunk 3 DEL-PBX</p></td>
<td><p>PBX</p></td>
<td><p>DEL-PBX</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Trunk 4 HYD-PBX</p></td>
<td><p>PBX</p></td>
<td><p>HYD-PBX</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>



## Définir des stratégies de voix

Vous devez définir des stratégies de voix pour votre déploiement de Voix Entreprise. Vous ne devez définir une stratégie de voix pour appliquer des restrictions de routage géodépendant à un sous-ensemble d’utilisateurs que si une partie d’entre eux doit utiliser le routage géodépendant. Pour cet exemple, le tableau suivant illustre les stratégies de voix utilisées dans ce scénario. Seuls les paramètres spécifiques au routage géodépendant sont inclus dans le tableau à des fins d’illustration.

Pour plus d’informations, voir [Configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités d’appel et les privilèges dans Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Stratégie de voix 1</th>
<th>Stratégie de voix 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID de la stratégie de voix</p></td>
<td><p>Delhi voice policy</p></td>
<td><p>Hyderabad voice policy</p></td>
</tr>
<tr class="even">
<td><p>Utilisations PSTN</p></td>
<td><p>Delhi usage, PBX Del usage, PBX Hyd usage</p></td>
<td><p>Hyderabad usage, PBX Hyd usage, PBX Del usage</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>False</p></td>
<td><p>False</p></td>
</tr>
</tbody>
</table>



## Définir des itinéraires des communications vocales

Vous devez définir des itinéraires des communications vocales pour votre déploiement de Voix Entreprise. Pour cet exemple, le tableau suivant illustre les itinéraires des communications vocales utilisés dans ce scénario. Seuls les paramètres spécifiques au routage géodépendant sont inclus dans le tableau à des fins d’illustration.

Pour plus d’informations, voir [Configuration des itinéraires de communications vocales pour les appels sortants dans Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Itinéraire des communications vocales 1</th>
<th>Itinéraire des communications vocales 2</th>
<th>Itinéraire des communications vocales 3</th>
<th>Itinéraire des communications vocales 4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nom</p></td>
<td><p>Delhi route</p></td>
<td><p>Hyderabad route</p></td>
<td><p>PBX Del route</p></td>
<td><p>PBX Hyd route</p></td>
</tr>
<tr class="even">
<td><p>Utilisations PSTN</p></td>
<td><p>Delhi usage</p></td>
<td><p>Hyderabad usage</p></td>
<td><p>PBX Del usage</p></td>
<td><p>PBX Hyd usage</p></td>
</tr>
<tr class="odd">
<td><p>Jonction</p></td>
<td><p>Trunk 1 DEL-GW</p></td>
<td><p>Trunk 2 HYD-GW</p></td>
<td><p>Trunk 3 DEL-PBX</p></td>
<td><p>Trunk 4 HYD-PBX</p></td>
</tr>
</tbody>
</table>



## Activation de Voix Entreprise pour les utilisateurs

Vous devez activer Voix Entreprise pour les utilisateurs et leur affecter une stratégie de voix précédemment définie. Pour cet exemple, le tableau suivant illustre l’affectation utilisée dans ce scénario. Seuls les paramètres spécifiques au routage géodépendant sont inclus dans le tableau à des fins d’illustration.

Pour plus d’informations, voir [Activation des utilisateurs pour Voix Entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Utilisateurs de Delhi</th>
<th>Utilisateurs d’Hyderabad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Stratégie de voix associée</p></td>
<td><p>Delhi voice policy</p></td>
<td><p>Hyderabad voice policy</p></td>
</tr>
<tr class="even">
<td><p>Exemples d’utilisateur</p></td>
<td><p>DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
</tbody>
</table>



## Voir aussi

#### Autres ressources

[Configuration du routage géodépendant dans Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)

