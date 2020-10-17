---
title: 'Lync Server 2013 : remplir la base de données d’emplacements'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Populate the location database
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413069(v=OCS.15)
ms:contentKeyID: 48185939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de9a5c9015dcaf83252260c89837a473a6a2291f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527971"
---
# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="a0f50-102">Remplir la base de données d’emplacements dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0f50-102">Populate the location database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0f50-103">_**Dernière modification de la rubrique :** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="a0f50-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="a0f50-p101">Pour localiser automatiquement des clients au sein d’un réseau, vous devez tout d’abord renseigner la base de données d’emplacements avec un *schéma de collage* réseau, qui mappe les éléments du réseau à des adresses civiles (c’est à dire, les rues). Vous pouvez utiliser des sous-réseaux, des points d’accès sans fil, des commutateurs et des ports pour définir le schéma de collage.</span><span class="sxs-lookup"><span data-stu-id="a0f50-p101">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses. You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="a0f50-106">Vous pouvez ajouter des adresses à la base de données d’emplacements individuellement ou par lot en utilisant un fichier CSV contenant les formats de colonne décrits dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a0f50-106">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="a0f50-p102">Si vous utilisez une passerelle ELIN, incluez-la dans le champ **CompanyName** pour chaque emplacement. Vous pouvez inclure plusieurs ELIN pour chaque emplacement, séparées par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="a0f50-p102">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0f50-109">Élément réseau</span><span class="sxs-lookup"><span data-stu-id="a0f50-109">Network Element</span></span></th>
<th><span data-ttu-id="a0f50-110">Colonnes requises</span><span class="sxs-lookup"><span data-stu-id="a0f50-110">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0f50-111"><strong>Point d’accès sans fil</strong></span><span class="sxs-lookup"><span data-stu-id="a0f50-111"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="a0f50-112">&lt;BSSID &gt; , &lt; description &gt; , &lt; location &gt; , &lt; CompanyName &gt; , &lt; HouseNumber &gt; , &lt; HouseNumberSuffix &gt; , &lt; &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="a0f50-112">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="a0f50-113">... &lt; StreetName &gt; , &lt; StreetSuffix &gt; , &lt; PostDirectional &gt; , &lt; ville &gt; , &lt; état &gt; , &lt; CodePostal &gt; , &lt; pays&gt;</span><span class="sxs-lookup"><span data-stu-id="a0f50-113">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f50-114"><strong>Subnet</strong></span><span class="sxs-lookup"><span data-stu-id="a0f50-114"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="a0f50-115">&lt;Sous-réseau &gt; , &lt; description &gt; , &lt; emplacement &gt; , &lt; CompanyName &gt; , &lt; HouseNumber &gt; , &lt; HouseNumberSuffix &gt; , &lt; &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="a0f50-115">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="a0f50-116">... &lt; StreetName &gt; , &lt; StreetSuffix &gt; , &lt; PostDirectional &gt; , &lt; ville &gt; , &lt; état &gt; , &lt; CodePostal &gt; , &lt; pays&gt;</span><span class="sxs-lookup"><span data-stu-id="a0f50-116">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f50-117"><strong>Port</strong></span><span class="sxs-lookup"><span data-stu-id="a0f50-117"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="a0f50-118">&lt;ChassisID &gt; , &lt; PortIDSubType &gt; , &lt; PortID &gt; , &lt; description &gt; , &lt; location &gt; , &lt; CompanyName &gt; , &lt; HouseNumber &gt; , &lt; HouseNumberSuffix &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="a0f50-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="a0f50-119">... &lt; Predirection &gt; , &lt; StreetName &gt; , &lt; StreetSuffix &gt; , &lt; PostDirectional &gt; , &lt; ville &gt; , &lt; état &gt; , &lt; CodePostal &gt; , &lt; pays&gt;</span><span class="sxs-lookup"><span data-stu-id="a0f50-119">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f50-120"><strong>Commutateur</strong></span><span class="sxs-lookup"><span data-stu-id="a0f50-120"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="a0f50-121">&lt;ChassisID &gt; , &lt; description &gt; , &lt; location &gt; , &lt; CompanyName &gt; , &lt; HouseNumber &gt; , &lt; HouseNumberSuffix &gt; , &lt; &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="a0f50-121">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="a0f50-122">... &lt; StreetName &gt; , &lt; StreetSuffix &gt; , &lt; PostDirectional &gt; , &lt; ville &gt; , &lt; état &gt; , &lt; CodePostal &gt; , &lt; pays&gt;</span><span class="sxs-lookup"><span data-stu-id="a0f50-122">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a0f50-123">Si vous ne renseignez pas la base de données d’emplacements et que **Lieu obligatoire** dans la stratégie d’emplacement est défini sur **Oui** ou sur **Clause d’exclusion de responsabilité**, le client invitera l’utilisateur à entrer un emplacement manuellement.</span><span class="sxs-lookup"><span data-stu-id="a0f50-123">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="a0f50-124">Pour plus d’informations sur le remplissage de la base de données d’emplacements, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="a0f50-124">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="a0f50-125">**Get-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="a0f50-125">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="a0f50-126">**Set-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="a0f50-126">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="a0f50-127">Remove-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="a0f50-127">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="a0f50-128">**Get-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="a0f50-128">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="a0f50-129">**Set-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="a0f50-129">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="a0f50-130">**Remove-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="a0f50-130">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="a0f50-131">**Get-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="a0f50-131">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="a0f50-132">**Set-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="a0f50-132">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="a0f50-133">**Remove-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="a0f50-133">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="a0f50-134">**Get-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="a0f50-134">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="a0f50-135">**Set-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="a0f50-135">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="a0f50-136">**Remove-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="a0f50-136">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="a0f50-137">Pour ajouter des éléments réseau à la base de données d’emplacements</span><span class="sxs-lookup"><span data-stu-id="a0f50-137">To add network elements to the location database</span></span>

