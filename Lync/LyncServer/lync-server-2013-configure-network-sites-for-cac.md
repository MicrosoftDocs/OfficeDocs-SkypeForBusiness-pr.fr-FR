---
title: 'Lync Server 2013: configurer les sites réseau pour le CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 528ed67243fb0ab0451abf504a458afc420d94ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>Configurer les sites réseau pour le CAC dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> Si vous avez déjà créé des sites réseau pour le contournement de E9-1-1 ou du contenu multimédia, vous pouvez modifier les sites réseau existants pour appliquer un profil de stratégie de bande passante à l’aide de l’applet de connexion <STRONG>Set-CsNetworkSite</STRONG> . Pour obtenir un exemple illustrant comment modifier un site réseau, voir <A href="lync-server-2013-create-or-modify-a-network-site.md">créer ou modifier un site réseau dans Lync Server 2013</A>.



</div>

Les *sites réseau* sont les bureaux ou les emplacements dans chaque région du réseau de déploiement d’admission des appels (CAC), de E9-1-1 et de contournement de média. Utilisez les procédures suivantes pour créer des sites réseau qui s’alignent sur les sites réseau dans l’exemple de topologie réseau pour CAC. Les procédures suivantes vous expliquent comment créer et configurer des sites réseau limités par une bande passante WAN et exiger ainsi des stratégies de bande passante qui limitent le flux de trafic audio ou vidéo en temps réel.

Dans l’exemple de déploiement CAC, la région Amérique du Nord comporte six sites. Trois de ces sites sont limités par une bande passante WAN: Reno, Portland et Albuquerque. Les trois autres sites, qui ne sont *pas* limités par la bande passante WAN: New York, Chicago et détroit. Pour obtenir un exemple illustrant la création ou la modification de ces sites, voir [créer ou modifier un site réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Pour afficher l’exemple de topologie du réseau, reportez-vous à la rubrique [exemple: rassemblement des exigences relatives au contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) dans la documentation de planification.

<div class=" ">


> [!NOTE]  
> Dans la procédure suivante, Lync Server Management Shell est utilisé pour créer un site réseau. Pour plus d’informations sur l’utilisation du panneau de configuration de Lync Server pour créer un site réseau, voir <A href="lync-server-2013-create-or-modify-a-network-site.md">créer ou modifier un site réseau dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>Pour créer un site réseau pour le contrôle d’admission des appels

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de nouvelle applet de **CsNetworkSite** pour créer des sites réseau et appliquer un profil de stratégie de bande passante approprié à chaque site. Par exemple, exécutez :
    
       ```
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  Pour terminer la création de sites réseau pour la topologie d’exemple complète, répétez l’étape 2 pour les sites réseau limités en bande passante dans les régions EMEA et APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

