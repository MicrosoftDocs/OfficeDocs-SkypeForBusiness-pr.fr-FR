---
title: Gérer votre topologie de réseau pour les fonctionnalités vocales cloud dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment configurer les paramètres réseau pour les fonctionnalités vocales cloud dans Microsoft Teams.
ms.openlocfilehash: f949016a06c9b9f5b2d0d87649a46396c8bb54d8
ms.sourcegitcommit: 5a28d052379aef67531d3023cbe4dff30dba1136
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2021
ms.locfileid: "60465774"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Gérer votre topologie de réseau pour les fonctionnalités vocales cloud dans Microsoft Teams

Si votre organisation déploie le routage basé sur l’emplacement pour le [routage](location-based-routing-plan.md) direct ou les appels d’urgence [dynamiques,](configure-dynamic-emergency-calling.md)vous devez configurer les paramètres réseau pour les utiliser avec ces fonctionnalités vocales cloud dans Microsoft Teams. Les paramètres réseau servent à déterminer l’emplacement d’un client Teams et incluent des régions réseau, des sites réseau, des sous-réseaux et des adresses IP fiables. En fonction de la fonctionnalité voix cloud et des fonctionnalités que vous déployez, vous configurez tout ou partie de ces paramètres. Pour en savoir plus sur ces termes, consultez [les paramètres réseau des fonctionnalités vocales cloud.](cloud-voice-network-settings.md)

Vous configurez les paramètres réseau sur la **page** Topologie de réseau du Centre Microsoft Teams’administration ou à l’aide Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Configurer les paramètres réseau dans le Centre Microsoft Teams’administration

Vous définissez les régions réseau, les sites réseau et les sous-réseaux sous l’onglet **Sites réseau** de la page **Topologie de** réseau. Dans cette zone, vous pouvez créer ou modifier un site réseau, associer un site à une région réseau, associer un sous-réseau au site, activer le routage en fonction de l’emplacement et affecter des stratégies d’urgence au site. Vous pouvez également ajouter des régions réseau qui peuvent être utilisées globalement pour tous les sites.

#### <a name="add-and-configure-a-network-site"></a>Ajouter et configurer un site réseau

1. Dans le navigation gauche du centre Microsoft Teams d’administration, allez à la topologie du réseau Emplacements, puis cliquez sur   >   **l’onglet Sites réseau.**
2. Cliquez **sur** Ajouter, puis entrez un nom et une description pour le site.

    ![Capture d’écran de la page Ajouter un site réseau.](media/manage-network-topology-add-site.png)

3. Pour associer le site à une région réseau, cliquez sur  Ajouter une région **réseau,** sélectionnez une région existante ou cliquez sur Ajouter pour ajouter une région, puis cliquez sur **Lien.**  
4. Pour activer Location-Based routage pour le site, activez le **routage basé sur l’emplacement.**
5. Pour affecter des stratégies de services d’urgence au site, vous pouvez :

    - Si votre organisation utilise des plans d’appels, des Connecter opérateur ou un routage direct, sous La stratégie Appels d’urgence, sélectionnez la stratégie de votre choix.
    - Si votre organisation a déployé un routage direct, dans le cadre de la stratégie de **routage** des appels d’urgence, sélectionnez la stratégie de votre choix.

6. Pour associer un sous-réseau au site, sous **Sous-réseaux,** cliquez **sur Ajouter des sous-réseaux.** Spécifiez la version IP, l’adresse IP, la plage réseau, ajoutez une description, puis cliquez sur **Appliquer.** Chaque sous-réseau doit être associé à un site spécifique.
7. Cliquez sur **Enregistrer**.

#### <a name="modify-a-network-site"></a>Modifier un site réseau

1. Dans le navigation gauche du centre Microsoft Teams d’administration, allez à la topologie du réseau Emplacements, puis cliquez sur   >   **l’onglet Sites réseau.**
2. Sélectionnez le site en cliquant à gauche du nom du site, puis cliquez sur **Modifier.**
3. A apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**

### <a name="manage-external-trusted-ip-addresses"></a>Gérer les adresses IP de confiance externes

Vous gérez les adresses IP fiables externes sous l’onglet Adresses **IP** de confiance sur la page **topologie** de réseau du Microsoft Teams d’administration. Vous pouvez ajouter un nombre illimité d’adresses IP de confiance externes.

#### <a name="add-a-trusted-ip-address"></a>Ajouter une adresse IP fiable