1.  <span data-ttu-id="a0f50-138">Exécutez la cmdlet suivante pour ajouter un emplacement de sous-réseau à la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="a0f50-138">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="a0f50-p103">Pour les passerelles ELIN, placez l’ELIN dans le champ CompanyName. Vous pouvez inclure plusieurs ELIN. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a0f50-p103">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="a0f50-142">Vous pouvez également exécuter les cmdlets et utiliser un fichier nommé « subnets.csv » pour pour mettre à jour par lot les emplacements de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="a0f50-142">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="a0f50-143">Exécutez la cmdlet suivante pour ajouter des emplacements sans fil à la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="a0f50-143">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="a0f50-144">Vous pouvez également exécuter les cmdlets suivantes et utiliser un fichier nommé « waps.csv » pour mettre à jour par lot les emplacements sans-fil.</span><span class="sxs-lookup"><span data-stu-id="a0f50-144">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="a0f50-145">Exécutez la cmdlet suivante pour ajouter des emplacements de commutateur à la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="a0f50-145">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="a0f50-146">Vous pouvez également exécuter les cmdlets suivantes et utiliser un fichier nommé « switches.csv » pour mettre à jour par lot les emplacements de commutateur.</span><span class="sxs-lookup"><span data-stu-id="a0f50-146">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="a0f50-147">Exécutez la cmdlet suivante pour ajouter des emplacements de port à la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="a0f50-147">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="a0f50-p104">La valeur par défaut de PortIDSubType est LocallyAssigned. Vous pouvez également la définir sur InterfaceAlias ou InterfaceName</span><span class="sxs-lookup"><span data-stu-id="a0f50-p104">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="a0f50-150">Vous pouvez également exécuter les cmdlets suivantes et utiliser un fichier nommé « ports.csv » pour mettre à jour par lot les emplacements de port.</span><span class="sxs-lookup"><span data-stu-id="a0f50-150">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

