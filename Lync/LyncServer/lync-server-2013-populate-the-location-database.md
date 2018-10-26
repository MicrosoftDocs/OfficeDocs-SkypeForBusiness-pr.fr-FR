---
title: Renseigner la base de données d’emplacements
TOCTitle: Renseigner la base de données d’emplacements
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413069(v=OCS.15)
ms:contentKeyID: 49299422
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Renseigner la base de données d’emplacements

 

_**Dernière rubrique modifiée :** 2015-03-09_

Pour localiser automatiquement des clients au sein d’un réseau, vous devez tout d’abord renseigner la base de données d’emplacements avec un *schéma de collage* réseau, qui mappe les éléments du réseau à des adresses civiles (c’est à dire, les rues). Vous pouvez utiliser des sous-réseaux, des points d’accès sans fil, des commutateurs et des ports pour définir le schéma de collage.

Vous pouvez ajouter des adresses à la base de données d’emplacements individuellement ou par lot en utilisant un fichier CSV contenant les formats de colonne décrits dans le tableau suivant.

Si vous utilisez une passerelle ELIN, incluez-la dans le champ **CompanyName** pour chaque emplacement. Vous pouvez inclure plusieurs ELIN pour chaque emplacement, séparées par un point-virgule.


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
<td><p>&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</p>
<p>…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Sous-réseau</strong></p></td>
<td><p>&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</p>
<p>…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>Port</strong></p></td>
<td><p>&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</p>
<p>…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Commutateur</strong></p></td>
<td><p>&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</p>
<p>…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</p></td>
</tr>
</tbody>
</table>


Si vous ne renseignez pas la base de données d’emplacements et que **Lieu obligatoire** dans la stratégie d’emplacement est défini sur **Oui** ou sur **Clause d’exclusion de responsabilité**, le client invitera l’utilisateur à entrer un emplacement manuellement.

Pour plus d’informations sur le renseignement de la base de données d’emplacements, voir la documentation Lync Server Management Shell pour les cmdlets suivantes :

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

## Pour ajouter des éléments réseau à la base de données d’emplacements

1.  Exécutez la cmdlet suivante pour ajouter un emplacement de sous-réseau à la base de données d’emplacements.
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Pour les passerelles ELIN, placez l’ELIN dans le champ CompanyName. Vous pouvez inclure plusieurs ELIN. Par exemple :
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Vous pouvez également exécuter les cmdlets et utiliser un fichier nommé « subnets.csv » pour pour mettre à jour par lot les emplacements de sous-réseau.
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  Exécutez la cmdlet suivante pour ajouter des emplacements sans fil à la base de données d’emplacements.
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    Vous pouvez également exécuter les cmdlets suivantes et utiliser un fichier nommé « waps.csv » pour mettre à jour par lot les emplacements sans-fil.
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  Exécutez la cmdlet suivante pour ajouter des emplacements de commutateur à la base de données d’emplacements.
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Vous pouvez également exécuter les cmdlets suivantes et utiliser un fichier nommé « switches.csv » pour mettre à jour par lot les emplacements de commutateur.
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  Exécutez la cmdlet suivante pour ajouter des emplacements de port à la base de données d’emplacements.
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    La valeur par défaut de PortIDSubType est LocallyAssigned. Vous pouvez également la définir sur InterfaceAlias ou InterfaceName
    
    Vous pouvez également exécuter les cmdlets suivantes et utiliser un fichier nommé « ports.csv » pour mettre à jour par lot les emplacements de port.
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

