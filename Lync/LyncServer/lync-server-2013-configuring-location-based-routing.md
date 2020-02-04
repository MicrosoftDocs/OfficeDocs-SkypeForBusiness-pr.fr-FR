---
title: 'Lync Server 2013 : Configuration du routage géodépendant'
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
ms.openlocfilehash: a0e82ae8a0dd9961bfeb9d2a513cb77b0affb2c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Configuration du routage géodépendant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-12_

Lync Server 2013 CU1, le routage selon l’emplacement est une fonctionnalité de voix entreprise. Le routage basé sur l’emplacement est une fonctionnalité de gestion des appels qui contrôle le routage des appels par Lync Server 2013 CU1. Il applique des restrictions sur la façon dont les appels peuvent être routés vers des destinations PBX ou PSTN en fonction de l’emplacement de l’appelant Lync. Le routage basé sur l’emplacement applique des règles d’autorisation d’appel aux appels RTC en fonction de l’emplacement réseau de l’appelant. L’emplacement de l’appelant est déterminé en fonction du site réseau associé au sous-réseau sur lequel est connecté l’appelant. La configuration du routage par emplacement nécessite d’abord le déploiement de voix entreprise et la configuration des régions, sites et sous-réseaux réseau. Cela permet de configurer la Fondation pour l’activation du routage par emplacement.

Avant de déployer le routage basé sur l’emplacement, vous devez d’abord déployer Enterprise Voice et configurer des régions, des sites et des sous-réseaux réseau associés sur les sites de votre réseau. Lorsque vous avez terminé, vous pouvez configurer le routage selon l’emplacement. Pour plus d’informations sur la façon de configurer des zones, des sites et des sous-réseaux, voir [déploiement de fonctionnalités avancées d’entreprise voix dans Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

Cette section vous guide dans la configuration du routage basé sur l’emplacement à l’aide de l’exemple suivant.

![Exemple de routage en fonction de l’emplacement voix entreprise](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Exemple de routage en fonction de l’emplacement voix entreprise")

  
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
<th>Lieu</th>
<th>Utilisateurs</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Delhi entreprise entreprise</p></td>
<td><p>DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Bureau d’entreprise Hyderabad</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Inconnu (c.-à-d. hôtel)</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>Private</p></td>
<td><p>Delhi entreprise entreprise</p></td>
<td><p>DEL-PBX-1, DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>Private</p></td>
<td><p>Bureau d’entreprise Hyderabad</p></td>
<td><p>HYD-PBX-1, HYD-PBX-2</p></td>
</tr>
<tr class="even">
<td><p>PSTN</p></td>
<td><p>Encore</p></td>
<td><p>RTC-1, RTC-2, RTC-3</p></td>
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
<th>SYSTEME</th>
<th>Lieu</th>
<th>Nom</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 CU1 pool</p></td>
<td><p>indifférente</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1, médiation Server</p></td>
<td><p>indifférente</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>Passerelle RTC 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>Passerelle RTC 2</p></td>
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

  - [Configuration d’Enterprise Voice dans Lync Server 2013](lync-server-2013-configuring-enterprise-voice.md)

  - [Déploiement de zones, sites et sous-réseaux réseau dans Lync Server 2013](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Activation du routage par emplacement dans Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement de fonctionnalités avancées d’entreprise voix dans Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

