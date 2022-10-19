---
title: Gérer la topologie de votre réseau pour les fonctionnalités de voix cloud dans Microsoft Teams
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
- highpri
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment configurer des paramètres réseau pour les fonctionnalités de voix cloud dans Microsoft Teams.
ms.openlocfilehash: a75ce05a29df84bb46cb430016e1a3453e96b64e
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584245"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Gérer la topologie de votre réseau pour les fonctionnalités de voix cloud dans Microsoft Teams

Si votre organisation déploie le [routage basé sur l’emplacement pour le routage direct](location-based-routing-plan.md) ou les [appels d’urgence dynamiques](configure-dynamic-emergency-calling.md), vous devez configurer les paramètres réseau à utiliser avec ces fonctionnalités de voix cloud dans Microsoft Teams. Les paramètres réseau sont utilisés pour déterminer l’emplacement d’un client Teams et inclure des régions réseau, des sites réseau, des sous-réseaux et des adresses IP approuvées. En fonction de la fonctionnalité de voix cloud et de la fonctionnalité que vous déployez, vous configurez certains ou tous ces paramètres. Pour en savoir plus sur ces termes, consultez [Paramètres réseau pour les fonctionnalités de voix cloud](cloud-voice-network-settings.md).

Vous configurez les paramètres réseau sur la page **De topologie réseau** du Centre d’administration Microsoft Teams ou à l’aide de Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Configurer les paramètres réseau dans le Centre d’administration Microsoft Teams

Vous définissez des régions réseau, des sites réseau et des sous-réseaux sous l’onglet **Sites réseau** de la page **Topologie réseau** . Ici, vous pouvez créer ou modifier un site réseau, associer un site à une région réseau, associer un sous-réseau au site, activer le routage basé sur l’emplacement et affecter des stratégies d’urgence au site. Vous pouvez également ajouter des régions réseau qui peuvent être utilisées globalement pour tous les sites.

#### <a name="add-and-configure-a-network-site"></a>Ajouter et configurer un site réseau

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à la **topologie réseau** **Emplacements** > , puis cliquez sur l’onglet **Sites réseau**.
2. Cliquez sur **Ajouter**, puis entrez un nom et une description pour le site.

    ![Capture d’écran de la page Ajouter un site réseau.](media/manage-network-topology-add-site.png)

3. Pour associer le site à une région réseau, cliquez sur **Ajouter une région réseau**, sélectionnez une région existante ou cliquez sur **Ajouter** pour ajouter une région, puis cliquez sur **Lien**.  
4. Pour activer Location-Based routage pour le site, activez le **routage basé sur l’emplacement**.
5. Pour affecter des stratégies de services d’urgence au site, effectuez l’une des opérations suivantes ou les deux :

    - Si votre organisation utilise des forfaits d’appels, une connexion d’opérateur ou un routage direct, sous stratégie **d’appel d’urgence**, sélectionnez la stratégie souhaitée.
    - Si votre organisation a déployé le routage direct, sous stratégie de **routage des appels d’urgence**, sélectionnez la stratégie souhaitée.

6. Pour associer un sous-réseau au site, sous **Sous-réseaux**, cliquez sur **Ajouter des sous-réseaux**. Spécifiez la version IP, l’adresse IP, la plage réseau, ajoutez une description, puis cliquez sur **Appliquer**. Chaque sous-réseau doit être associé à un site spécifique.
7. Cliquez sur **Enregistrer**.

#### <a name="modify-a-network-site"></a>Modifier un site réseau

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à la **topologie réseau** **Emplacements** > , puis cliquez sur l’onglet **Sites réseau**.
2. Sélectionnez le site en cliquant à gauche du nom du site, puis cliquez sur **Modifier**.
3. Apportez les modifications souhaitées, puis cliquez sur **Enregistrer.**

### <a name="manage-external-trusted-ip-addresses"></a>Gérer les adresses IP approuvées externes

Vous gérez les adresses IP approuvées externes sous l’onglet **Adresses IP approuvées** de la page **Topologie réseau** du Centre d’administration Microsoft Teams. Vous pouvez ajouter un nombre illimité d’adresses IP approuvées externes.

