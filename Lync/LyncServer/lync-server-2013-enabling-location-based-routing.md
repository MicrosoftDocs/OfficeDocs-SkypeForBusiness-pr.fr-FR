---
title: 'Lync Server 2013: activation du routage par emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170ca1af77a84b655e90d5587fcd101cccf83c8a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a>Activation du routage par emplacement dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-04-26_

Après le déploiement d’Enterprise Voice et des régions du réseau, des sites et des sous-réseaux sont définis, vous pouvez activer le routage selon l’emplacement. Le routage basé sur l’emplacement doit être activé pour les éléments vocaux d’entreprise suivants:

  - Sites réseau

  - Configurations de Trunk

  - Stratégies de voix

  - Configuration de routage

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>Activer le routage par emplacement vers les sites réseau

Après avoir déployé Enterprise Voice et configuré les sites réseau, vous pouvez configurer le routage sur site. Tout d’abord, vous devez créer une stratégie de routage vocal pour associer le site réseau aux utilisations RTC appropriées. Lorsque vous attribuez des utilisations RTC à une stratégie de routage téléphonique, veillez à n’utiliser que des utilisations RTC associées à des itinéraires vocaux utilisant une passerelle PSTN locale vers le site ou une passerelle RTC située dans une région où les restrictions de routage basées sur l’emplacement ne sont pas nécessaires. Utilisez la commande Windows PowerShell de Lync Server, le nouveau-CsVoiceRoutingPolicy ou le panneau de configuration de Lync Server pour créer des stratégies de routage de messagerie vocale.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

Pour plus d’informations, consultez la rubrique [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).

Pour cet exemple, les commandes de tableau et Windows PowerShell suivantes montrent deux stratégies de routage de voix et leurs utilisations RTC associées définies dans ce scénario. Seuls les paramètres spécifiques au routage de géolocalisation sont inclus dans la table à des fins d’illustration.

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
<th>Politique de routage de la voix 1</th>
<th>Politique de routage de la voix 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID de la stratégie vocale</p></td>
<td><p>Politique de routage vocal de Delhi</p></td>
<td><p>Politique de routage vocale Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usages RTC</p></td>
<td><p>Utilisation de Delhi, utilisation de PBX del, utilisation du PBX HYD</p></td>
<td><p>Utilisation de Hyderabad, utilisation de PBX HYD, utilisation de PBX del</p></td>
</tr>
</tbody>
</table>

  

Ensuite, configurez le routage selon l’emplacement pour les sites réseau concernés et associez-leur des stratégies de routage de votre voix. Utilisez la commande Windows PowerShell de Lync Server, New-CsNetworkSite, pour activer le routage par emplacement et associer des stratégies de routage de messagerie à vos sites réseau qui doivent appliquer des restrictions de routage.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

Dans cet exemple, le tableau ci-dessous illustre le routage basé sur l’emplacement de deux sites réseau différents, Delhi et Hyderabad, définis dans ce scénario à l’aide de Lync Server Windows PowerShell. Seuls les paramètres spécifiques au routage de géolocalisation sont inclus dans la table à des fins d’illustration.

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
<td><p>Politique de routage de la voix</p></td>
<td><p>Politique de routage vocal de Delhi</p></td>
<td><p>Politique de routage vocale Hyderabad</p></td>
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

## <a name="enable-location-based-routing-to-trunks"></a>Activez le routage par emplacement vers les Trunks

Pour que la configuration de Trunk puisse être activée pour le routage de l’emplacement, vous devez créer une configuration de Trunk pour chaque Trunk ou chaque site réseau. Pour créer une configuration de Trunk, utilisez la commande Windows PowerShell de Lync Server, New-CsTrunkConfiguration. Si plusieurs Trunks sont associées à un système donné (c.-à-d. passerelle ou PBX), chaque configuration de Trunk doit être modifiée pour permettre de limiter le routage selon l’emplacement.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

