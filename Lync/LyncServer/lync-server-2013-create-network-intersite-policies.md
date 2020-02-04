---
title: 'Lync Server 2013 : création de stratégies d’intersite réseau'
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
ms.openlocfilehash: 655cde30a3d798d57520c57e3882b2162010888c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a>Créer des stratégies d’intersite réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Une *stratégie d’intersite réseau* définit des limitations de bande passante entre les sites disposant de liens WAN directs entre eux.

Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> Une stratégie d’intersite réseau est requise <EM>uniquement</EM> s’il existe un lien croisé direct entre deux sites du réseau.



</div>

Dans la région Amérique du Nord de l’exemple de topologie, il existe un lien direct entre les sites Reno et Albuquerque. Ces deux sites nécessitent une stratégie de intersite qui applique un profil de stratégie de bande passante approprié. L’exemple suivant applique le profil\_de liaison 20Mo.

<div>

## <a name="to-create-a-network-intersite-policy"></a>Pour créer une stratégie d’intersite réseau

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de nouvelle applet de CsNetworkInterSitePolicy pour créer des stratégies d’intersite réseau et appliquer un profil de stratégie de bande passante approprié pour deux sites qui disposent d’un lien direct. Par exemple, exécutez :
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  Répétez l’étape 2 autant de fois que nécessaire pour créer des stratégies d’intersite réseau pour toutes les paires de sites réseau qui présentent un lien croisé direct.

</div>

</div>

<span> </span>

</div>

</div>

</div>

