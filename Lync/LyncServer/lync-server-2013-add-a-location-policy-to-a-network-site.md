---
title: Ajouter une stratégie d’emplacement à un site réseau
TOCTitle: Ajouter une stratégie d’emplacement à un site réseau
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425936(v=OCS.15)
ms:contentKeyID: 49297044
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ajouter une stratégie d’emplacement à un site réseau

 

_**Dernière rubrique modifiée :** 2013-02-24_

Les exemples suivants indiquent comment ajouter la stratégie d’emplacement **Redmond** définie dans [Créer des stratégies d’emplacement dans Lync Server 2013](lync-server-2013-create-location-policies.md) à un site réseau existant, mais aussi comment créer un nouveau site réseau qui utilise la stratégie d’emplacement **Redmond**.

Pour plus d’informations sur l’utilisation des sites réseau, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - **New-CsNetworkSite**

  - **Get-CsNetworkSite**

  - **Set-CsNetworkSite**

  - **Remove-CsNetworkSite**

## Pour affecter une stratégie d’emplacement à un site réseau existant

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez les applets de commande suivantes pour modifier un site réseau existant.
    
    Affectez la stratégie d’emplacement balisée **Redmond** à un site réseau existant appelé **Redmond**.
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

## Pour affecter une stratégie d’emplacement à un nouveau site réseau

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande suivante pour créer un nouveau site réseau.
    
    Créez un nouveau site réseau dans la région réseau et affectez la stratégie d’emplacement balisée **Redmond**.
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

