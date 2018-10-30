---
title: "Dépl. des régions réseau, sites réseau et sous-réseaux dans Lync Server 2013"
TOCtitle: "Dépl. des régions réseau, sites réseau et sous-réseaux dans Lync Server 2013"
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994067(v=OCS.15)
ms:contentKeyID: 53095526
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement des régions réseau, sites réseau et sous-réseaux dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Une fois que Voix Entreprise est déployée, vous devez configurer les éléments suivants :

  - régions réseau ;

  - sites réseau ;

  - sous-réseaux.

## Définir les régions réseau

Utilisez la commande Lync ServerWindows PowerShell New-CsNetworkRegion ou le Panneau de configuration Lync Server pour définir les régions réseau.

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

Pour plus d’informations, voir [New-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegion).

Pour cet exemple, la commande Windows PowerShell suivante illustre la région réseau region 1 (India) définie dans ce scénario.

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"


## Définir les sites réseau

Utilisez la commande Lync ServerWindows PowerShell New-CsNetworkSite ou le Panneau de configuration Lync Server pour définir les sites réseau.

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

Pour plus d’informations, voir [New-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSite).

Pour cet exemple, le tableau suivant et la commande Lync ServerWindows PowerShell illustrent les sites réseau définis dans ce scénario. Seuls les paramètres spécifiques au routage géodépendant sont inclus dans le tableau à des fins d’illustration.

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
<th>Site 1 (Delhi)</th>
<th>Site 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID de site</p></td>
<td><p>Site 1 (Delhi)</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>ID de région</p></td>
<td><p>Region 1 (India)</p></td>
<td><p>Region 1 (India)</p></td>
</tr>
</tbody>
</table>



## Définir les sous-réseaux

Utilisez la commande Lync ServerWindows PowerShell New-CsNetworkSubnet ou le Panneau de configuration Lync Server pour définir les sous-réseaux et les affecter aux sites réseau.

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

Pour plus d’informations, voir [New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet).

Pour cet exemple, le tableau suivant et les commandes Windows PowerShell illustrent l’affectation de sous-réseaux aux sites réseau Delhi et Hyderabad définis dans ce scénario. Seuls les paramètres spécifiques au routage géodépendant sont inclus dans le tableau à des fins d’illustration.

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
<th>Site 1 (Delhi)</th>
<th>Site 2 (Hyderabad)</th>
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
<td><p>24</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>ID de site</p></td>
<td><p>Site 1 (Delhi)</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>



## Voir aussi

#### Autres ressources

[Configuration du routage géodépendant dans Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)

