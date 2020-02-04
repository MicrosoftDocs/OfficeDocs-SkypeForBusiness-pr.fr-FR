---
title: Ajout d’un site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4fc2dd7426006d0c8f19b38b85ba778744fff2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>Ajout d’un site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-07_

Microsoft Lync Server 2013 les appareils de branchement Survivables (SBA) ne peuvent pas être associés à un pool Microsoft Lync Server 2010 frontal en tant qu’Bureau d’enregistrement de sauvegarde. Le SBA doit être associé à un pool Microsoft Lync Server 2013 front end. Ces étapes supposent un serveur Microsoft Lync Server 2013 SBA. Suivez cette procédure sur le site central.

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>Pour ajouter des sites de succursale avec Microsoft Lync Server 2013 SBA à votre topologie

1.  Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans l’arborescence de la console, développez le site central, développez **sites de succursales**, puis cliquez sur **nouveau site de succursale**.

3.  Dans la boîte de dialogue **définir un nouveau site de succursale** , cliquez sur **nom**, puis tapez un nom pour le nouveau site de succursale.

4.  Facultatif Cliquez sur **Description**, puis tapez une description significative pour le site de la succursale.

5.  Cliquez sur **Suivant**.

6.  Facultatif Dans la boîte de dialogue **définir un nouveau site de succursale** suivante, effectuez l’une des opérations suivantes :
    
      - Cliquez sur **City**, puis tapez le nom de la ville dans laquelle se trouve le site de la succursale.
    
      - Cliquez sur **état/région**, puis tapez le nom de l’État ou de la région où se trouve le site de la succursale.
    
      - Cliquez sur **indicatif du pays**, puis tapez le code d’appel à deux chiffres correspondant au pays/la région où se trouve le site de la succursale.

7.  Cliquez sur **suivant**, puis effectuez l’une des opérations suivantes :
    
      - Si vous utilisez un appareil de branchement ou un serveur de succursales survivant sur ce site, vérifiez que la case à cocher **ouvrir le nouvel Assistant survie à la fermeture de cet Assistant** est activée.
    
      - Si vous n’utilisez pas une application de succursale Survivable ou un serveur de succursales survivant sur ce site, désactivez la case à cocher **ouvrir le nouvel Assistant survie à la fermeture de cet Assistant** .
    
      - Cliquez sur **Terminer**, puis suivez les instructions de l’Assistant qui s’ouvre. Pour plus d’informations sur les éléments de l’Assistant, voir [définir une unité ou un serveur de succursales survivant dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).

8.  Répétez les étapes précédentes pour chaque site de succursale que vous voulez ajouter à la topologie.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Définition d’une passerelle RTC pour un site de succursale dans Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurer un Trunk sans dérivation multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

