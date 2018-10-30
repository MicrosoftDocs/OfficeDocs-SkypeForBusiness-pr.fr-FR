---
title: 'Lync Server 2013 : Vue d’ensemble des types d’adresse IP'
TOCTitle: Vue d’ensemble des types d’adresse IP pour Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205363(v=OCS.15)
ms:contentKeyID: 49299248
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble des types d’adresse IP pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Vous disposez de trois options lors de la configuration d’adresses IP dans Lync Server 2013. Vous pouvez configurer Lync Server 2013 pour prendre en charge uniquement IP version 4 (IPv4), uniquement IP version 6 (IPv6), ou une combinaison des deux (appelée *double pile* ). Chaque type de configuration implique certains problèmes à prendre en considération  :

  - **IPv4 uniquement**   IPv6 a été créé parce qu’il n’y a presque plus d’adresses IPv4 disponibles dans le monde. Au final, IPv6 sera entièrement pris en charge partout mais, pour l’instant, de nombreuses sociétés et périphériques avec lesquels votre entreprise peut avoir à communiquer ne prennent pas encore en charge IPv6, et ce pour encore quelque temps. Une configuration IPv4 uniquement vous permet de vous assurer que votre implémentation Lync Server peut communiquer avec la plupart des périphériques existants.

  - **IPv6 uniquement**   Inversement, une implémentation tout-IPv6 exclut, pour l’instant, la communication avec la plupart des périphériques existants.

  - **Double pile**   La double pile est un réseau où les types d’adresses IPv4 et IPv6 sont tous deux autorisés. Cette configuration est prise en charge dans Lync Server 2013, car, dans la plupart des cas, la transition de tout-IPv4 à tout-IPv6 prendra plusieurs années.

Les sections suivantes précisent la compatibilité de ces trois configurations avec différentes fonctionnalités Lync Server.

> [!NOTE]  
> La configuration client ou serveur avec IPv6 uniquement n’est prise en charge qu’à des fins de validation ou en laboratoire. La configuration IPv6 uniquement n’est pas prise en charge dans le déploiement de production.

## Enregistrement client


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Réseau de point de terminaison client</th>
<th>Réseau de serveur</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Double pile</p></td>
</tr>
<tr class="odd">
<td><p>Double pile</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Double pile</p></td>
<td><p>Double pile</p></td>
</tr>
<tr class="odd">
<td><p>Double pile</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Double pile</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


## Client P2P

Les communications P2P incluent l’audio, l’audio/vidéo, le partage d’application et le transfert de fichiers. Lorsque les deux clients sont enregistrés, les combinaisons suivantes sont prises en charge.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Point de terminaison client 1</th>
<th>Point de terminaison client 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Double pile</p></td>
</tr>
<tr class="odd">
<td><p>Double pile</p></td>
<td><p>Double pile</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Double pile</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


## Conférence

La conférence comprend l’audio/vidéo, le partage d’application et la collaboration de données (tableau blanc et partage de fichiers).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Réseau de point de terminaison client</th>
<th>Réseau de serveur</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Double pile</p></td>
</tr>
<tr class="odd">
<td><p>Double pile</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Double pile</p></td>
<td><p>Double pile</p></td>
</tr>
<tr class="odd">
<td><p>Double pile</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Double pile</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


## Serveur de médiation/RTC

Lync Server 2013 ne prend pas en charge la déviation du trafic multimédia pour les appels du réseau téléphonique commuté (RTC) si le trafic passe par une interface IPv6. Si la déviation du trafic multimédia est requise, nous recommandons que la passerelle RTC soit configurée sur IPv4.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Interface principale*</th>
<th>Interface RTC (sur le serveur de médiation)</th>
<th>Paramètre de passerelle RTC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>Double pile</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Double pile</p></td>
<td><p>Double pile</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>Double pile</p></td>
<td><p>Double pile</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


\* L’interface principale est celle qui communique avec les composants Lync Server.

## Communications P2P d’utilisateur distant

Les communications P2P avec des utilisateurs distants incluent la messagerie instantanée, l’audio/vidéo, le partage d’application et le transfert de fichiers.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Réseau d’utilisateur distant</th>
<th>Serveur Edge (périmètre externe)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Double pile</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>Double pile</p></td>
<td><p>Double pile</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Double pile</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


## Configuration des pools frontal et Edge

Le tableau ci-dessous montre la matrice de prise en charge entre le pool serveur frontal et le pool serveur Edge interne.

### Matrice de pool frontal et de pool Edge (périmètre interne)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><strong>Pool Edge : IPv4</strong></p></td>
<td><p><strong>Pool Edge : Double pile</strong></p></td>
<td><p><strong>Pool Edge : IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Pool frontal : IPv4</strong></p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool frontal : Double pile</strong></p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool frontal : IPv6</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Oui*</p></td>
</tr>
</tbody>
</table>


\* Utilisez cette combinaison uniquement dans un environnement de laboratoire.

Le tableau ci-dessous représente une matrice des combinaisons d’interfaces Edge internes et externes prises en charge.

### Matrice de pool Edge (périmètre interne) et de pool Edge (périmètre externe)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><strong>Pool Edge (périmètre externe) : IPv4</strong></p></td>
<td><p><strong>Pool Edge (périmètre externe) : Double pile</strong></p></td>
<td><p><strong>Pool Edge (périmètre externe) : IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Pool Edge (périmètre interne) : IPv4</strong></p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool Edge (périmètre interne) : Double pile</strong></p></td>
<td><p>Non</p></td>
<td><p>Oui</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool Edge (périmètre interne) : IPv6</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Oui*</p></td>
</tr>
</tbody>
</table>


\* Utilisez cette combinaison uniquement dans un environnement de laboratoire.

## Prise en charge Voix Entreprise pour IPv6 avancée

Les déploiements qui incluent le contrôle d’admission des appels (CAC), Enhanced 9-1-1 (E9-1-1), ou la déviation du trafic multimédia doivent être configurés sur une implémentation IPv4 uniquement ou double pile.

> [!NOTE]  
> Dans un déploiement en double pile, même si un client Lync se connecte à Lync Server en utilisant IPv6, Lync fera tout pour mapper une adresse IPv4 appropriée afin de prendre en charge E9-1-1.

Le service d’informations sur l’emplacement avec des adresses IPv6 n’est pas pris en charge.

La messagerie unifiée Exchange (UM) ne prend pas en charge IPv6. Pour cette fonctionnalité, assurez-vous que la résolution DNS ne renvoie pas une adresse IPv6. L’utilisation d’IPv6 peut entraîner des échecs lorsque les appels sont envoyés vers la messagerie vocale.

## Prise en charge d’autres fonctionnalités Lync Server 2013 pour IPv6

Outre les fonctionnalités et composants mentionnés ci-dessus, Lync Server 2013 prend en charge IPv6 pour les fonctionnalités suivantes :

  - **Conversation permanente**
    
    Vous configurez IPv6 pour la conversation permanente à l’aide du Générateur de topologie. Pour plus d’informations sur la configuration de la conversation permanente, reportez-vous à la documentation Déployer un serveur de conversation permanente.

  - **Rapports de qualité de l’expérience (QoE) et d’enregistrement des détails des appels**
    
    Les rapports de suivi comportent l’adresse IP telle que stockée dans la base de données du serveur de suivi, qu’elle soit de type IPv4 ou IPv6.