Pour plus d’informations, reportez-vous à [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

Pour cet exemple, les commandes Windows PowerShell suivantes montrent comment créer une configuration de Trunk pour chaque Trunk dans le déploiement défini dans ce scénario.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

Une fois qu’une configuration de Trunk est configurée par Trunk, vous pouvez utiliser la commande Windows PowerShell de Lync Server, Set-CsTrunkConfiguration, pour activer le routage par emplacement vers vos lignes de Trunk qui doivent appliquer des restrictions de routage. Activez le routage basé sur l’emplacement vers les Trunks qui routent les appels vers les passerelles RTC qui routent les appels vers le RTC et associez le site réseau où se trouve la passerelle.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

Pour plus d’informations, reportez-vous à [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

Dans cet exemple, le routage basé sur l’emplacement est activé pour chaque Trunk associé aux passerelles RTC dans Delhi et Hyderabad:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

N’activez pas le routage par emplacement pour les lignes qui ne routent pas les appels vers le RTC; Toutefois, vous devez toujours associer le Trunk au site réseau où se trouve le système en tant que restrictions de routage basées sur l’emplacement doivent être appliquées pour les appels RTC atteignant des points de terminaison connectés par le biais de ce Trunk. Pour cet exemple, le routage basé sur l’emplacement n’est pas activé pour chaque Trunk associé aux systèmes PBX dans Delhi et Hyderabad:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
Les points de terminaison qui sont connectés à des systèmes qui ne routent pas les appels vers le RTC (par exemple, un PBX) présentent des restrictions similaires aux points de terminaison Lync pour le routage de l’emplacement. Cela signifie que ces utilisateurs seront en mesure de passer et de recevoir des appels vers et à partir de l’utilisateur Lync indépendamment de l’emplacement de l’utilisateur. Ils seront également en mesure de passer des appels de réception vers et à partir d’autres systèmes qui ne routent pas les appels vers le réseau PSTN (par exemple, un point de terminaison connecté à un autre système PBX), quel que soit le site du réseau auquel le système est associé. Tous les appels entrants, les appels sortants, les transferts d’appel et le transfert d’appel impliquant des points de terminaison RTC sont soumis à des conditions de routage basées sur l’emplacement. Ces appels doivent uniquement utiliser des passerelles RTC définies comme locales pour ces systèmes.

Le tableau suivant illustre la configuration de Trunk de quatre Trunks dans deux sites réseau différents: deux connectés à des passerelles RTC et deux connectés à des systèmes PBX.


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
<td><p>PstnGateway: Trunk 1 DEL-GW</p></td>
<td><p>True</p></td>
<td><p>Site 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: Trunk 2 HYD-GW</p></td>
<td><p>True</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway: Trunk 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>Site 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: Trunk 4 HYD-PBX</p></td>
<td><p>False</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>Activer le routage par emplacement vers les stratégies vocales

Pour appliquer le routage basé sur l’emplacement à des utilisateurs spécifiques, configurez la politique vocale de ces utilisateurs afin d’éviter tout contournement de la fonction d’appel RTC. Utiliser la commande Lync Server Windows PowerShell, New-CsVoicePolicy, pour créer une nouvelle stratégie vocale ou Set-CsVoicePolicy, si vous utilisez une stratégie existante, pour activer le routage sur site en prévenant le contournement du numéro RTC.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

Pour plus d’informations, reportez-vous à [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).

Pour cet exemple, les commandes de tableau et de Windows PowerShell suivantes illustrent l’activation de la fonctionnalité de prévention des appels payants RTC aux politiques vocales Delhi et Hyderabad définies dans ce scénario. Seuls les paramètres spécifiques au routage de géolocalisation sont inclus dans la table à des fins d’illustration.

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
<th>Politique vocale 1</th>
<th>Politique vocale 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID de la stratégie vocale</p></td>
<td><p>Politique vocale de Delhi</p></td>
<td><p>Politique vocale Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usages RTC</p></td>
<td><p>Utilisation de Delhi, utilisation de PBX del, utilisation du PBX HYD</p></td>
<td><p>Utilisation de Hyderabad, utilisation de PBX HYD, utilisation de PBX del</p></td>
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

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>Activer le routage en fonction de l’emplacement dans la configuration de routage

Enfin, activez globalement le routage par emplacement vers votre configuration de routage. Pour activer le routage par emplacement, utilisez la commande Windows PowerShell de Lync Server, New-CsRoutingConfiguration.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

Pour plus d’informations, consultez la rubrique [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).

<div>


> [!NOTE]  
> Lorsque le routage local doit être activé par le biais d’une configuration globale, l’ensemble de règles à appliquer ne sera appliqué qu’aux sites, utilisateurs et Trunks pour lesquels il a été configuré comme spécifié dans cette documentation.



</div>

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

