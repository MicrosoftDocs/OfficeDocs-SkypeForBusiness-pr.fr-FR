---
title: 'Lync Server 2013 : Vue d’ensemble des types d’adresse IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90d31045879c4e6f488c232687346ed0413ef62b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Vue d’ensemble des types d’adresse IP pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-01-29_

Trois options s’offrent à vous lorsque vous configurez les adresses IP dans Lync Server 2013. Vous pouvez configurer Lync Server 2013 de manière à prendre en charge uniquement le protocole IP version 4 (IPv4), uniquement le protocole IPv4 version 6 (IPv6) ou une combinaison des deux (appelé *pile double*). Chaque type de configuration implique certains problèmes à prendre en considération :

  - **IPv4 uniquement**   IPv6 a été créé, car le monde ne dispose plus d’adresses IPv4. Au final, IPv6 sera entièrement pris en charge partout mais, pour l’instant, de nombreuses sociétés et périphériques avec lesquels votre entreprise peut avoir à communiquer ne prennent pas encore en charge IPv6, et ce pour encore quelque temps. Une configuration IPv4 uniquement permet de s’assurer que votre implémentation Lync Server peut communiquer avec la plupart des appareils existants.

  - ****   Pour le moment, le protocole IPv6 ne peut pas être associé à de nombreux périphériques existants.

  - ****   Stack Double Stack est un réseau sur lequel les adresses IPv4 et IPv6 sont activées. Cette configuration est prise en charge dans Lync Server 2013, car dans la plupart des cas, le passage de l’intégralité du protocole IPv4 au protocole IPv6 complet nécessite plusieurs années.

Les sections suivantes décrivent la compatibilité entre ces trois configurations pour différentes fonctionnalités de Lync Server.

<div>


> [!NOTE]  
> La configuration client ou serveur avec IPv6 uniquement n’est prise en charge qu’à des fins de validation ou en laboratoire. La configuration IPv6 uniquement n’est pas prise en charge dans le déploiement de production.



</div>

<div>

## <a name="client-registration"></a>Enregistrement client


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


</div>

<div>

## <a name="peer-to-peer-client"></a>Client P2P

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


</div>

<div>

## <a name="conferencing"></a>Téléconférence

Les conférences incluent l’audio/la vidéo, le partage d’application et la collaboration sur les données (tableau blanc et partage de fichiers).


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


</div>

<div>

## <a name="mediation-serverpstn"></a>Serveur de médiation/RTC

Lync Server 2013 ne prend pas en charge la dérivation multimédia pour les appels de réseau téléphonique commuté (PSTN) si le trafic provient d’une interface IPv6. Si la déviation du trafic multimédia est requise, nous recommandons que la passerelle RTC soit configurée sur IPv4.


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


\*L’interface principale est l’interface qui communique avec les composants serveur Lync.

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>Communications P2P d’utilisateur distant

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


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a>Configuration des pools frontal et Edge

Le tableau suivant montre la matrice de prise en charge entre le pool de serveurs frontal et le pool de serveurs Edge interne.

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>Matrice de pool frontal et de pool Edge (périmètre interne)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
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
<td><p>Oui </p></td>
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


\*Utilisez cette combinaison uniquement dans un environnement Lab.

Le tableau ci-dessous représente une matrice des combinaisons d’interfaces Edge internes et externes prises en charge.

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a>Matrice de pool Edge (périmètre interne) et de pool Edge (périmètre externe)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
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


\*Utilisez cette combinaison uniquement dans un environnement Lab.

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>Prise en charge Voix Entreprise pour IPv6 avancée

Les déploiements qui incluent le service Contrôle d’admission des appels (CAC), Enhanced 9-1-1 (E9-1-1), ou la déviation du trafic multimédia doivent être configurés sur une implémentation IPv4 uniquement ou double pile.

<div>


> [!NOTE]  
> Dans un déploiement à double empilage, même si un client Lync se connecte à un serveur Lync à l’aide du protocole IPv6, Lync fera tout particulièrement un effort pour mapper une adresse IPv4 appropriée à la prise en charge de E9-1-1.



</div>

Le service d’information d’emplacement avec les adresses IPv6 n’est pas pris en charge.

La messagerie unifiée Exchange (UM) ne prend pas en charge IPv6. Pour cette fonctionnalité, assurez-vous que la résolution DNS ne renvoie pas une adresse IPv6. L’utilisation d’IPv6 peut entraîner des échecs lorsque les appels sont envoyés vers la messagerie vocale.

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>Autres fonctionnalités de Lync Server 2013 prises en charge pour IPv6

Outre les fonctionnalités et composants mentionnés précédemment, Lync Server 2013 prend en charge le protocole IPv6 pour les fonctionnalités suivantes:

  - **Conversation permanente**
    
    Vous pouvez configurer le protocole IPv6 pour une conversation permanente à l’aide du générateur de topologie. Pour plus d’informations sur la configuration d’une conversation permanente, voir la documentation déploiement d’un serveur de chat permanent.

  - **Rapports de qualité de l’expérience (QoE) et d’enregistrement des détails des appels**
    
    Les rapports de suivi comportent l’adresse IP telle que stockée dans la base de données du serveur de suivi, qu’elle soit de type IPv4 ou IPv6.

</div>

</div>

<span> </span>

</div>

</div>

</div>

