---
title: Utiliser PowerShell pour les tâches dans le menu Configuration du réseau
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Résumé : Skype Entreprise Server panneau de configuration au mappage de cmdlet pour le menu Configuration du réseau.'
ms.openlocfilehash: aa42ac465ffd72a4aff9c03293124c857e5b712c
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626136"
---
# <a name="network-configuration"></a>Configuration réseau

Cet article décrit comment des résultats similaires à ceux de l’élément de menu **Configuration** réseau du Panneau de configuration hérité peuvent être obtenus à l’aide d’cmdlets.

Cet article décrit les sous-menus suivants :

- [Configuration du réseau](#network-configuration)
  - [Stratégie d’emplacement](#location-policy)
  - [Stratégie de bande passante](#bandwidth-policy)
  - [Région](#region)
  - [Site](#site)
  - [Subnet](#subnet)
  - [Lien de région](#region-link)
  - [Itinéraire de région](#region-route)

## <a name="location-policy"></a>Stratégie d’emplacement

Le **sous-menu STRATÉGIE** D’EMPLACEMENT est utilisé pour appliquer les paramètres liés à la fonctionnalité E9-1-1. La stratégie d’emplacement détermine si un utilisateur peut avoir recours au système E9-1-1 et, le cas échéant, le comportement d’un appel d’urgence.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur LA STRATÉGIE D’EMPLACEMENT **et** les cmdlets Skype Entreprise que ces tâches m’indiquent.

---

> **Scénario 1 :** liste de toutes les stratégies d’emplacement

   ![Stratégie d’emplacement de liste](./media/location-policy-1.png)

***Cmdlet***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***Exemple***

```powershell
 Get-CsLocationPolicy
```

---

> **Scénario 2 :** créer une stratégie d’emplacement

   ![Créer une stratégie d’emplacement](./media/location-policy-2.png)

***Cmdlet***

[New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy)  

***Exemple***

```powershell
 New-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

> **Scénario 3 :** obtenir les détails d’une stratégie d’emplacement choisie

   ![Obtenir une stratégie d’emplacement](./media/location-policy-3.png)

***Cmdlet***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***Exemple***

```powershell
 Get-CsLocationPolicy -Identity Reno
```

---

> **Scénario 4 :** supprimer les stratégies d’emplacement choisies

   ![Supprimer une stratégie d’emplacement](./media/location-policy-4.png)

***Cmdlet***

[Remove-CsLocationPolicy](/powershell/module/skype/remove-cslocationpolicy)

***Exemple***

```powershell
 Remove-CsLocationPolicy -Identity Reno
```

---

> **Scénario 5 :** mettre à jour une stratégie d’emplacement

   ![Mettre à jour la stratégie d’emplacement](./media/location-policy-5.png)

***Cmdlet***

[Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy)

***Exemple***

```powershell
 Set-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

## <a name="bandwidth-policy"></a>Stratégie de bande passante

La stratégie de bande passante utilisée dans le cadre du contrôle d’admission des appels (CAC) permet de définir des restrictions de bande passante pour des modes bien précis. (Dans Skype Entreprise Server, seules les modalités audio et vidéo peuvent être affectées à des restrictions de bande passante.) Cette cmdlet crée un profil de conteneur pour ces stratégies. Vous définissez les stratégies individuelles dans le conteneur en indiquant les limites de bande passante audio et vidéo lorsque vous appelez cette applet de commande.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **BANDWIDTH POLICY** et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---
> **Scénario 1 :** liste de toutes les stratégies de bande passante

   ![Stratégie de bande passante de liste](./media/bandwidth-policy-1.png)

***Cmdlet***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***Exemple***

```powershell
 Get-CsNetworkBandwidthPolicyProfile
```

---

> **Scénario 2 :** créer une stratégie de bande passante

   ![Nouvelle stratégie de bande passante](./media/bandwidth-policy-2.png)

***Cmdlet***

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile)  

***Exemple***

```powershell
 New-CsNetworkBandwidthPolicyProfile -Identity LowBWLimits -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400 -VideoBWSessionLimit 500
```

---

> **Scénario 3 :** obtenir les détails d’une stratégie de bande passante choisie

   ![Obtenir une stratégie de bande passante](./media/bandwidth-policy-3.png)

***Cmdlet***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***Exemple***

```powershell
 Get-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **Scénario 4 : supprimer** les stratégies de bande passante choisies

   ![Supprimer la stratégie de bande passante](./media/bandwidth-policy-4.png)

***Cmdlet***

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile)

***Exemple***

```powershell
 Remove-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **Scénario 5 : mettre** à jour une stratégie de bande passante

   ![Mettre à jour la stratégie de bande passante](./media/bandwidth-policy-5.png)

***Cmdlet***

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile)

***Exemple***

```powershell
 Set-CsNetworkBandwidthPolicyProfile -Identity LowBWLimit -VideoBWLimit 2500 -VideoBWSessionLimit 300
```

---

## <a name="region"></a>Région

Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques. Chaque région réseau doit être associée à un site central. Les administrateurs peuvent utiliser le menu **RÉGION** pour gérer les informations sur une ou plusieurs régions réseau, y compris le site central associé et les paramètres qui déterminent si d’autres chemins d’accès sont autorisés pour les connexions audio et vidéo et qui associent les sites de la région à une configuration de contournement de média.

---

> **Scénario 1 :** Liste de toutes les régions

   ![Zone de liste](./media/network-region-1.png)

***Cmdlet***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***Exemple***

```powershell
 Get-CsNetworkRegion
```

---

> **Scénario 2**: créer une région

   ![Créer une région](./media/network-region-2.png)

***Cmdlet***

[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion)  

***Exemple***

```powershell
 New-CsNetworkRegion -Identity NorthAmerica -Description "All North American Locations" -CentralSite Redmond-NA-MLS
```

---

> **Scénario 3 :** obtenir les détails d’une région sélectionnée

   ![Obtenir la région](./media/network-region-3.png)

***Cmdlet***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***Exemple***

```powershell
 Get-CsNetworkRegion -Identity NorthAmerica
```

---

> **Scénario 4 :** Supprimer les régions sélectionnées

   ![Supprimer une région](./media/network-region-4.png)

***Cmdlet***

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion)

***Exemple***

```powershell
 Remove-CsNetworkRegion -Identity NorthAmerica
```

---

> **Scénario 5 :** mettre à jour une région

   ![Mettre à jour la région](./media/network-region-5.png)

- **Annotation 1 - Résultat**

    Cette annotation sur l’image indique un résultat, c’est-à-dire les données récupérées et affichées.

    ***Cmdlet***

    [Get-CsNetworkSite de region](/powershell/module/skype/get-csnetworksite)

    ***Exemple***

    ```powershell
     Get-CsNetworkSite | Where-Object {$_.NetworkRegionID -eq "AKR"}
    ```

- **Annotation 2 - Option (pour l’utilisateur)**

    Cette annotation sur l’image indique une option que l’utilisateur peut implémenter, c’est-à-dire, pour enregistrer une région réseau.

    [Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion)

   ***Exemple***

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -Description "North American Region"
   ```

---

## <a name="site"></a>Site

Les sites réseau sont les bureaux ou emplacements configurés au sein de chaque région d’un contrôle d’admission des appels (Call Admission Control ou CAC) ou encore d’un déploiement E9-1-1. **Le** sous-menu SITE permet aux administrateurs d’ajouter, de supprimer ou de gérer leurs paramètres.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **SITE** et les cmdlets Skype Entreprise ces tâches m’indiquent.

---

> **Scénario 1 :** lister tous les sites

   ![Site de liste](./media/network-site-1.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***Exemple***

```powershell
 Get-CsNetworkSite
```

---

> **Scénario 2**: créer un site

   ![Créer un site](./media/network-site-2.png)

***Cmdlet***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksite)  

***Exemple***

```powershell
 New-CsNetworkSite -Identity Vancouver -NetworkRegionID NorthAmerica
```

---

> **Scénario 3 :** obtenir les détails d’un site choisi

   ![Obtenir un site](./media/network-site-3.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***Exemple***

```powershell
 Get-CsNetworkSite -Identity Redmond
```

---

> **Scénario 4 :** supprimer les sites sélectionnés

   ![Supprimer un site](./media/network-site-4.png)

***Cmdlet***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksite)

***Exemple***

```powershell
 Remove-CsNetworkSite -Identity Vancouver
```

---

> **Scénario 5 :** mettre à jour un site

   ![Mettre à jour le site](./media/network-site-5.png)

- **Annotation 1 - Résultat**

    Cette annotation sur l’image indique un résultat, c’est-à-dire les données récupérées et affichées.

    ***Cmdlet***

    [Get-CsNetworkSubnet à partir du site](/powershell/module/skype/get-csnetworksubnet)

    ***Exemple***

    ```powershell
     Get-CsNetworkSubnet | Where-Object {$_.NetworkSiteID -eq "Vancouver"}
    ```

- **Annotation 2 - Option (pour l’utilisateur)**

    Cette annotation sur l’image indique une option que l’utilisateur peut implémenter, c’est-à-dire, pour enregistrer un site réseau.

   ***Cmdlet***

   [Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksite)

   ***Exemple***

   ```powershell
    Set-CsNetworkSite -Identity Vancouver - BWPolicyProfileID LowBWLimits
   ```

---

## <a name="subnet"></a>Sous-réseau

Les administrateurs peuvent utiliser **le sous-menu SUBNET** pour créer, mettre à jour et gérer des sous-réseaux.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **SUBNET** et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---

> **Scénario 1 :** Liste de tous les sous-réseaux

   ![Sous-réseau de liste](./media/network-subnet-1.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***Exemple***

```powershell
 Get-CsNetworkSubnet
```

---

> **Scénario 2**: créer un sous-réseau

   ![Créer un sous-réseau](./media/network-subnet-2.png)

***Cmdlet***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet)  

***Exemple***

```powershell
 New-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 24 -NetworkSiteID Vancouver
```

---

> **Scénario 3**: obtenir les détails d’un sous-réseau choisi

   ![Obtenir un sous-réseau](./media/network-subnet-3.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***Exemple***

```powershell
 Get-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **Scénario 4 :** Supprimer les sous-réseaux sélectionnés

   ![Supprimer un sous-réseau](./media/network-subnet-4.png)

***Cmdlet***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet)

***Exemple***

```powershell
 Remove-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **Scénario 5 :** mettre à jour un sous-réseau

   ![Mettre à jour un sous-réseau](./media/network-subnet-5.png)

***Cmdlet***

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet)

***Exemple***

```powershell
 Set-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 25 -NetworkSiteID Chicago
```

---

## <a name="region-link"></a>Lien de région

Les régions au sein d’un réseau sont liées par le biais d’une connectivité WAN physique. Les administrateurs peuvent utiliser le sous-menu **LIEN RÉGION** pour créer, mettre à jour et gérer des sous-réseaux.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **REGION LINK** et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---

> **Scénario 1 :** lister tous les liens de région

   ![Lien de région de liste](./media/network-regionlink-1.png)

***Cmdlet***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***Exemple***

```powershell
 Get-CsNetworkRegionLink
```

---

> **Scénario 2 :** créer un lien de région

   ![Créer un lien de région](./media/network-regionlink-2.png)

***Cmdlet***

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionLink)  

***Exemple***

```powershell
 New-CsNetworkRegionLink -Identity NA_EMEA -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID LowBWLimits
```

---

> **Scénario 3 :** obtenir les détails d’un lien de région choisi

   ![Obtenir un lien de région](./media/network-regionlink-3.png)

***Cmdlet***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***Exemple***

```powershell
 Get-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **Scénario 4 :** supprimer les liens de région choisis

   ![Supprimer un lien de région](./media/network-regionlink-4.png)

***Cmdlet***

[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionLink)

***Exemple***

```powershell
 Remove-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **Scénario 5 :** mettre à jour un lien de région

   ![Mettre à jour le lien de région](./media/network-regionlink-5.png)

***Cmdlet***

[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionLink)

***Exemple***

```powershell
 Set-CsNetworkRegionLink -Identity NA_EMEA -BWPolicyProfileID HighBWLimits
```

---

## <a name="region-route"></a>Itinéraire de région

Chaque zone d’une configuration de contrôle d’admission des appels doit pouvoir accéder à toutes les autres zones. Alors que les liens de région définissent des restrictions de bande passante sur les connexions entre les régions et qu’ils représentent des liens physiques, un routage détermine le chemin lié que la connexion traverse d’une région à une autre. Les administrateurs peuvent utiliser le sous-menu **ROUTE** RÉGION pour créer, mettre à jour et gérer ces éléments.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **REGION ROUTE** et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---

> **Scénario 1 :** liste de tous les itinéraires de région

   ![Itinéraire de région de liste](./media/network-regionroute-1.png)

***Cmdlet***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***Exemple***

```powershell
 Get-CsNetworkInterRegionRoute
```

---

> **Scénario 2 :** créer un itinéraire de région

   ![Créer un itinéraire de région](./media/network-regionroute-2.png)

***Cmdlet***

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute)  

***Exemple***

```powershell
 New-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA_EMEA,EMEA_APAC"
```

---

> **Scénario 3 :** obtenir les détails d’un itinéraire de région choisi

   ![Obtenir l’itinéraire de région](./media/network-regionroute-3.png)

***Cmdlet***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***Exemple***

```powershell
 Get-CsNetworkInterRegionRoute -Filter *APAC*
```

---

> **Scénario 4 :** supprimer les itinéraires de région choisis

   ![Supprimer l’itinéraire de région](./media/network-regionroute-4.png)

***Cmdlet***

[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute)

***Exemple***

```powershell
 Remove-CsNetworkInterRegionRoute -Identity NA_APAC_Route
```

---

> **Scénario 5 :** mettre à jour un itinéraire de région

   ![Mettre à jour l’itinéraire de région](./media/network-regionroute-5.png)

- **Annotation 1 - Option (pour l’utilisateur)**

    Cette annotation sur l’image indique un résultat, c’est-à-dire les données récupérées et affichées.

   ***Cmdlet***

   [Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

   ***Exemple***

   ```powershell
   Get-CsNetworkRegionLink
   ```

- **Annotation 2 - Option (pour l’utilisateur)**

    Cette annotation sur l’image indique une option que l’utilisateur peut implémenter, c’est-à-dire, pour enregistrer un itinéraire de région réseau.

    ***Cmdlet***

   [Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute)

   ***Exemple***

   ```powershell
   Set-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionLinkIDs "NA_SA,SA_APAC"
   ```

---
---