#### <a name="add-a-trusted-ip-address"></a>Ajouter une adresse IP approuvée

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à la **topologie réseau** **Emplacements** > , puis cliquez sur l’onglet **Adresses IP approuvées**.
2. Cliquez sur **Nouveau**.
3. Dans le volet **Ajouter une adresse IP approuvée** , spécifiez la version IP, l’adresse IP, la plage réseau, ajoutez une description, puis cliquez sur **Appliquer**.

    ![Capture d’écran du volet Ajouter une adresse IP approuvée.](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Modifier une adresse IP approuvée

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à la **topologie réseau** **Emplacements** > , puis cliquez sur l’onglet **Adresses IP approuvées**.
2. Sélectionnez l’adresse IP en cliquant à gauche de celle-ci, puis cliquez sur **Modifier**.
3. Dans le volet **Modifier l’adresse IP approuvée** , apportez les modifications souhaitées, puis cliquez sur **Appliquer**.

## <a name="configure-network-settings-using-powershell"></a>Configurer les paramètres réseau à l’aide de PowerShell

Pour suivre les étapes décrites dans cette section, vous devez connaître les applets de commande PowerShell. Pour en savoir plus, consultez [La vue d’ensemble de Teams PowerShell](teams-powershell-overview.md).

### <a name="define-network-regions"></a>Définir des régions réseau

 Utilisez l’applet [de commande New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) pour définir des régions réseau. Notez que le paramètre RegionID est un nom logique qui représente la zone géographique de la région et n’a pas de dépendances ou de restrictions et que le paramètre d’ID&gt; de site CentralSite &lt;est facultatif.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

Dans cet exemple, nous créons une région réseau nommée Inde.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

Voir aussi [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworkregion).

### <a name="define-network-sites"></a>Définir des sites réseau

Utilisez l’applet [de commande New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) pour définir des sites réseau. Chaque site réseau doit être associé à une région réseau.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

Dans cet exemple, nous créons deux nouveaux sites réseau, Delhi et Hyderabad, dans la région de l’Inde.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

Le tableau suivant montre les sites réseau définis dans cet exemple.

|&nbsp;|Site 1 |Site 2 |
|---------|---------|---------|
|Site ID    |    Site 1 (Delhi)     |  Site 2 (Hyderabad)       |
|ID de région  |     Région 1 (Inde)    |   Région 1 (Inde)      |

Voir aussi [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworksite).

### <a name="define-network-subnets"></a>Définir des sous-réseaux réseau

Utilisez l’applet de commande [New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) pour définir des sous-réseaux réseau et les associer à des sites réseau. Chaque sous-réseau réseau ne peut être associé qu’à un seul site.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

Dans cet exemple, nous créons une association entre le sous-réseau 192.168.0.0 et le site réseau de Delhi et entre le sous-réseau 2001:4898:e8:25:844e:926f:85ad:dd8e et le site réseau Hyderabad.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

Le tableau suivant montre les sous-réseaux définis dans cet exemple.

|&nbsp;|Site 1 |Site 2 |
|---------|---------|---------|
|ID de sous-réseau   |    192.168.0.0     |  2001:4898:e8:25:844e:926f:85ad:dd8e     |
|Masque  |     24    |   120      |
|Site ID  | Site (Delhi) | Site 2 (Hyderabad) |

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


Consultez également [Set-CsTenantNetworkSubnet](/powershell/module/skype/set-cstenantnetworksubnet).


### <a name="define-external-subnets-external-trusted-ip-addresses"></a>Définir des sous-réseaux externes (adresses IP approuvées externes)

Utilisez l’applet de commande [New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) pour définir des sous-réseaux externes et les affecter au locataire. Vous pouvez définir un nombre illimité de sous-réseaux externes pour un locataire.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

Par exemple :

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

Voir aussi [Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress).

## <a name="related-topics"></a>Rubriques connexes

- [Paramètres réseau pour les fonctionnalités de voix cloud dans Teams](cloud-voice-network-settings.md)
