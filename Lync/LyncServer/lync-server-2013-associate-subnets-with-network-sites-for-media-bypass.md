---
title: 'Lync Server 2013 : associez des sous-réseaux à des sites réseau pour la déviation du trafic multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe244426b6c2b7f83ef8070f995305a2a02ef31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a>Associer des sous-réseaux à des sites réseau pour la déviation du trafic multimédia dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-12_

<div>


> [!NOTE]  
> Dans cette rubrique, nous partons du principe que vous avez déjà configuré les paramètres globaux de contournement de média, mais aussi la région et les sites de réseau pour le contournement de média.



</div>

Chaque sous-réseau de votre réseau doit être associé à un site réseau spécifique. Ceci est dû au fait que les informations de sous-réseau permettent de déterminer le site réseau sur lequel se trouve un système d’extrémité. Lorsque les emplacements des deux parties sont connus dans une session, le contournement de média peut déterminer où le média doit être envoyé pour traitement.

Le contournement de média ne doit respecter aucune condition particulière pour associer les sous-réseaux aux sites réseau. Pour créer une association entre les sous-réseaux et les sites réseau de votre topologie, suivez les procédures décrites dans [associer un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a>Étapes suivantes : Créer des profils de stratégie de bande passante

Une fois que vous avez associé les sous-réseaux à des sites réseau pour le contournement de média, vous devez créer un ou plusieurs profils de stratégie de bande passante qui partitionneront les sous-réseaux en éléments de bonne connectivité et éléments sans connectivité à des fins de contournement de média. Tous les sous-réseaux d’une région réseau comportant des sites réseau qui ne sont soumis à aucune limitation de bande passante disposent d’une bonne connectivité. Ces sous-réseaux peuvent donc utiliser le contournement de média.

Pour connaître les procédures de configuration des profils de stratégie de bande passante, voir [Create Bandwidth Policy Profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

