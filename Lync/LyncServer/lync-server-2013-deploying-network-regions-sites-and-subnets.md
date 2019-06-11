---
title: 'Lync Server 2013: déploiement de zones, de sites et de sous-réseaux réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e75c18a582be046755a54656e9f367edabdda3e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>Déploiement de zones, sites et sous-réseaux réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-03-12_

Après le déploiement d’Enterprise Voice, vous devez configurer les éléments suivants:

  - Régions réseau

  - Sites réseau

  - Sous-réseaux réseau

<div>

## <a name="define-network-regions"></a>Définir des régions réseau

Pour définir les zones du réseau, utilisez la commande Windows PowerShell de Lync Server, le nouveau-CsNetworkRegion ou le panneau de configuration de Lync Server.

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

Pour plus d’informations, reportez-vous à [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).

Pour cet exemple, la commande Windows PowerShell suivante illustre la région du réseau, région 1 (Inde), définie dans ce scénario.

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>Définir des sites réseau

Utilisez la commande Windows PowerShell de Lync Server, le nouveau-CsNetworkSite ou le panneau de configuration de Lync Server pour définir les sites réseau.

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

Pour plus d’informations, reportez-vous à [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).

Pour cet exemple, le tableau suivant et la commande Windows PowerShell Lync Server illustrent les sites réseau définis dans ce scénario. Seuls les paramètres spécifiques au routage de géolocalisation sont inclus dans la table à des fins d’illustration.

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

## <a name="define-network-subnets"></a>Définir des sous-réseaux réseau

Utilisez la commande Windows PowerShell de Lync Server, le nouveau-CsNetworkSubnet ou le panneau de configuration de Lync Server pour définir des sous-réseaux réseau et les affecter à des sites réseau.

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

Pour plus d’informations, reportez-vous à [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

Pour cet exemple, les commandes de tableau et Windows PowerShell suivantes montrent l’affectation de sous-réseaux réseau aux sites réseau, Delhi et Hyderabad définis dans ce scénario. Seuls les paramètres spécifiques au routage de géolocalisation sont inclus dans la table à des fins d’illustration.

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
<td><p>Réseau</p></td>
<td><p>24</p></td>
<td><p>24</p></td>
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


[Configuration du routage géodépendant dans Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

