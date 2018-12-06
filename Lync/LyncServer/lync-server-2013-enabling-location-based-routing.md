---
title: Activation du routage géodépendant dans Lync Server 2013
TOCTitle: Activation du routage géodépendant dans Lync Server 2013
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994014(v=OCS.15)
ms:contentKeyID: 53095349
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation du routage géodépendant dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Une fois que Voix Entreprise est déployé et que les régions réseau, sites réseau et sous-réseaux sont définis, vous pouvez activer le routage géodépendant. Cette fonctionnalité doit être activée pour les éléments Voix Entreprise suivants :

  - sites réseau ;

  - configurations de jonction ;

  - stratégies de voix ;

  - configuration du routage.

## Activation du routage géodépendant sur les sites réseau

Une fois que vous avez déployé Voix Entreprise et configuré les sites réseau, vous êtes prêt à configurer le routage géodépendant. Vous devez commencer par créer une stratégie de routage des communications vocales afin d’associer le site réseau aux utilisations PSTN appropriées. Lorsque vous affectez des utilisations PSTN à une stratégie de routage des communications vocales, veillez à n’utiliser que les utilisations PSTN associées aux itinéraires de communications vocales qui utilisent une passerelle PSTN locale sur le site ou une passerelle PSTN située dans une région dans laquelle les restrictions de routage géodépendant ne sont pas nécessaires. Utilisez la commande Lync ServerWindows PowerShell New-CsVoiceRoutingPolicy ou le Panneau de configuration Lync Server pour créer les stratégies de routage des communications vocales.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

Pour plus d’informations, voir [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsVoiceRoutingPolicy).

Pour cet exemple, le tableau suivant et les commandes Windows PowerShell illustrent deux stratégies de routage des communications vocales et les utilisations PSTN associées définies dans ce scénario. Seuls les paramètres spécifiques au routage géodépendant sont inclus dans le tableau à des fins d’illustration.

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
<th>Stratégie de routage des communications vocales 1</th>
<th>Stratégie de routage des communications vocales 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID de la stratégie de voix</p></td>
<td><p>Delhi voice routing policy</p></td>
<td><p>Hyderabad voice routing policy</p></td>
</tr>
<tr class="even">
<td><p>Utilisations PSTN</p></td>
<td><p>Delhi usage, PBX Del usage, PBX Hyd usage</p></td>
<td><p>Hyderabad usage, PBX Hyd usage, PBX Del usage</p></td>
</tr>
</tbody>
</table>

  

Vous devez ensuite configurer le routage géodépendant pour les sites réseau applicables et associer vos stratégies de routage des communications vocales à ceux-ci. Utilisez la commande Lync ServerWindows PowerShell New-CsNetworkSite pour activer le routage géodépendant et associer les stratégies de routage des communications vocales à vos sites réseau devant appliquer les restrictions de routage.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

Dans cet exemple, le tableau suivant illustre le routage géodépendant pour deux sites réseau (Delhi et Hyderabad) définis dans ce scénario à l’aide de Lync ServerWindows PowerShell. Seuls les paramètres spécifiques au routage géodépendant sont inclus dans le tableau à des fins d’illustration.

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
<th>Site 1 (Delhi)</th>
<th>Site 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nom du site</p></td>
<td><p>Site 1 (Delhi)</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>Stratégie de routage des communications vocales</p></td>
<td><p>Delhi voice routing policy</p></td>
<td><p>Hyderabad voice routing policy</p></td>
</tr>
<tr class="even">
<td><p>Sous-réseaux</p></td>
<td><p>Subnet 1 (Delhi)</p></td>
<td><p>Subnet 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>



## Activation du routage géodépendant sur les jonctions

Avant qu’une configuration de jonction ne puisse être activée pour le routage géodépendant, vous devez créer une configuration pour chaque jonction ou site réseau. Utilisez la commande Lync ServerWindows PowerShell New-CsTrunkConfiguration pour créer une configuration de jonction. Si plusieurs jonctions sont associées à un système donné (passerelle ou PBX), chaque configuration de jonction doit être modifiée pour activer les restrictions de routage géodépendant.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

Pour plus d’informations, voir [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration).

Pour cet exemple, les commandes Windows PowerShell suivantes illustrent la création d’une configuration pour chaque jonction dans le déploiement défini dans ce scénario.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

