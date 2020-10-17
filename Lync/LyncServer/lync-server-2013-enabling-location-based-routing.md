---
title: 'Lync Server 2013 : activation du routage des Location-Based'
description: 'Lync Server 2013 : activation du routage des Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7844af5792468cd5645b6b42c857c63b943c2df1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557620"
---
# <a name="enabling-location-based-routing-in-lync-server-2013"></a>Activation du routage des Location-Based dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-04-26_

Une fois que Enterprise Voice est déployé et que des régions réseau, des sites et des sous-réseaux sont définis, vous pouvez activer le routage des Location-Based. Le routage des Location-Based doit être activé pour les éléments voix entreprise suivants :

  - Sites réseau

  - Configurations de jonctions

  - Stratégies de voix

  - Configuration du routage

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>Activer le routage des Location-Based vers les sites réseau

Une fois que vous avez déployé voix entreprise, et configuré les sites réseau, vous êtes prêt à configurer le routage des Location-Based. Tout d’abord, vous créez une stratégie de routage des communications vocales pour associer le site réseau aux utilisations RTC appropriées. Lorsque vous affectez des utilisations PSTN à une stratégie de routage des communications vocales, veillez à n’utiliser que les utilisations RTC associées aux itinéraires vocaux qui utilisent une passerelle PSTN locale au site ou à une passerelle PSTN située dans une région où Location-Based des restrictions de routage ne sont pas nécessaires. Utilisez la commande Lync Server Windows PowerShell, le panneau de configuration New-CsVoiceRoutingPolicy ou Lync Server pour créer des stratégies de routage des communications vocales.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

Pour plus d’informations, consultez la rubrique [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).

Pour cet exemple, le tableau suivant et les commandes Windows PowerShell illustrent deux stratégies de routage des communications vocales et les utilisations RTC associées définies dans ce scénario. Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Stratégie de routage des communications vocales 1</th>
<th>Stratégie de routage des communications vocales 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID de stratégie de voix</p></td>
<td><p>Stratégie de routage des communications vocales de Delhi</p></td>
<td><p>Stratégie de routage des communications vocales Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Utilisations RTC</p></td>
<td><p>Utilisation de Delhi, utilisation de PBX del, utilisation de PBX HYD</p></td>
<td><p>Utilisation de Hyderabad, utilisation de la HYD PBX, utilisation de PBX del</p></td>
</tr>
</tbody>
</table>

  

Ensuite, configurez le routage des Location-Based pour les sites réseau applicables et associez-leur des stratégies de routage des communications vocales. Utilisez la commande Lync Server Windows PowerShell, New-applet csnetworksite, pour activer le routage des Location-Based et associer des stratégies de routage des communications vocales à vos sites réseau qui doivent appliquer des restrictions de routage.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

Dans cet exemple, le tableau suivant illustre le Location-Based routage de deux sites réseau différents, Delhi et Hyderabad, défini dans ce scénario à l’aide de Lync Server Windows PowerShell. Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


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
<td><p>Nom du site</p></td>
<td><p>Site 1 (Delhi)</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>Stratégie de routage vocale</p></td>
<td><p>Stratégie de routage des communications vocales de Delhi</p></td>
<td><p>Stratégie de routage des communications vocales Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Sous-réseaux</p></td>
<td><p>Sous-réseau 1 (Delhi)</p></td>
<td><p>Sous-réseau 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>Activer le routage des Location-Based vers les jonctions

Avant de pouvoir activer une configuration de jonction pour le routage de Location-Based, vous devez créer une configuration de jonction pour chaque jonction ou chaque site réseau. Utilisez la commande Lync Server Windows PowerShell, New-applet cstrunkconfiguration, pour créer une configuration de jonction. Si plusieurs jonctions sont associées à un système donné (par exemple, passerelle ou PBX), chaque configuration de tronçon doit être modifiée afin d’activer les restrictions de routage de Location-Based.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

