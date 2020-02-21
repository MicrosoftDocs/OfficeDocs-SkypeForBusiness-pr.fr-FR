---
title: 'Lync Server 2013 : vue d’ensemble des types d’adresses IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 417b304825da6a611ccfdaf3521b2d9571cd4756
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Vue d’ensemble des types d’adresses IP pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-29_

Vous disposez de trois options lors de la configuration des adresses IP dans Lync Server 2013. Vous pouvez configurer Lync Server 2013 pour prendre en charge uniquement IP version 4 (IPv4), uniquement IP version 6 (IPv6), ou une combinaison des deux (appelée *double pile*). Il existe plusieurs problèmes à prendre en compte pour chaque type de configuration :

  - **IPv4 uniquement**   IPv6 a été créé car le monde a des adresses IPv4 insuffisantes. Au final, IPv6 sera entièrement pris en charge dans le monde entier, mais pour l’instant, de nombreuses sociétés et appareils dont votre entreprise peut avoir besoin de communiquer ne prennent pas encore en charge IPv6, et peuvent ne pas prendre du temps. Une configuration IPv4 uniquement permet de s’assurer que votre implémentation Lync Server peut communiquer avec la plupart des périphériques existants.

  - **IPv6 uniquement**   inversement, une implémentation complète d’IPv6, à ce stade, exclut la communication avec de nombreux appareils existants.

  - **La double**   pile double pile est un réseau où les adresses IPv4 et IPv6 sont activées. Cette configuration est prise en charge dans Lync Server 2013 car, dans la plupart des cas, la transition de Full-IPv4 à Full-IPv6 prend plusieurs années.

Les sections suivantes décrivent la compatibilité entre ces trois configurations pour différentes fonctionnalités Lync Server.

<div>


> [!NOTE]  
> La configuration du client ou du serveur avec IPv6 uniquement n’est prise en charge qu’à des fins de validation ou de laboratoire. La configuration IPv6 uniquement n’est pas prise en charge dans le déploiement de production.



</div>

<div>

## <a name="client-registration"></a>Inscription du client


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Réseau de point de terminaison client</th>
<th>Réseau de serveurs</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Double pile</p></td>
</tr>
<tr class="odd">
<td><p>Double pile</p></td>
<td><p>IPv6</p></td>
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

## <a name="peer-to-peer-client"></a>Client d’égal à égal

Les communications d’égal à égal incluent l’audio, l’audio/vidéo, le partage d’application et le transfert de fichiers. Une fois que les deux clients ont été correctement enregistrés, les combinaisons suivantes sont prises en charge.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Point de terminaison du client 1</th>
<th>Point de terminaison client 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
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

## <a name="conferencing"></a>Vidéoconférence

La Conférence comprend l’audio/vidéo, le partage d’application et la collaboration de données (tableau blanc et partage de fichiers).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Réseau de point de terminaison client</th>
<th>Réseau de serveurs</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Double pile</p></td>
</tr>
<tr class="odd">
<td><p>Double pile</p></td>
<td><p>IPv6</p></td>
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

Lync Server 2013 ne prend pas en charge la déviation du trafic multimédia pour les appels de réseau téléphonique commuté (PSTN) si le trafic se fait via une interface IPv6. Si la déviation du trafic multimédia est requise, nous vous recommandons de configurer la passerelle PSTN sur IPv4.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Interface principale *</th>
<th>Interface PSTN (sur le serveur de médiation)</th>
<th>Paramètre de passerelle PSTN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>Double pile</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>Double pile</p></td>
<td><p>Double pile</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="odd">
<td><p>Double pile</p></td>
<td><p>Double pile</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


\*L’interface principale est l’interface qui communique avec les composants Lync Server.

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>Communications P2P des utilisateurs distants

Les communications P2P avec des utilisateurs distants incluent la messagerie instantanée, l’audio/vidéo, le partage d’application et le transfert de fichiers.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Réseau d’utilisateurs distants</th>
<th>Serveur Edge (périmètre externe)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>Double pile</p></td>
<td><p>IPv6</p></td>
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

## <a name="front-end-pool-and-edge-pool-configuration"></a>Configuration des pools frontaux et des pools de serveurs Edge

Le tableau suivant montre la matrice de prise en charge entre le pool de serveurs frontaux et le pool de serveurs Edge interne.

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>Matrice des pools frontaux et des pools de serveurs Edge (périmètre interne)

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
<td><p><strong>Pool de serveurs Edge : double pile</strong></p></td>
<td><p><strong>Pool de serveurs Edge : IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Pool frontal : IPv4</strong></p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool frontal : double pile</strong></p></td>
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


\*Utilisez cette combinaison uniquement dans un environnement de laboratoire.

Le tableau suivant est une matrice des combinaisons d’interfaces Edge internes et externes prises en charge.

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
<td><p><strong>Pool Edge (périmètre externe) : double pile</strong></p></td>
<td><p><strong>Pool Edge (périmètre externe) : IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Pool Edge (périmètre interne) : IPv4</strong></p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool Edge (périmètre interne) : double pile</strong></p></td>
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


\*Utilisez cette combinaison uniquement dans un environnement de laboratoire.

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>Prise en charge avancée de voix entreprise pour IPv6

Les déploiements qui incluent le contrôle d’admission des appels (CAC), Enhanced 9-1-1 (E9-1-1) ou la déviation du trafic multimédia doivent être configurés en tant que protocole IPv4 uniquement ou en tant qu’implémentation à double pile.

<div>


> [!NOTE]  
> Dans un déploiement à double pile, même si un client Lync se connecte à un serveur Lync à l’aide D’ipv6, Lync permettra de mapper une adresse IPv4 appropriée pour prendre en charge E9-1-1.



</div>

Le service d’informations d’emplacement avec des adresses IPv6 n’est pas pris en charge.

La messagerie unifiée Exchange ne prend pas en charge IPv6. Pour la messagerie unifiée Exchange, assurez-vous que la résolution DNS ne renvoie pas une adresse IPv6. L’utilisation D’ipv6 peut entraîner un échec lorsque des appels sont envoyés à la messagerie vocale.

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>Autres fonctionnalités de prise en charge de Lync Server 2013 pour IPv6

Outre les fonctionnalités et composants mentionnés précédemment, Lync Server 2013 prend en charge IPv6 pour les fonctionnalités suivantes :

  - **Conversation permanente**
    
    Vous configurez IPv6 pour la conversation permanente à l’aide du générateur de topologie. Pour plus d’informations sur la configuration de la conversation permanente, voir la documentation sur le déploiement du serveur de conversation permanente.

  - **Rapports sur la qualité de l’expérience et l’enregistrement des détails des appels (CDR)**
    
    Les rapports de surveillance incluent l’adresse IP telle qu’elle est stockée dans la base de données du serveur de surveillance, qu’elle soit de type IPv4 ou IPv6.

</div>

</div>

<span> </span>

</div>

</div>

</div>

