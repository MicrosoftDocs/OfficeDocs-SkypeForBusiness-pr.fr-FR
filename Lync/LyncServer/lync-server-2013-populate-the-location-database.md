---
title: 'Lync Server 2013: peupler la base de données d’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Populate the location database
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413069(v=OCS.15)
ms:contentKeyID: 48185939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08c1718c3d7ffdc79b82ac34016e79bf647ae6f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a>Peupler la base de données de localisation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-17_

Pour localiser automatiquement des clients sur un réseau, vous devez tout d’abord remplir la base de données d’emplacements avec un *schéma de collage* réseau, qui mappe les éléments du réseau à des adresses civiles (c’est à dire, les rues). Vous pouvez utiliser des sous-réseaux, des points d’accès sans fil, des commutateurs et des ports pour définir le schéma de collage.

Vous pouvez ajouter des adresses à la base de données d’emplacements individuellement ou par lot en utilisant un fichier CSV contenant les formats de colonne décrits dans le tableau suivant.

Si vous utilisez une passerelle ELIN, incluez-la dans le champ **CompanyName** pour chaque emplacement. Vous pouvez inclure plusieurs passerelles ELIN pour chaque emplacement, en les séparant par des points-virgules.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Élément réseau</th>
<th>Colonnes requises</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Point d’accès sans fil</strong></p></td>
<td><p>&lt;BSSID&gt;,&lt;description&gt;,&lt;emplacement&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;&gt;,... prédirectionnel</p>
<p>... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;CodePostal&gt;,&lt;Country&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Subnet</strong></p></td>
<td><p>&lt;Sous&gt;-&lt;réseau&gt;,&lt;description&gt;,&lt;emplacement&gt;,&lt;nom_société&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix,&gt;,... prédirectionnel</p>
<p>... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;CodePostal&gt;,&lt;Country&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>Port</strong></p></td>
<td><p>&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;description&gt;,&lt;emplacement&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt; HouseNumberSuffix&gt;,...</p>
<p>... &lt;Prédirectionnelle&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;ville&gt;,&lt;état&gt;,&lt;CodePostal&gt;,&lt; Pays&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Commutateur</strong></p></td>
<td><p>&lt;ChassisID&gt;,&lt;description&gt;,&lt;emplacement&gt;,&lt;nom_société&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;&gt;,... prédirectionnel</p>
<p>... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;CodePostal&gt;,&lt;Country&gt;</p></td>
</tr>
</tbody>
</table>


Si vous ne remplissez pas la base de données d’emplacements et que **Lieu obligatoire** dans la stratégie d’emplacement est défini sur **Oui** ou sur **Clause d’exclusion de responsabilité**, le client invitera l’utilisateur à entrer manuellement un emplacement.

Pour plus d’informations sur le remplissage de la base de données de localisation, voir la documentation Lync Server Management Shell pour les applets de commande suivantes:

  - **Get-CsLisSubnet**

  - **Set-CsLisSubnet**

  - Remove-CsLisSubnet

  - **Get-CsLisWirelessAccessPoint**

  - **Set-CsLisWirelessAccessPoint**

  - **Remove-CsLisWirelessAccessPoint**

  - **Get-CsLisSwitch**

  - **Set-CsLisSwitch**

  - **Remove-CsLisSwitch**

  - **Get-CsLisPort**

  - **Set-CsLisPort**

  - **Remove-CsLisPort**

<div>

## <a name="to-add-network-elements-to-the-location-database"></a>Pour ajouter des éléments réseau à la base de données d’emplacements

1.  Exécutez l’applet de commande ci-dessous pour ajouter un emplacement de sous-réseau à la base de données d’emplacements.
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Pour les passerelles ELIN, insérez l’ELIN dans le champ CompanyName. Vous pouvez inclure plusieurs ELIN. Par exemple :
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Vous pouvez également exécuter les applets de commande et utiliser le fichier « subnets.csv » pour pour mettre à jour par lot les emplacements de sous-réseau.
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  Exécutez l’applet de commande ci-dessous pour ajouter des emplacements sans fil à la base de données d’emplacements.
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    Vous pouvez également exécuter les applets de commande ci-dessous et utiliser le fichier « waps.csv » pour mettre à jour par lot les emplacements sans-fil.
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  Exécutez l’applet de commande ci-dessous pour ajouter des emplacements de commutateur à la base de données d’emplacements.
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Vous pouvez également exécuter les applets de commande ci-dessous et utiliser le fichier « switches.csv » pour mettre à jour par lot les emplacements de commutateur.
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  Exécutez l’applet de commande ci-dessous pour ajouter des emplacements de port à la base de données d’emplacements.
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    La valeur par défaut de PortIDSubType est LocallyAssigned. Vous pouvez également la définir sur InterfaceAlias ou InterfaceName
    
    Vous pouvez également exécuter les applets de commande ci-dessous et utiliser le fichier « ports.csv » pour mettre à jour par lot les emplacements de port.
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

