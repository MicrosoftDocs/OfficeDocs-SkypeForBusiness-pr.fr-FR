---
title: 'Lync Server 2013 : création de stratégies intersite réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55c8523fe86cfee7b9e2332e459959b096831abb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515591"
---
# <a name="create-network-intersite-policies-in-lync-server-2013"></a>Créer des stratégies inter-sites réseau dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Une *stratégie intersite réseau* définit des limitations de bande passante entre des sites présentant des liens directs WAN entre eux.

Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> Une stratégie intersite réseau est nécessaire <EM>uniquement</EM> s’il existe un lien d’accès direct entre deux sites réseau.



</div>

Dans la région Amérique du Nord de l’exemple de topologie, il existe un lien direct entre les sites Reno et Albuquerque. Ces deux sites nécessitent une stratégie intersite qui applique un profil de stratégie de bande passante approprié. L’exemple suivant applique le \_ profil de lien 20Mo.

<div>

## <a name="to-create-a-network-intersite-policy"></a>Pour créer une stratégie intersite réseau

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande New-CsNetworkInterSitePolicy pour créer des stratégies intersite réseau et appliquez un profil de stratégie de bande passante approprié pour deux sites qui présentent un lien d’accès direct. Par exemple, exécutez :
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  Répétez l’étape 2 autant que nécessaire, afin de créer des stratégies intersite réseau pour toutes les paires de sites réseau qui présentent un lien d’accès direct.

</div>

</div>

<span> </span>

</div>

</div>

</div>

