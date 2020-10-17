---
title: 'Lync Server 2013 : configuration du routage des Location-Based'
description: 'Lync Server 2013 : configuration du routage des Location-Based.'
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
ms.openlocfilehash: 080c2a3a82a8714fc35ce882b0c6cb1630552f27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570880"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Configuration du routage des Location-Based dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-12_

Lync Server 2013 CU1, le routage Location-Based est une fonctionnalité de voix entreprise. Le routage des Location-Based est une fonctionnalité de gestion des appels qui contrôle la manière dont les appels sont routés par Lync Server 2013 CU1. Elle impose des restrictions quant à la possibilité de router les appels vers des destinations PBX ou PSTN en fonction de l’emplacement de l’appelant Lync. Le routage des Location-Based applique les règles d’autorisation des appels aux appels RTC en fonction de l’emplacement réseau de l’appelant. L’emplacement de l’appelant est déterminé en fonction du site réseau associé au sous-réseau auquel l’appelant est connecté. La configuration du routage des Location-Based nécessite le déploiement d’Enterprise Voice, puis la configuration des régions réseau, des sites et des sous-réseaux. Cela permet de configurer la base pour activer le routage des Location-Based.

Avant de déployer Location-Based routage, vous devez d’abord déployer voix entreprise et configurer des régions réseau, des sites et des sous-réseaux associés sur vos sites réseau. Une fois l’opération terminée, vous pouvez configurer le routage des Location-Based. Pour connaître les étapes de configuration des régions réseau, des sites et des sous-réseaux, voir [Deploying Advanced Enterprise Voice Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

Cette section vous guide tout au long de la configuration du routage des Location-Based à l’aide de l’exemple suivant comme illustration.

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
<th>Emplacement</th>
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
<th>Emplacement</th>
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

  - [Activation du routage des Location-Based dans Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)

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

