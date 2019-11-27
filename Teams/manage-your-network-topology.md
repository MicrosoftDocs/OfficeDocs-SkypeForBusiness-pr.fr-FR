---
title: Gérer la topologie de votre réseau pour les fonctionnalités vocales de Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1keywords: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment configurer les paramètres réseau pour les fonctionnalités vocales de Microsoft Teams.
ms.openlocfilehash: 72fb40b31b7881f550800bad5a2d2fca304431ae
ms.sourcegitcommit: 021c86bf579e315f15815dcddf232a0c651cbf6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615894"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Gérer la topologie de votre réseau pour les fonctionnalités vocales de Microsoft teams

Si votre organisation déploie le [routage de géolocalisation pour le routage direct](location-based-routing-plan.md) ou les [appels d’urgence dynamiques](configure-dynamic-emergency-calling.md), vous devez configurer des paramètres réseau pour ces fonctionnalités de voix Cloud dans Microsoft Teams. Les paramètres réseau permettent de déterminer l’emplacement d’un client teams et d’inclure des régions réseau, des sites réseau, des sous-réseaux et des adresses IP approuvées. En fonction de la fonctionnalité voix sur le Cloud et des fonctionnalités que vous déployez, vous configurez l’ensemble ou une partie de ces paramètres. Pour en savoir plus sur ces conditions, voir [paramètres réseau pour les fonctionnalités vocales](cloud-voice-network-settings.md)dans le Cloud.

Vous pouvez configurer les paramètres réseau dans la page **topologie du réseau** du centre d’administration Microsoft teams ou à l’aide de Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Configurer les paramètres réseau dans le centre d’administration Microsoft teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Vous définissez les zones du réseau, les sites réseau et les sous-réseaux sous l’onglet **sites du réseau** de la page **topologie du réseau** . Dans cette section, vous pouvez créer ou modifier un site réseau, associer un site à une région réseau, associer un sous-réseau au site, activer le routage basé sur l’emplacement et affecter des stratégies d’urgence au site. Vous pouvez également ajouter des régions réseau qui peuvent être utilisées globalement pour tous les sites.

#### <a name="add-and-configure-a-network-site"></a>Ajouter et configurer un site réseau

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **emplacements** > **réseau**, puis cliquez sur l’onglet **sites du réseau** .
2. Cliquez sur **nouveau**, puis tapez un nom et une description pour le site.

    ![Capture d’écran de la page Ajouter un site réseau](media/manage-network-topology-add-site.png)

3. Pour associer le site à une région du réseau, cliquez sur **lier la région du réseau**, sélectionnez une région existante ou cliquez sur **Ajouter** pour ajouter une région, puis cliquez sur **lien**.  
4. Pour activer le routage en fonction de l’emplacement du site, activez le **routage selon l’emplacement**.
5. Pour attribuer des stratégies de services d’urgence au site, effectuez l’une des opérations suivantes ou les deux :

    - Si votre organisation utilise des plans d’appel ou du routage direct du système téléphonique, sous **stratégie d’appel d’urgence**, sélectionnez la stratégie de votre choix.
    - Si votre organisation a déployé le routage direct du système téléphonique, sous **stratégie d’acheminement des appels d’urgence**, sélectionnez la stratégie de votre choix.

6. Pour associer un sous-réseau au site, sous **sous-réseaux**, cliquez sur Ajouter des sous- **réseaux**. Spécifiez la version IP, l’adresse IP, la plage réseau, ajoutez une description, puis cliquez sur **appliquer**. Chaque sous-réseau doit être associé à un site spécifique.
7. Cliquez sur **Enregistrer**.

#### <a name="modify-a-network-site"></a>Modifier un site réseau

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **emplacements** > **réseau**, puis cliquez sur l’onglet **sites du réseau** .
2. Sélectionnez le site en cliquant à gauche du nom du site, puis cliquez sur **modifier**.
3. Apportez les modifications souhaitées, puis cliquez sur **Enregistrer.**

### <a name="manage-external-trusted-ip-addresses"></a>Gérer les adresses IP de confiance externes

Pour gérer les adresses IP de confiance externes, accédez à l’onglet **IPS approuvés** de la page **Topology Network** du centre d’administration Microsoft Teams. Vous pouvez ajouter un nombre illimité d’adresses IP de confiance externes.

#### <a name="add-a-trusted-ip-address"></a>Ajouter une adresse IP de confiance

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **emplacements** > **réseau**, puis cliquez sur l’onglet **IPS approuvés** .
2. Cliquez sur **Nouveau**.
3. Dans le volet **Ajouter une adresse IP approuvée** , spécifiez la version IP, l’adresse IP, la plage réseau, ajoutez une description, puis cliquez sur **appliquer**.

    ![Capture d’écran du volet ajouter une adresse IP approuvée](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Modifier une adresse IP de confiance

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **emplacements** > **réseau**, puis cliquez sur l’onglet **IPS approuvés** .
2. Sélectionnez l’adresse IP en cliquant à gauche de celle-ci, puis cliquez sur **modifier**.
3. Dans le volet **modifier l’adresse IP de confiance** , apportez les modifications souhaitées, puis cliquez sur **appliquer**.

## <a name="configure-network-settings-using-powershell"></a>Configurer les paramètres réseau à l’aide de PowerShell

Pour suivre les étapes décrites dans cette section, vous devez vous familiariser avec les applets de cmdlet PowerShell. Pour en savoir plus, voir [vue d’ensemble de PowerShell teams](teams-powershell-overview.md).

### <a name="define-network-regions"></a>Définir des régions réseau

 Utilisez l’applet de nouvelle applet de [nouveau-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) pour définir des régions du réseau. Notez que le paramètre RegionID est un nom logique qui représente la géographie de la région et qu’il n’y a pas de dépendances ni&gt; de restrictions et que le paramètre d’ID de site CentralSite &lt;est facultatif.

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

Dans cet exemple, nous créons une région réseau nommée Inde.
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

Voir également [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).

### <a name="define-network-sites"></a>Définir des sites réseau

Utilisez l’applet de nouvelle applet de [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) pour définir des sites réseau. Chaque site réseau doit être associé à une région réseau.

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

Voir également [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).

### <a name="define-network-subnets"></a>Définir des sous-réseaux réseau

Utilisez l’applet de nouvelle applet de [nouveau-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) pour définir des sous-réseaux réseau et les associer aux sites du réseau. Chaque sous-réseau ne peut être associé qu’à un seul site.

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

Voir également [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).

### <a name="define-external-subnets-external-trusted-ip-addresses"></a>Définir des sous-réseaux externes (adresses IP de confiance externes)

Utilisez l’applet de nouvelle applet de [nouveau-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) pour définir des sous-réseaux externes et les affecter au client. Vous pouvez définir un nombre illimité de sous-réseaux externes pour un client.
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
Par exemple :
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

Voir également [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).

## <a name="related-topics"></a>Voir aussi

- [Paramètres réseau pour les fonctionnalités vocales de Cloud dans teams](cloud-voice-network-settings.md)
