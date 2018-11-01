---
title: "Conf. les sites réseau pour le contr. d’adm. des appels dans Lync Server 2013"
TOCtitle: "Conf. les sites réseau pour le contr. d’adm. des appels dans Lync Server 2013"
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412840(v=OCS.15)
ms:contentKeyID: 49298526
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurer les sites réseau pour le contrôle d’admission des appels dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-05_

> [!IMPORTANT]  
> Si vous avez déjà créé des sites réseau pour E9-1-1 ou le contournement de média, vous pouvez modifier les sites réseau existants pour appliquer un profil de stratégie de bande passante à l’aide de l’applet de commande <strong>Set-CsNetworkSite</strong>. Pour consulter un exemple présentant la procédure permettant de modifier un site réseau, voir <a href="lync-server-2013-create-or-modify-a-network-site.md">Création ou modification d’un site réseau dans Lync Server 2013</a>.

Les *sites réseau* sont les bureaux ou emplacements au sein de chaque région réseau des déploiements de contrôle d’admission des appels (Call Admission Control ou CAC), E9-1-1 et de contournement de média. Utilisez les procédures suivantes pour créer des sites réseau qui s’alignent sur les sites réseau de l’exemple de topologie de réseau pour le service CAC. Ces procédures indiquent comment créer et configurer des sites réseau restreints par la bande passante de réseau étendu et qui nécessitent, par conséquent, des stratégies de bande passante qui limitent le flux du trafic audio ou vidéo en temps réel.

Dans l’exemple de déploiement CAC, la région Amérique du Nord comporte six sites. Parmi ces sites, trois sont restreints par la bande passante de réseau étendu : Reno, Portland et Albuquerque. Les trois autres sites, qui ne sont *pas* restreints par la bande passante de réseau étendu sont les suivants : New York, Chicago et Détroit. Pour consulter un exemple présentant la procédure de création ou de modification de ces autres sites réseau, voir [Création ou modification d’un site réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Pour afficher l’exemple de topologie du réseau, voir l’[Exemple : collecte des données de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) dans la documentation de planification.

> [!NOTE]  
> La procédure suivante utilise Lync Server Management Shell pour créer un site réseau. Pour plus d’informations sur l’utilisation du Panneau de configuration Lync Server pour créer un site réseau, voir <a href="lync-server-2013-create-or-modify-a-network-site.md">Création ou modification d’un site réseau dans Lync Server 2013</a>.

## Pour créer des sites réseau pour le contrôle d’admission des appels

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande **New-CsNetworkSite** pour créer des sites réseau, puis appliquez un profil de stratégie de bande passante approprié à chaque site. Par exemple, exécutez :
    
    ```
    New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
    ```
    ```
    New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
    ```
    ```
    New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
    ```

3.  Afin de terminer la création de sites réseau pour l’ensemble de l’exemple de topologie, répétez l’étape 2 pour les sites réseau à bande passante restreinte dans les régions EMEA et APAC.

