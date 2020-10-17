---
title: 'Lync Server 2013 : suppression des itinéraires de région réseau existants'
description: 'Lync Server 2013 : suppression des itinéraires de région réseau existants.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2501dc3f4ed88a56e9f591e3af11a673046280a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557900"
---
# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a>Suppression des itinéraires de région réseau existants dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Chaque région au sein d’un contrôle d’admission des appels doit disposer d’un moyen lui permettant d’accéder à toutes les autres régions. Alors que les liens de région définissent des restrictions de bande passante sur les connexions entre les régions et qu’ils représentent également des liens physiques, un itinéraire détermine le chemin lié que la connexion traverse d’une région à une autre. Vous pouvez utiliser le panneau de configuration Lync Server pour configurer les itinéraires de région réseau. Dans le panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer un itinéraire de région réseau. Utilisez cette rubrique pour supprimer des itinéraires de région réseau existants. Pour plus d’informations sur la création ou la modification des itinéraires de région réseau, voir [création ou modification des itinéraires de région réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).

<div>

## <a name="to-delete-a-network-region-route"></a>Pour supprimer un itinéraire de région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Itinéraire de région**.

4.  Dans la page **Itinéraire de région**, cliquez sur l’itinéraire de région à supprimer.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs itinéraires de région à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs itinéraires de région. Ou, pour sélectionner tous les itinéraires de région, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG>.

    
    </div>

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification des itinéraires de région réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md)  


[Configurer un itinéraire de région réseau](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))  


[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

