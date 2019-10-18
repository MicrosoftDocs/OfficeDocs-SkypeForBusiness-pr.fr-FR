---
title: Configurer les paramètres de réseau pour le routage géodépendant
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer et configurer des zones, des sites et des sous-réseaux réseau pour le routage direct.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240bbce48452edf505a61830891d0fcd6a6d199d
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570698"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configurer les paramètres de réseau pour le routage géodépendant

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Si vous ne l’avez pas encore fait, lisez [la section routage en fonction de l’emplacement pour le routage direct](location-based-routing-plan.md) pour réviser les autres étapes que vous devez effectuer avant de configurer les paramètres réseau pour le routage en fonction de l’emplacement.

Cet article décrit comment configurer les paramètres réseau pour le routage sur site. Après avoir déployé le routage direct du système téléphonique au sein de votre organisation, les étapes suivantes permettent de créer et de configurer les zones du réseau, les sites réseau et les sous-réseaux réseau. Pour suivre les étapes décrites dans cet article, vous devez être familiarisé avec les applets de méthode PowerShell. Pour en savoir plus, voir [vue d’ensemble de PowerShell teams](teams-powershell-overview.md).

## <a name="define-network-regions"></a>Définir des régions réseau
 Une région réseau interconnecte diverses parties d’un réseau à plusieurs zones géographiques. Utilisez l’applet de nouvelle applet de [nouveau-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) pour définir des régions du réseau. Notez que le paramètre RegionID est un nom logique qui représente la géographie de la région et qu’il n’y a pas de dépendances ni&gt; de restrictions et que le paramètre d’ID de site CentralSite &lt;est facultatif. 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

Dans cet exemple, nous créons une région réseau nommée Inde. 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>Définir des sites réseau

Utilisez l’applet de nouvelle applet de [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) pour définir des sites réseau. 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
Dans cet exemple, nous créons deux nouveaux sites réseau, Delhi et Hyderabad, dans la région Inde. 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
Le tableau suivant indique les sites réseau définis dans cet exemple. 

||Site 1 |Site 2 |
|---------|---------|---------|
|ID de site    |    Site 1 (Delhi)     |  Site 2 (Hyderabad)       |
|ID de région  |     Région 1 (Inde)    |   Région 1 (Inde)      |

## <a name="define-network-subnets"></a>Définir des sous-réseaux réseau

Utilisez l’applet de nouvelle applet de [nouveau-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) pour définir des sous-réseaux réseau et les associer aux sites du réseau. Chaque sous-réseau interne ne peut être associé qu’à un seul site. 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
Dans cet exemple, nous créons une association entre le sous-réseau 192.168.0.0 et le site réseau de Delhi et entre le sous-réseau 2001:4898 : E8:25:844e : 926f : 85AD : DD8E et le site du réseau Hyderabad.
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
Le tableau suivant montre les sous-réseaux définis dans cet exemple. 

||Site 1 |Site 2 |
|---------|---------|---------|
|ID de sous-réseau   |    192.168.0.0     |  2001:4898 : E8:25:844e : 926f : 85AD : DD8E     |
|Réseau  |     24    |   120      |
|ID de site  | Site (Delhi) | Site 2 (Hyderabad) |

Pour plusieurs sous-réseaux, vous pouvez importer un fichier CSV à l’aide d’un script comme celui-ci.
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
Dans cet exemple, le fichier CSV ressemble à ceci :
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>Définir des sous-réseaux externes
Utilisez l’applet de nouvelle applet de [nouveau-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) pour définir des sous-réseaux externes et les affecter au client. Vous pouvez définir un nombre illimité de sous-réseaux pour un client. 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
Par exemple :
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>Étapes suivantes
Accédez à [activer le routage en fonction de l’emplacement pour le routage direct](location-based-routing-enable.md).

### <a name="related-topics"></a>Voir aussi
- [Planifier le routage géodépendant pour le routage direct](location-based-routing-plan.md)
- [Terminologie du routage géodépendant](location-based-routing-terminology.md)
