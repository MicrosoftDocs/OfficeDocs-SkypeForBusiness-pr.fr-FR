---
title: Ajouter le site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie
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
ms.openlocfilehash: 1e57a7b062cd95012102ba30a527c99c2fba71d6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>Ajouter le site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-07_

Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) ne peut pas être associé à un pool frontal Microsoft Lync Server 2010 comme serveur d’inscriptions de sauvegarde. Le SBA doit être associé à un pool frontal Microsoft Lync Server 2013. Ces étapes supposent une Microsoft Lync Server 2013 SBA. Cette procédure doit être effectuée sur le site central.

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>Pour ajouter des sites de succursale avec Microsoft Lync Server 2013 SBA à votre topologie

1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

2.  Dans l’arborescence de la console, développez successivement le site central, **Sites de succursale**, puis cliquez sur **Nouveau site de succursale**.

3.  Dans la boîte de dialogue **Définir un nouveau site de succursale**, cliquez sur **Nom**, puis tapez un nom pour le nouveau site de succursale.

4.  (Facultatif) Cliquez sur **Description**, puis tapez une description explicite pour le site de succursale.

5.  Cliquez sur **Suivant**.

6.  (Facultatif) Dans la boîte de dialogue **Définir un nouveau site de succursale** qui suit, effectuez l’une des opérations suivantes :
    
      - Cliquez sur **Ville**, puis tapez le nom de la ville dans laquelle se trouve le site de succursale.
    
      - Cliquez sur **Dép./Région**, puis tapez le nom du département ou de la région où se trouve le site de succursale.
    
      - Cliquez sur **Code du pays**, puis tapez le code d’appel à deux chiffres du pays ou de la région du site de succursale.

7.  Cliquez sur **Suivant** et effectuez l’une des opérations suivantes :
    
      - Si vous utilisez un Survivable Branch Appliance ou un serveur Survivable Branch Server sur ce site, vérifiez que la case à cocher **ouvrir l’Assistant Nouveau Survivable Branch Wizard à la fermeture de cet Assistant** est activée.
    
      - Si vous n’utilisez pas un Survivable Branch Appliance ou un serveur Survivable Branch Server sur ce site, désactivez la case à cocher **ouvrir l’Assistant Nouveau Survivable Branch Server lors de la fermeture de cet Assistant** .
    
      - Cliquez sur **Terminer**, puis suivez les instructions de l’Assistant qui s’ouvre. Pour plus d’informations sur les éléments de l’Assistant, voir [define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).

8.  Répétez les étapes précédentes pour chaque site de succursale que vous souhaitez ajouter à la topologie.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Définition d’une passerelle PSTN pour un site de succursale dans Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