Une fois qu’une configuration est définie pour chaque jonction, vous pouvez utiliser la commande Lync ServerWindows PowerShell Set-CsTrunkConfiguration pour activer le routage géodépendant sur vos jonctions devant appliquer les restrictions de routage. Vous devez activer le routage géodépendant sur les jonctions qui acheminent les appels vers les passerelles PSTN et associer le site réseau sur lequel la passerelle est située.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

Pour plus d’informations, voir [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration).

Dans cet exemple, le routage géodépendant est activé pour chaque jonction associée à des passerelles PSTN à Delhi et Hyderabad :

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

Vous ne devez pas activer le routage géodépendant pour les jonctions n’acheminant pas d’appels vers le réseau téléphonique commuté. Vous devez tout de même associer la jonction au site réseau dans lequel se trouve le système, car les restrictions de routage géodépendant doivent être appliquées pour les appels PSTN atteignant des points de terminaison connectés via cette jonction. Pour cet exemple, le routage géodépendant n’est pas activé pour chaque jonction associée à des systèmes PBX à Delhi et Hyderabad :

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
Les points de terminaison connectés à des systèmes n’acheminant pas d’appels vers le réseau téléphonique commuté (PBX) auront des restrictions semblables à celles des points de terminaison Lync des utilisateurs pour lesquels le routage géodépendant est activé. Ces utilisateurs pourront passer et recevoir des appels via Lync quel que soit leur emplacement. Ils pourront également passer et recevoir des appels via d’autres systèmes n’acheminant pas d’appels vers le réseau téléphonique commuté (point de terminaison connecté à un autre PBX) quel que soit le site réseau auquel le système est associé. Les restrictions de routage géodépendant seront appliquées à tous les appels entrants, appels sortants, transferts d’appel et renvois d’appel impliquant des points de terminaison PSTN. Les appels ne doivent utiliser que les passerelles PSTN définies comme locales pour ces systèmes.

Le tableau suivant illustre la configuration de quatre jonctions dans deux sites réseau : deux connectés aux passerelles PSTN et deux connectés aux systèmes PBX.


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
<td><p>PstnGateway:Trunk 1 DEL-GW</p></td>
<td><p>True</p></td>
<td><p>Site 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway:Trunk 2 HYD-GW</p></td>
<td><p>True</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway:Trunk 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>Site 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway:Trunk 4 HYD-PBX</p></td>
<td><p>False</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>



## Activation du routage géodépendant sur les stratégies de routage des communications vocales

Pour activer le routage géodépendant pour des utilisateurs spécifiques, vous devez configurer la stratégie de voix de ceux-ci afin d’empêcher le contournement des frais de réseau téléphonique commuté. Utilisez la commande Lync ServerWindows PowerShell New-CsVoicePolicy pour créer une stratégie de voix ou Set-CsVoicePolicy, si vous utilisez une stratégie existante, pour activer le routage géodépendant en empêchant le contournement des frais de réseau téléphonique commuté.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

Pour plus d’informations, voir [New-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsVoicePolicy).

Pour cet exemple, le tableau suivant et les commandes Windows PowerShell illustrent l’activation de la prévention du contournement des frais de réseau téléphonique commuté sur les stratégies de voix de Delhi et d’Hyderabad définies dans le scénario. Seuls les paramètres spécifiques au routage géodépendant sont inclus dans le tableau à des fins d’illustration.

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
<th>Stratégie de voix 1</th>
<th>Stratégie de voix 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID de la stratégie de voix</p></td>
<td><p>Delhi voice policy</p></td>
<td><p>Hyderabad voice policy</p></td>
</tr>
<tr class="even">
<td><p>Utilisations PSTN</p></td>
<td><p>Delhi usage, PBX Del usage, PBX Hyd usage</p></td>
<td><p>Hyderabad usage, PBX Hyd usage, PBX Del usage</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
</tbody>
</table>



## Activation du routage géodépendant dans la configuration du routage

Enfin, activez globalement le routage géodépendant sur votre configuration du routage. Utilisez la commande Lync ServerWindows PowerShell New-CsRoutingConfiguration pour activer le routage géodépendant.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

Pour plus d’informations, voir [Set-CsRoutingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRoutingConfiguration).

> [!NOTE]  
> Si le routage géodépendant doit être activé via une configuration globale, l’ensemble de règles devant être appliqué ne le sera que pour les sites, utilisateurs et jonctions pour lesquels il a été configuré, comme spécifié dans cette documentation.


## Voir aussi

#### Autres ressources

[Configuration du routage géodépendant dans Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)