1. Dans le navigation gauche du centre Microsoft Teams d’administration, allez à la topologie du réseau Emplacements, puis cliquez sur l’onglet Adresses  >   **IPS** de confiance.
2. Cliquez sur **Nouveau**.
3. Dans le **volet Ajouter des adresses IP** fiables, spécifiez la version IP, l’adresse IP et la plage réseau, ajoutez une description, puis cliquez sur **Appliquer.**

    ![Capture d’écran du volet Ajouter des adresses IP fiables.](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Modifier une adresse IP fiable

1. Dans le navigation gauche du centre Microsoft Teams d’administration, allez à la topologie du réseau Emplacements, puis cliquez sur l’onglet Adresses  >   **IPS** de confiance.
2. Sélectionnez l’adresse IP en cliquant à gauche de cette adresse, puis cliquez sur **Modifier.**
3. Dans le **volet Modifier les adresses IP** fiables, a apporter les modifications de votre souhaitez, puis cliquez sur **Appliquer.**

## <a name="configure-network-settings-using-powershell"></a>Configurer les paramètres réseau à l’aide de PowerShell

Pour suivre les étapes de cette section, vous devez être familiarisé avec les cmdlets PowerShell. Pour en savoir plus, voir [Teams vue d’ensemble de PowerShell.](teams-powershell-overview.md)

### <a name="define-network-regions"></a>Définir les régions réseau

 Utilisez [l’cmdlet New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) pour définir les régions réseau. Notez que le paramètre RegionID est un nom logique qui représente la géographie de la région et ne présente aucune dépendance ou restriction et que le paramètre ID de site central est &lt; &gt; facultatif.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

Dans cet exemple, nous créons une région réseau nommée Inde.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

Voir également [Set-CsTenantNetworkRegion.](/powershell/module/skype/set-cstenantnetworkregion)

### <a name="define-network-sites"></a>Définir des sites réseau

Utilisez [l’cmdlet New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) pour définir des sites réseau. Chaque site réseau doit être associé à une région réseau.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

Dans cet exemple, nous créons deux sites réseau, Tous les deux dans la région Inde.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

Le tableau suivant indique les sites réseau définis dans cet exemple.

|&nbsp;|Site 1 |Site 2 |
|---------|---------|---------|
|Site ID    |    Site 1 (Syz)     |  Site 2 (Syz)       |
|ID de région  |     Région 1 (Inde)    |   Région 1 (Inde)      |

Voir également [Set-CsTenantNetworkRegion.](/powershell/module/skype/set-cstenantnetworksite)

### <a name="define-network-subnets"></a>Définir des sous-réseaux réseau

Utilisez la [cmdlet New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) pour définir des sous-réseaux et les associer à des sites réseau. Chaque sous-réseau ne peut être associé qu’à un seul site.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

Dans cet exemple, nous créons une association entre le sous-réseau 192.168.0.0 et le site du réseau Premièrement, ainsi qu’entre le sous-réseau 2001:4898:e8:25:844e:926f:85ad:dd8e et le site réseau Centrer network.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

Le tableau suivant indique les sous-réseaux définis dans cet exemple.

|&nbsp;|Site 1 |Site 2 |
|---------|---------|---------|
|ID de sous-réseau   |    192.168.0.0     |  2001:4898:e8:25:844e:926f:85ad:dd8e     |
|Masque  |     24    |   120      |
|Site ID  | Site (Syz) | Site 2 (Syz) |

Pour plusieurs sous-réseaux, vous pouvez importer un fichier CSV à l’aide d’un script tel que le suivant.

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

Dans cet exemple, le fichier CSV ressemble à ceci :

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


Voir également [Set-CsTenantNetworkSubnet.](/powershell/module/skype/set-cstenantnetworksubnet)


### <a name="define-external-subnets-external-trusted-ip-addresses"></a>Définir des sous-réseaux externes (adresses IP de confiance externes)

Utilisez la [cmdlet New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) pour définir des sous-réseaux externes et les affecter au client. Vous pouvez définir un nombre illimité de sous-réseaux externes pour un client.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

Par exemple :

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

Voir également [Set-CsTenantTrustedIPAddress.](/powershell/module/skype/set-cstenanttrustedipaddress)

## <a name="related-topics"></a>Sujets associés

- [Paramètres réseau pour les fonctionnalités vocales cloud dans Teams](cloud-voice-network-settings.md)
