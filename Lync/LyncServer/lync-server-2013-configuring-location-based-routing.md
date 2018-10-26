---
title: 'Lync Server 2013 : Configuration du routage géodépendant'
TOCTitle: Configuration du routage géodépendant
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994036(v=OCS.15)
ms:contentKeyID: 53095438
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du routage géodépendant dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le routage géodépendant de Lync Server 2013 CU1 est une fonctionnalité de gestion des appels de Voix Entreprise qui contrôle l’acheminement des appels par Lync Server 2013 CU1. Elle restreint l’acheminement des appels vers des destinations PBX ou RTC sur la base de l’emplacement de l’appelant Lync. Le routage géodépendant applique des règles d’autorisation d’appels aux appels RTC sur la base de l’emplacement réseau de l’appelant. L’emplacement de l’appelant est déterminé en fonction du site réseau associé au sous-réseau sur lequel l’appelant est connecté. La configuration du routage géodépendant nécessite de commencer par déployer Voix Entreprise, puis de configurer les régions réseau, sites réseau et sous-réseaux. Cela permet de définir les bases pour l’activation du routage géodépendant.

Avant de déployer le routage géodépendant, vous devez commencer par déployer Voix Entreprise, configurer les régions réseau et sites réseau, puis associer des sous-réseaux à vos sites réseau. Lorsque vous avez terminé, vous pouvez configurer le routage géodépendant. Pour plus d’informations sur la configuration des régions réseau, sites réseau et sous-réseaux, reportez-vous à [Déploiement des fonctionnalités avancées de Voix Entreprise dans Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

Cette section vous guide tout au long de la configuration du routage géodépendant en utilisant l’exemple suivant à des fins d’illustration.

![Exemple de routage basé sur l’emplacement Voix Entreprise](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Exemple de routage basé sur l’emplacement Voix Entreprise")

  
Le tableau ci-dessous présente les utilisateurs définis dans cet exemple.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de point de terminaison</th>
<th>Emplacement</th>
<th>Utilisateurs</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Agence de Delhi</p></td>
<td><p>DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Agence d’Hyderabad</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Inconnu (par exemple, hôtel)</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>Agence de Delhi</p></td>
<td><p>DEL-PBX-1, DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>Agence d’Hyderabad</p></td>
<td><p>HYD-PBX-1, HYD-PBX-2</p></td>
</tr>
<tr class="even">
<td><p>RTC</p></td>
<td><p>Inconnu</p></td>
<td><p>RTC-1, RTC-2, RTC-3</p></td>
</tr>
</tbody>
</table>

  

Le tableau ci-dessous présente les systèmes illustrés dans cet exemple d’environnement.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Système</th>
<th>Emplacement</th>
<th>Nom</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Pool Lync Server 2013 CU1</p></td>
<td><p>Quelconque</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1, serveur de médiation</p></td>
<td><p>Quelconque</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>Passerelle RTC 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>Passerelle RTC 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>HYD-GW</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>RED-PBX</p></td>
</tr>
</tbody>
</table>


## Dans cette section

  - [Configuration de Voix Entreprise dans Lync Server 2013](lync-server-2013-configuring-enterprise-voice.md)

  - [Déploiement des régions réseau, sites réseau et sous-réseaux dans Lync Server 2013](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Activation du routage géodépendant dans Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)

## Voir aussi

#### Autres ressources

[Déploiement des fonctionnalités avancées de Voix Entreprise dans Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

