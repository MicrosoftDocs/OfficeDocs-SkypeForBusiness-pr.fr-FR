---
title: Créer des stratégies inter-sites réseau
TOCTitle: Créer des stratégies inter-sites réseau
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412844(v=OCS.15)
ms:contentKeyID: 49298566
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer des stratégies inter-sites réseau

 

_**Dernière rubrique modifiée :** 2012-10-19_

Une *stratégie intersite réseau* définit des limitations de bande passante entre des sites présentant des liens directs WAN entre eux.

Pour plus d’informations, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

> [!IMPORTANT]  
> Une stratégie intersite réseau est nécessaire <em>uniquement</em> s’il existe un lien d’accès direct entre deux sites réseau.

Dans la région Amérique du Nord de l’exemple de topologie, il existe un lien direct entre les sites Reno et Albuquerque. Ces deux sites nécessitent une stratégie intersite qui applique un profil de stratégie de bande passante approprié. L’exemple suivant applique le profil 20Mb\_Link.

## Pour créer une stratégie intersite réseau

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande New-CsNetworkInterSitePolicy pour créer des stratégies intersite réseau et appliquez un profil de stratégie de bande passante approprié pour deux sites qui présentent un lien d’accès direct. Par exemple, exécutez :
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  Répétez l’étape 2 autant que nécessaire, afin de créer des stratégies intersite réseau pour toutes les paires de sites réseau qui présentent un lien d’accès direct.

