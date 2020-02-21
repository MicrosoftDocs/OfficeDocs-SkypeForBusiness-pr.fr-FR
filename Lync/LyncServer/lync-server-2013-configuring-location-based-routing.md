---
title: 'Lync Server 2013 : configuration du routage géodépendant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b88df8bf0b8362a09ea2e5b779b7fa9d789a0a48
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Configuration du routage géodépendant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-12_

Lync Server 2013 CU1, le routage géodépendant est une fonctionnalité de voix entreprise. Le routage géodépendant est une fonctionnalité de gestion des appels qui contrôle la manière dont les appels sont routés par Lync Server 2013 CU1. Elle impose des restrictions quant à la possibilité de router les appels vers des destinations PBX ou PSTN en fonction de l’emplacement de l’appelant Lync. Le routage géodépendant applique des règles d’autorisation d’appels aux appels RTC en fonction de l’emplacement réseau de l’appelant. L’emplacement de l’appelant est déterminé en fonction du site réseau associé au sous-réseau auquel l’appelant est connecté. La configuration du routage géodépendant nécessite le déploiement d’Enterprise Voice, puis la configuration des régions réseau, des sites et des sous-réseaux. Cela configure les bases de l’activation du routage géodépendant.

Avant de déployer le routage géodépendant, vous devez d’abord déployer voix entreprise et configurer des régions réseau, des sites et des sous-réseaux associés sur vos sites réseau. Une fois terminé, vous pouvez configurer le routage géodépendant. Pour connaître les étapes de configuration des régions réseau, des sites et des sous-réseaux, voir [Deploying Advanced Enterprise Voice Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

Cette section vous guide tout au long de la configuration du routage géodépendant en utilisant l’exemple suivant comme illustration.

![Exemple de routage basé sur l’emplacement de voix entreprise](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Exemple de routage basé sur l’emplacement de voix entreprise")

  
Le tableau suivant représente les utilisateurs définis dans cet exemple.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de point de terminaison</th>
<th>L’emplacement</th>
<th>Utilisateurs</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Siège social de Delhi</p></td>
<td><p>DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Bureau d’entreprise Hyderabad</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Inconnu (c.-à-d. Hotel)</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>Siège social de Delhi</p></td>
<td><p>DEL-PBX-1, DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>Bureau d’entreprise Hyderabad</p></td>
<td><p>HYD-PBX-1, HYD-PBX-2</p></td>
</tr>
<tr class="even">
<td><p>RTC</p></td>
<td><p>Inconnu</p></td>
<td><p>PSTN-1, PSTN-2, PSTN-3</p></td>
</tr>
</tbody>
</table>

  

Le tableau suivant représente les systèmes illustrés dans cet exemple d’environnement.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Système</th>
<th>L’emplacement</th>
<th>Nom</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 CU1 pool</p></td>
<td><p>indifférent</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1, serveur de médiation</p></td>
<td><p>indifférent</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>Passerelle PSTN 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>Passerelle PSTN 2</p></td>
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
<td><p>PBX ROUGE</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration de voix entreprise dans Lync Server 2013](lync-server-2013-configuring-enterprise-voice.md)

  - [Déploiement des régions réseau, des sites et des sous-réseaux dans Lync Server 2013](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Activation du routage géodépendant dans Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement des fonctionnalités avancées de voix entreprise dans Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

