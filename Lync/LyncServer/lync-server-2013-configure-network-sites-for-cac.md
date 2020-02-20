---
title: 'Lync Server 2013 : configuration des sites réseau pour le contrôle d’admission des opérations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a44d3e25aecb33b6f3969213c682cfa90b7d5a1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>Configuration des sites réseau pour le contrôle d’admission des adresses dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> Si vous avez déjà créé des sites réseau pour E9-1-1 ou le contournement de média, vous pouvez modifier les sites réseau existants pour appliquer un profil de stratégie de bande passante à l’aide de l’applet de commande <STRONG>Set-CsNetworkSite</STRONG>. Pour obtenir un exemple de la façon de modifier un site réseau, reportez-vous à la rubrique <A href="lync-server-2013-create-or-modify-a-network-site.md">créer ou modifier un site réseau dans Lync Server 2013</A>.



</div>

Les *sites réseau* sont les bureaux ou emplacements au sein de chaque région réseau des déploiements de contrôle d’admission des appels (Call Admission Control ou CAC), E9-1-1 et de contournement de média. Utilisez les procédures suivantes pour créer des sites réseau qui s’alignent sur les sites réseau de l’exemple de topologie de réseau pour le service CAC. Ces procédures indiquent comment créer et configurer des sites réseau restreints par la bande passante de réseau étendu et qui nécessitent, par conséquent, des stratégies de bande passante qui limitent le flux du trafic audio ou vidéo en temps réel.

Dans l’exemple de déploiement CAC, la région Amérique du Nord comporte six sites. Parmi ces sites, trois sont restreints par la bande passante de réseau étendu : Reno, Portland et Albuquerque. Les trois autres sites, qui ne sont *pas* restreints par la bande passante de réseau étendu sont les suivants : New York, Chicago et Détroit. Pour obtenir un exemple de création ou de modification de ces autres sites réseau, reportez-vous à la rubrique [créer ou modifier un site réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Pour afficher l’exemple de topologie réseau, reportez-vous à l’exemple [suivant : collecte de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) dans la documentation de planification.

<div class=" ">


> [!NOTE]  
> Dans la procédure suivante, Lync Server Management Shell est utilisé pour créer un site réseau. Pour plus d’informations sur l’utilisation du panneau de configuration Lync Server pour créer un site réseau, voir <A href="lync-server-2013-create-or-modify-a-network-site.md">créer ou modifier un site réseau dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>Pour créer des sites réseau pour le contrôle d’admission des appels

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande **New-CsNetworkSite** pour créer des sites réseau, puis appliquez un profil de stratégie de bande passante approprié à chaque site. Par exemple, exécutez :
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  Afin de terminer la création de sites réseau pour l’ensemble de l’exemple de topologie, répétez l’étape 2 pour les sites réseau à bande passante restreinte dans les régions EMEA et APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

