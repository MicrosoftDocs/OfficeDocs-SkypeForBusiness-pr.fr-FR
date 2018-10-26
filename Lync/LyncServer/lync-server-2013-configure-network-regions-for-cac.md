---
title: Configurer les régions de réseau pour le contrôle d’admission des appels (CAC)
TOCTitle: Configurer les régions de réseau pour le contrôle d’admission des appels (CAC)
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399051(v=OCS.15)
ms:contentKeyID: 49299253
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurer les régions de réseau pour le contrôle d’admission des appels (CAC)

 

_**Dernière rubrique modifiée :** 2012-09-21_

> [!IMPORTANT]  
> Si vous avez déjà créé des régions de réseau pour E9-1-1 ou la déviation du trafic multimédia, vous pouvez modifier les régions de réseau existantes en ajoutant des paramètres spécifiques au contrôle d’admission des appels (CAC) à l’aide de la cmdlet <strong>Set-CsNetworkRegion</strong>. Pour consulter un exemple de modification d’une région de réseau, voir <a href="lync-server-2013-create-or-modify-a-network-region.md">Création ou modification d’une région réseau dans Lync Server 2013</a> (contenu éventuellement en anglais).

Les *régions réseau* sont les concentrateurs réseau ou dorsales principales utilisés dans la configuration du contrôle d’admission des appels, du service E9-1-1 et de la déviation du trafic multimédia. Utilisez les procédures suivantes pour créer des régions de réseau alignées avec les régions de réseau de l’exemple de topologie de réseau pour le contrôle d’admission des appels. Pour afficher l’exemple de topologie du réseau, voir [Exemple : collecte des données de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) (contenu éventuellement en anglais) dans la documentation de planification.

L’exemple de topologie de réseau pour le contrôle d’admission des appels comporte trois régions : Amérique du Nord, EMEA et APAC. Chaque région dispose d’un site central spécifié. Pour l’Amérique du Nord, le site central désigné est CHICAGO. La procédure suivante présente un exemple montrant comment utiliser la cmdlet **New-CsNetworkRegion** pour créer la région Amérique du Nord.

> [!NOTE]  
> Dans la procédure suivante, Lync Server Management Shell sert à créer une région de réseau. Pour plus d’informations sur l’utilisation du Panneau de configuration Lync Server pour créer une région de réseau, voir <a href="lync-server-2013-create-or-modify-a-network-region.md">Création ou modification d’une région réseau dans Lync Server 2013</a> (contenu éventuellement en anglais).

## Pour créer une région de réseau pour le contrôle d’admission des appels

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Pour chaque région que vous devez créer, exécutez la cmdlet **New-CsNetworkRegion**. Par exemple, pour créer la région Amérique du Nord, exécutez :
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  Répétez l’étape 2 pour créer les régions de réseau EMEA et APAC.

