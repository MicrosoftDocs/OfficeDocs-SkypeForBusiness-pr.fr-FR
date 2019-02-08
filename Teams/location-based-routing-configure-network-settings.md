---
title: Configurer les paramètres réseau pour le routage basé sur l’emplacement
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer et configurer les régions réseau, sites et les sous-réseaux pour le routage basé sur un emplacement pour le routage Direct.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b99e21d172e35eb8e2ceb2aaabacee78cf45ef9
ms.sourcegitcommit: a80f26cdb91fac904e5c292c700b66af54261c62
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "29771015"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configurer les paramètres réseau pour le routage basé sur l’emplacement

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Si vous n’avez pas déjà fait, lisez [Plan Location-Based de routage pour le routage Direct](location-based-routing-plan.md) pour passer en revue les autres étapes, vous devez effectuer avant de déployer les paramètres réseau pour le routage basé sur l’emplacement.

Cet article explique comment configurer les paramètres réseau pour le routage basé sur l’emplacement. Une fois que vous déployez l’acheminement d’un système téléphonique Direct dans votre organisation, les étapes suivantes consistent à créer et configurer des régions réseau, sites réseau et sous-réseaux. Pour effectuer les étapes décrites dans cet article, vous aurez besoin de se familiariser avec les applets de commande PowerShell. Pour plus d’informations, voir [Vue d’ensemble de PowerShell équipes](teams-powershell-overview.md).

## <a name="define-network-regions"></a>Définir des régions réseau
 Une région réseau relie des différentes parties d’un réseau entre plusieurs zones géographiques. Utiliser le ``New-CsTenantNetworkRegion`` applet de commande PowerShell pour définir des régions réseau. Notez que la ``RegionID`` paramètre est un nom logique qui représente la zone géographique de la région et n’a ni dépendances restrictions et les ``CentralSite <site ID>`` paramètre est facultatif. 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

Dans cet exemple, nous créons une zone réseau nommée Inde. 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>Définir des sites réseau

Utiliser le ``New-CsTenantNetworkSitePowerShell`` applet de commande PowerShell pour définir des sites réseau. 

```
New-CsTenantNetworkSite -NetworkRegionID <region ID>  
```
Dans cet exemple, nous créons deux nouveaux sites réseau, Delhi et Hyderabad, dans la zone Inde. 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
Le tableau suivant indique les sites de réseau définis dans cet exemple. 

||Site 1 |Site 2 |
|---------|---------|---------|
|ID de site    |    Site 1 (Delhi)     |  Site 2 (Hyderabad)       |
|ID de région  |     Région 1 (Inde)    |   Région 1 (Inde)      |

## <a name="define-network-subnets"></a>Définir les sous-réseaux

Utiliser le ``New-CsTenantNetworkSubnet`` applet de commande pour définir les sous-réseaux et les associer aux sites du réseau. Chaque sous-réseau interne ne peut être associé à un site. 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
Dans cet exemple, nous créons une association entre le sous-réseau 192.168.0.0 et le site de réseau Delhi et entre le sous-réseau 192.168.1.0 et le site d’Hyderabad réseau.
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
Le tableau suivant indique les sous-réseaux définis dans cet exemple. 

||Site 1 |Site 2 |
|---------|---------|---------|
|ID de sous-réseau   |    192.168.0.0     |  192.168.1.0     |
|Masque  |     24    |   24      |
|ID de site  | Site (Delhi) | Site 2 (Hyderabad) |

Pour plusieurs sous-réseaux, vous pouvez importer un fichier CSV à l’aide d’un script, telles que les suivantes.
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
Dans cet exemple, le fichier CSV se présente comme suit :
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>Définir les sous-réseaux externes
Utiliser le ``New-CsTenantTrustedIPAddress`` applet de commande pour définir les sous-réseaux externes et les assigner au client. Vous pouvez définir un nombre illimité de sous-réseaux pour un client. 
```
New-CsTenantTrustedIPAddress -IPAddress <Subnet IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
Par exemple :
```
New-CsTenantTrustedIPAddress -IPAddress 192.168.0.1 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>Étapes suivantes
Accédez à [Activer le routage par emplacement pour le routage Direct](location-based-routing-enable.md).

### <a name="related-topics"></a>Rubriques connexes
- [Planifier le routage par emplacement pour le routage Direct](location-based-routing-plan.md)
- [Terminologie de routage basée sur l’emplacement](location-based-routing-terminology.md)