Pour plus d’informations, consultez la rubrique [New-applet cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

Pour cet exemple, les commandes Windows PowerShell suivantes illustrent la création d’une configuration de jonction pour chaque jonction dans le déploiement défini dans ce scénario.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

Une fois qu’une configuration de jonction est configurée par jonction, vous pouvez utiliser la commande Lync Server Windows PowerShell, Set-applet cstrunkconfiguration, pour activer le routage des Location-Based vers vos jonctions qui doivent appliquer des restrictions de routage. Activez le routage des Location-Based vers des jonctions qui acheminent les appels vers des passerelles PSTN qui acheminent les appels vers le RTC, et associez le site réseau sur lequel se trouve la passerelle.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

Pour plus d’informations, consultez la rubrique [New-applet cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

Dans cet exemple, Location-Based routage est activé pour chaque jonction associée aux passerelles RTC dans Delhi et Hyderabad :

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

N’activez pas le routage des Location-Based pour les jonctions qui n’acheminent pas les appels vers le réseau téléphonique commuté (RTC). Toutefois, vous devez toujours associer la jonction au site réseau où se trouve le système comme Location-Based les restrictions de routage doivent être appliquées pour que les appels PSTN atteignent les points de terminaison connectés via cette jonction. Pour cet exemple, Location-Based routage n’est pas activé pour chaque jonction associée aux systèmes PBX dans Delhi et Hyderabad :

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
Les points de terminaison connectés aux systèmes qui n’acheminent pas les appels vers le réseau téléphonique commuté (PBX) auront des restrictions similaires à celles des points de terminaison Lync des utilisateurs activés pour le routage des Location-Based. Cela signifie que ces utilisateurs pourront passer et recevoir des appels vers et à partir de l’utilisateur de Lync indépendamment de l’emplacement de l’utilisateur. Ils peuvent également passer des appels reçus vers et à partir d’autres systèmes qui n’acheminent pas les appels vers le réseau PSTN (c’est-à-dire un point de terminaison connecté à un autre PBX), quel que soit le site réseau auquel le système est associé. Tous les appels entrants, sortants, de transfert d’appel et de transfert d’appel impliquant des points de terminaison PSTN seront soumis à des Location-Based de routage. Ces appels doivent utiliser uniquement des passerelles PSTN définies comme locales à ces systèmes.

Le tableau suivant illustre la configuration de jonction de quatre tronçons dans deux sites réseau différents : deux connectés à des passerelles PSTN et deux connectés à des systèmes PBX.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>EnableLocationRestriction</th>
<th>NetworkSiteID</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PstnGateway : jonction 1 DEL-GW</p></td>
<td><p>Vrai</p></td>
<td><p>Site 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway : jonction 2 HYD-GW</p></td>
<td><p>Vrai</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway : jonction 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>Site 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway : jonction 4 HYD-PBX</p></td>
<td><p>False</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>Activer le routage des Location-Based vers les stratégies de voix

Pour appliquer le routage de Location-Based à des utilisateurs spécifiques, configurez la stratégie de voix de ces utilisateurs afin d’empêcher le contournement de numéro de téléphone PSTN. Utilisez la commande Lync Server Windows PowerShell, New-CsVoicePolicy, pour créer une nouvelle stratégie de voix ou Set-CsVoicePolicy, si vous utilisez une stratégie existante, pour activer le routage des Location-Baseds en empêchant le contournement des appels RTC.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

Pour plus d’informations, consultez la rubrique [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).

Pour cet exemple, le tableau suivant et les commandes Windows PowerShell illustrent l’activation de la prévention du contournement payant PSTN vers les stratégies de voix Delhi et Hyderabad définies dans ce scénario. Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Stratégie de voix 1</th>
<th>Stratégie de voix 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID de stratégie de voix</p></td>
<td><p>Stratégie de voix de Delhi</p></td>
<td><p>Stratégie de voix Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Utilisations RTC</p></td>
<td><p>Utilisation de Delhi, utilisation de PBX del, utilisation de PBX HYD</p></td>
<td><p>Utilisation de Hyderabad, utilisation de la HYD PBX, utilisation de PBX del</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>Activer le routage des Location-Based dans la configuration de routage

Enfin, activez globalement le routage des Location-Based vers votre configuration de routage. Utilisez la commande Lync Server Windows PowerShell, New-CsRoutingConfiguration, pour activer le routage des Location-Based.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

Pour plus d’informations, consultez la rubrique [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).

<div>


> [!NOTE]  
> même si le routage de Location-Based doit être activé par le biais d’une configuration globale, l’ensemble de règles à appliquer n’est appliqué que pour les sites, les utilisateurs et les jonctions pour lesquels il a été configuré comme indiqué dans cette documentation.



</div>

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

