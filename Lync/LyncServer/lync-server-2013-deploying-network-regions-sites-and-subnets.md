---
title: 'Lync Server 2013 : déploiement des régions réseau, des sites et des sous-réseaux'
description: 'Lync Server 2013 : déploiement des régions réseau, des sites et des sous-réseaux.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1c4c08cd9b78b1439000cdb4a7bbe3ffc2f99d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561090"
---
# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>Déploiement des régions réseau, des sites et des sous-réseaux dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-12_

Une fois Enterprise Voice déployé, vous devez configurer les éléments suivants :

  - Régions réseau

  - Sites réseau

  - Sous-réseaux de réseau

<div>

## <a name="define-network-regions"></a>Définir les régions réseau

Utilisez la commande Lync Server Windows PowerShell, le panneau de configuration New-applet csnetworkregion ou Lync Server pour définir les régions réseau.

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

Pour plus d’informations, consultez la rubrique [New-applet csnetworkregion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).

Pour cet exemple, la commande Windows PowerShell suivante illustre la région réseau, région 1 (Inde), définie dans ce scénario.

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>Définir les sites réseau

Utilisez la commande Lync Server Windows PowerShell, New-applet csnetworksite ou le panneau de configuration Lync Server pour définir les sites réseau.

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

Pour plus d’informations, consultez la rubrique [New-applet csnetworksite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).

Pour cet exemple, le tableau suivant et la commande Lync Server Windows PowerShell illustrent les sites réseau définis dans ce scénario. Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Site 1 (Delhi)</th>
<th>Site 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID de site</p></td>
<td><p>Site 1 (Delhi)</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>ID de région</p></td>
<td><p>Région 1 (Inde)</p></td>
<td><p>Région 1 (Inde)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a>Définir des sous-réseaux

Utilisez la commande Lync Server Windows PowerShell, New-CsNetworkSubnet ou le panneau de configuration Lync Server pour définir des sous-réseaux réseau et les affecter aux sites réseau.

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

Pour plus d’informations, consultez la rubrique [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

Pour cet exemple, le tableau suivant et les commandes Windows PowerShell illustrent l’affectation de sous-réseaux réseau aux sites réseau, Delhi et Hyderabad, définis dans ce scénario. Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Site 1 (Delhi)</th>
<th>Site 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID de sous-réseau</p></td>
<td><p>192.168.0.0</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>Masque</p></td>
<td><p>heures/24</p></td>
<td><p>heures/24</p></td>
</tr>
<tr class="odd">
<td><p>ID de site</p></td>
<td><p>Site 1 (Delhi)</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration du routage des Location-Based dans Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

