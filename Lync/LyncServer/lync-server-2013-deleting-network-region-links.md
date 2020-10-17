---
title: 'Lync Server 2013 : suppression de liens de région réseau'
description: 'Lync Server 2013 : suppression de liens de région réseau.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a17c1ec64460e0f7cb447597f94aadd7fd2a9ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545330"
---
# <a name="deleting-network-region-links-in-lync-server-2013"></a>Suppression de liens de région réseau dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Vous pouvez configurer les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC). Au sein d’un réseau, les régions sont liées par une connectivité physique au réseau étendu (WAN). Vous pouvez utiliser le panneau de configuration Lync Server pour supprimer un lien existant entre deux régions réseau. Pour plus d’informations sur la création ou la modification d’un lien de région réseau, voir [Configuring Network Region Links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)

<div>

## <a name="to-delete-a-network-region-link"></a>Pour supprimer un lien de région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Lien de région**.

4.  Dans la page **Lien de région**, cliquez sur le lien de région que vous souhaitez supprimer.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs liens de région à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs liens de région. Ou, pour sélectionner tous les liens de région, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG>.

    
    </div>

5.  Dans le menu **Edition**, sélectionnez **Supprimer**.

6.  Cliquez sur **OK**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration des liens de région réseau dans Lync Server 2013](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

